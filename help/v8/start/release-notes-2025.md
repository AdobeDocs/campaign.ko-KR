---
title: Campaign v8(콘솔) 2025 릴리스 정보
description: 2025 Campaign v8 릴리스의 기능 및 개선 사항 목록
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 96%

---

# 2025 릴리스 정보 {#2025-rn}

이 페이지에는 **2025 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 해결 사항이 나와 있습니다. 최신 릴리스는 [이 페이지](release-notes.md)를 참조하세요.

새 구현이나 기존 환경으로 업그레이드하려면 [최신 릴리스](release-notes.md)를 설치하십시오.

>[!BEGINSHADEBOX]

**이 페이지의 내용**

* [릴리스 8.6.5](#release-8-6-5)
* [릴리스 8.6.4](#release-8-6-4)
* [릴리스 8.7.4](#release-8-7-4)
* [릴리스 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## 릴리스 8.6.5 {#release-8-6-5}

_2025년 4월 25일_

>[!AVAILABILITY]
>
>이 릴리스는 **LA(제한 공개)** 상태입니다. 

### 새로운 기능 {#features-8-6-5}

**새로운 SMS 전송 커넥터** - SMS 전송 커넥터가 최신화되고 개선되었습니다. 송수신기 모드 SMPP 연결 및 영구 SMPP 연결을 사용할 수 있으며 Adobe Campaign Standard에서 전환할 때 환경에 대해 보다 나은 호환성을 보장합니다. 이제 모든 새 SMS 구현에 새 SMS 외부 계정을 사용할 수 있습니다. 기존 구현도 여전히 지원하지만 새롭게 확장된 최신형 커넥터로 옮기는 것을 권장합니다. [자세히 보기](../send/sms/sms.md).

### 일반 개선 사항 {#improvements-8-6-5}

* 엔터프라이즈(FFDA) 배포 환경에서 게재 증명 전송 및 데이터베이스 정리를 포함하여 애플리케이션의 전역 성능이 개선되었습니다.

* 애플리케이션 간 모든 통신에 대한 보안을 강화하기 위해 이제 외부 API 호출에도 mTLS를 지원합니다.

* 메일 전송 에이전트(MTA) - 분리된 MTA 하위 요소가 **[!UICONTROL Start pending]** 상태에서 중단되는 문제를 해결했습니다.

### 해결 사항 {#fixes-8-6-5}

이 릴리스에서는 다음 문제도 해결합니다.

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## 릴리스 8.7.4 {#release-8-7-4}

_2025년 4월 10일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}에서 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#features-8-7-4}

* **SMS REST API 지원** - 이제 SMS 채널에서 트랜잭션 메시지 REST API를 사용할 수 있습니다. 페이로드에 이메일과 휴대폰이 모두 있는 경우 “wishedChannel” 필드를 사용하여 채널을 지정할 수 있습니다. 제공되지 않으면 wishedChannel에서 SMS를 명시적으로 요청하지 않는 한 기본적으로 이메일이 사용됩니다. 

* **다국어 게재** - Campaign Web 사용자 인터페이스 4월 릴리스부터 다양한 언어로 여러 이메일 게재를 보내고 관련 동적 보고서에 액세스할 수 있습니다. 이 기능은 4월 말 Adobe Campaign Web 사용자 인터페이스에서만 사용할 수 있으며 서버를 Campaign v8.7.4로 업데이트해야 합니다.

### 해결 사항 {#fixes-8-7-4}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-80245, NEO-83559

## 릴리스 8.7.3 {#release-8-7-3}

_2025년 2월 14일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}에서 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#features-8-7-3}

* **트랜잭션 메시지에 대한 Dynamic Reporting** - 이제 Dynamic Reporting 사용자 인터페이스에서 트랜잭션 메시지를 모니터링할 수 있습니다. 이러한 보고서는 마케터가 템플릿을 통해 실시간으로 전송된 게재 분류와 트랜잭션 메시지의 모든 보고 지표와 차원을 볼 수 있는 기능을 제공합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=ko){target="_blank"}

* **트랜잭션 메시지 REST API** - 이벤트 기반 트랜잭션 API를 이제 이메일에 사용할 수 있습니다. [자세히 알아보기](../dev/api/get-started-apis.md)

### 해결 사항 {#fixes-8-7-3}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-79373, NEO-81908, NEO-83081

## 릴리스 8.6.4 {#release-8-6-4}

_2025년 1월 15일_

### 일반 개선 사항 {#improvements-8-6-4}

* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md) 컨텍스트에서 게재 분석 중에 캠페인 애플리케이션 안정성이 향상되었습니다.
* 이 릴리스에는 주요 관리, 스테이징 및 데이터 복제를 비롯한 향상된 FFDA 아키텍처 메커니즘이 함께 제공됩니다.
* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에 새로운 기술 워크플로가 도입되었습니다. 이러한 워크플로는 병렬 복제 요청을 해당 테이블에 중앙 집중화하여 게재와 관련 데이터를 복제합니다. 이 워크플로는 `Replicate nms`(으)로 시작합니다. [자세히 알아보기](../architecture/replication.md)
* 이제 새로운 **워크플로를 영구적으로 실행할 수 있도록 워치도그 감독자 활성화** 옵션을 워크플로 속성에서 사용할 수 있습니다. 이 옵션을 활성화하면 오류가 발생한 후 워크플로가 자동으로 다시 시작됩니다. 워크플로에 여전히 오류가 있는 경우 기본적으로 30초마다 다시 시작됩니다. 이 간격을 조정하려면 새 `XtkWorkflow_WatchdogRestartTimerTimeout` 옵션을 만들고 Integer 데이터 유형을 설정하여 새 지연을 지정하면 됩니다. 이 옵션은 기술 워크플로에서만 활성화해야 합니다. [자세히 알아보기](../../automation/workflow/workflow-properties.md#execution)

### 보안 개선 사항 {#security-8-6-4}

보안을 강화하기 위해 **[!UICONTROL Adobe Experience Cloud]** 외부 계정을 통한 Adobe 솔루션 및 앱 연결을 업데이트했습니다.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 호환성 업데이트 {#comp-8-6-4}

다음 FDA 커넥터가 추가되었습니다. 이 [페이지](compatibility-matrix.md#FederatedDataAccessFDA)를 참조하세요.

* 이제 Databricks는 Adobe Campaign 페더레이션 데이터 액세스(FDA)를 통해 외부 데이터베이스로 지원됩니다. 

* 이제 새로운 Amazon Redshift FDA ODBC 커넥터를 사용할 수 있습니다. 개선된 연결성, 쉬운 유지 관리 및 향상된 호환성을 제공합니다. 이 신규 버전에는 다음과 같은 개선 사항이 포함되어 있습니다.

   * 새 커넥터는 최신 FDA 커넥터에 맞는 ODBC 인터페이스를 기반으로 합니다. 이를 통해 장기적인 지원이 보장됩니다.
   * 또한 s3 버킷을 사용하는 새로운 데이터 로드 메커니즘을 도입하여 성능이 크게 향상되었습니다.

  레거시 커넥터는 계속 사용할 수 있습니다. 새로운 기능을 사용해 보려면 Adobe 담당자에게 문의하세요.

### 해결 사항 {#fixes-8-6-4}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

