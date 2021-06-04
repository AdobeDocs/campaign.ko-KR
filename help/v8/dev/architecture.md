---
product: Adobe Campaign
title: Campaign 아키텍처 시작
description: Campaign 아키텍처 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: e6086620909277eaaf5966335df9b71c6830e726
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Campaign 아키텍처 시작{#gs-ac-archi}

## 환경

Campaign은 개별 인스턴스로서 사용할 수 있게 되었으며, 이때 각 인스턴스는 전체 캠페인 환경을 나타냅니다.

Campaign Cloud Service에서 사용할 수 있는 환경의 세 가지 유형은 다음과 같습니다.

* **프로덕션 환경**:비즈니스 전문가를 위한 애플리케이션을 호스팅합니다.

* **스테이지 환경**:애플리케이션 변경 사항이 프로덕션 환경에 푸시되기 전에 다양한 성능 및 품질 테스트에 사용됩니다.

* **개발 환경**:개발자는 단계 및 프로덕션 환경과 동일한 런타임 조건으로 Campaign을 구현할 수 있습니다.

한 환경에서 다른 환경으로 패키지를 내보내고 가져올 수 있습니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 패키지에 대해 자세히 알아보십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## 중간 소싱 배포{#mid-sourcing-deployment}

서버와 프로세스 간의 일반 통신은 다음 스키마에 따라 수행됩니다.

![](assets/architecture.png)

* 인스턴스에서 실행 및 반송 관리 모듈을 사용할 수 없습니다.

* 이 애플리케이션은 SOAP 호출(HTTP 또는 HTTPS를 통해)을 사용하여 구동되는 원격 &quot;mid 소스&quot; 서버에서 메시지 실행을 수행하도록 구성됩니다.

>[!NOTE]
>
> Campaign v8은 하이브리드 아키텍처를 사용합니다. Campaign Classic v7에서 전환하는 경우 모든 게재는 중간 소싱 서버를 통과합니다.
> 따라서 Campaign v8에서는 내부 라우팅이 **가능하지 않으며 외부 계정이 그에 따라 비활성화되었습니다.**

## 메시지 센터 아키텍처{#transac-msg-archi}

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

[!DNL :bulb:]  [이 섹션](../send/transactional.md)에서 트랜잭션 메시지를 보내는 방법을 알아봅니다.

웹 사이트에서 고객이 수행한 작업에 대한 응답으로, 이벤트는 REST API를 통해 Campaign으로 전송되고, 메시지 템플릿에는 API 호출을 통해 제공된 정보 또는 데이터가 채워지고, 트랜잭션 메시지는 실시간으로 고객에게 전송됩니다. 이러한 메시지는 개별적으로 또는 이메일, SMS 또는 푸시 알림을 통해 일괄적으로 전송할 수 있습니다.

이 특정 아키텍처에서는 실행 셀이 제어 인스턴스와 분리되어 고가용성과 로드 관리를 보장합니다.

* **컨트롤 인스턴스**(또는 마케팅 인스턴스)는 마케터와 IT 팀이 메시지 템플릿을 만들고, 구성하고, 게시하기 위해 사용합니다. 또한 이 인스턴스는 이벤트 모니터링 및 기록을 중앙 집중화합니다.

   [!DNL :bulb:]  [이 섹션](../send/transactional.md)에서 메시지 템플릿을 만들고 게시하는 방법을 알아봅니다.

* **실행 인스턴스**&#x200B;는 들어오는 이벤트(예를 들어, 웹 사이트의 암호 재설정 또는 주문)를 검색하고 개인화된 메시지를 보냅니다. 로드 밸런서를 통해 메시지를 처리하고 최대 가용성을 위해 진행할 이벤트 수의 크기를 조정하는 실행 인스턴스가 두 개 이상 있을 수 있습니다.

>[!CAUTION]
>
>제어 인스턴스와 실행 인스턴스는 다른 컴퓨터에 설치해야 합니다. 동일한 Campaign 인스턴스를 공유할 수 없습니다.

![](assets/messagecenter_diagram.png)

### 인증

이러한 기능을 사용하려면 Adobe Campaign 사용자가 제어 인스턴스에 로그인하여 트랜잭션 메시지 템플릿을 만들고, 시드 목록을 사용하여 메시지 미리 보기를 생성하고, 보고서를 표시하고 실행 인스턴스를 모니터링합니다.

* 단일 실행 인스턴스
Adobe 호스팅 메시지 센터 실행 인스턴스와 상호 작용할 때, 외부 시스템은 제공된 계정 로그인 및 암호를 사용하여 세션 로그온 메서드에 api를 호출하여 세션 토큰(기본적으로 24시간 후에 만료)을 먼저 검색할 수 있습니다.
그런 다음 위의 호출에 대한 응답으로 실행 인스턴스에서 제공하는 sessionToken 을 사용하면 외부 애플리케이션이 각 SOAP 호출에 계정 로그인 및 암호를 포함하지 않고 통신을 보내기 위해 SOAP api 호출(rtEvents 또는 batchEvents)을 수행할 수 있습니다.

* 여러 실행 인스턴스
로드 밸런서 뒤에 여러 실행 인스턴스가 있는 다중 셀 실행 아키텍처에서 외부 응용 프로그램에서 호출하는 로그온 방법이 로드 밸런서를 통해 수행됩니다.따라서 토큰 기반 인증을 사용할 수 없습니다. 사용자/암호 기반 인증이 필요합니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 트랜잭션 메시지 이벤트에 대해 자세히 알아보십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)