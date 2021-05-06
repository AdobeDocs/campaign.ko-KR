---
solution: Campaign Classic
product: campaign
title: 캠페인 아키텍처 시작하기
description: 캠페인 아키텍처 시작하기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
translation-type: tm+mt
source-git-commit: cd6691fc04999927c5c50fecfb03cac6139729df
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# 캠페인 아키텍처 시작하기{#gs-ac-archi}

## 환경

캠페인은 전체 캠페인 환경을 나타내는 각 인스턴스에서 개별 인스턴스로 사용할 수 있습니다.

캠페인 Cloud Service에서 사용할 수 있는 세 가지 환경:

* 제작 환경:비즈니스 전문가를 위한 애플리케이션을 호스팅합니다.

* 스테이지 환경:애플리케이션 변경 사항이 프로덕션 환경에 푸시되기 전에 다양한 성능 및 품질 테스트에 사용됩니다.

* 개발 환경:개발자는 단계 및 프로덕션 환경과 동일한 런타임 조건 하에 Campaign을 구현할 수 있습니다.

한 환경에서 다른 환경으로 패키지를 내보내고 가져올 수 있습니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=en#about-data-packages)의 패키지에 대한 자세한 내용

## 중간 소싱 배포{#mid-sourcing-deployment}

서버와 프로세스 간의 일반적인 통신은 다음 스키마에 따라 수행됩니다.

![](assets/architecture.png)

* 인스턴스에서 실행 및 바운스 관리 모듈을 사용할 수 없습니다.

* 응용 프로그램은 SOAP 호출(HTTP 또는 HTTPS를 통해)을 사용하여 구동되는 원격 &quot;mid-sources&quot; 서버에서 메시지 실행을 수행하도록 구성됩니다.

>[!NOTE]
>
> 캠페인 v8은 하이브리드 아키텍처에 의존합니다. Campaign Classic v7에서 전환하는 경우 모든 배달이 mid-sourcing 서버를 통과한다는 점을 참고하십시오.
> 그 결과, 내부 라우팅은 Campaign v8에서 **이(가)**&#x200B;될 수 없으며 이에 따라 외부 계정이 비활성화되었습니다.


## 메시지 센터 아키텍처{#transac-msg-archi}

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

: 전구:[이 섹션](../send/transactional.md)에서 트랜잭션 메시지를 보내는 방법을 알아봅니다.

웹 사이트에서 고객의 행동에 대한 응답으로, 이벤트는 REST API를 통해 Campaign으로 전송되고, 메시지 템플릿은 API 호출을 통해 제공된 정보 또는 데이터로 채워지며, 거래 메시지는 실시간으로 고객에게 전송됩니다. 이러한 메시지는 이메일, SMS 또는 푸시 알림을 통해 개별적으로 또는 일괄적으로 보낼 수 있습니다.

이 특정 아키텍처에서는 실행 셀이 제어 인스턴스와 분리되어 고가용성 및 로드 관리를 보장합니다.

* **Control 인스턴스**(또는 Marketing 인스턴스)는 마케터와 IT 팀이 메시지 템플릿을 만들고 구성하고 게시하기 위해 사용합니다. 또한 이 인스턴스는 이벤트 모니터링과 기록을 중앙에서 관리합니다.

   :arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/introduction.html?lang=en#transactional-messaging)에서 메시지 템플릿을 만들고 게시하는 방법에 대해 알아봅니다.

* **실행 인스턴스**&#x200B;는 들어오는 이벤트(예: 암호 재설정 또는 웹 사이트의 주문)를 검색하고 개인화된 메시지를 전송합니다. 부하 균형 조정기를 통해 메시지를 처리할 실행 인스턴스가 두 개 이상 있을 수 있으며 최대 가용성을 위해 진행할 이벤트 수의 크기를 조정할 수 있습니다.

>[!CAUTION]
>
>제어 인스턴스와 실행 인스턴스를 다른 컴퓨터에 설치해야 합니다. 동일한 캠페인 인스턴스를 공유할 수 없습니다.

![](assets/messagecenter_diagram.png)

:arrow_upper_right:메시지 센터 아키텍처는 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)에 설명되어 있습니다.


### 인증

이러한 기능을 사용하려면 Adobe Campaign 사용자가 제어 인스턴스에 로그인하여 트랜잭션 메시지 템플릿을 만들고, 시드 목록을 사용하여 메시지 미리 보기를 생성하고, 보고서를 표시하고 실행 인스턴스를 모니터링합니다.

* 단일 실행 인스턴스
Adobe 호스팅 Message Center 실행 인스턴스와 상호 작용할 때 외부 시스템은 제공된 계정 로그인 및 암호를 사용하여 세션 로그온 메서드에 api를 호출하여 세션 토큰을 먼저 검색합니다(기본적으로 24시간 후에 만료).
그런 다음, 위의 호출에 대한 응답으로 실행 인스턴스에서 제공하는 sessionToken을 사용하면 외부 응용 프로그램에서 SOAP api 호출(rtEvents 또는 batchEvents)을 수행하여 통신을 전송할 수 있습니다. 이때 각 SOAP 호출에서 계정 로그인 및 암호를 호출하지 않아도 됩니다.

* 다중 실행 인스턴스
부하 균형 조정기 뒤에 여러 실행 인스턴스가 있는 다중 셀 실행 아키텍처에서 외부 응용 프로그램에서 호출한 로그온 방법이 부하 균형 조정기를 거칩니다.따라서 토큰 기반 인증을 사용할 수 없습니다. 사용자/암호 기반 인증이 필요합니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)의 트랜잭션 메시지 이벤트에 대한 자세한 내용