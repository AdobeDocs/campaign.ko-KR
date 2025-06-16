---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 9187ac7fd0d17a6dc28c3b6564913bcd93e45943
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 35%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 Campaign v8(콘솔) **최신 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. [이 페이지](upgrades.md)에서 Campaign 릴리스, 버전 및 업그레이드에 대해 자세히 알아보세요. 다른 릴리스는 이 설명서의 이전 릴리스 섹션에 나열되어 있습니다.

>[!BEGINSHADEBOX]

**이 페이지에서**

* [릴리스 8.6.5](#release-8-6-5)
* [릴리스 8.7.4](#release-8-7-4)
* [릴리스 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## 릴리스 8.6.5 {#release-8-6-5}

_2025년 4월 25일 토요일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한된 가용성**(LA)에 있습니다.

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

_2025년 4월 10일 금요일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign Standard 사용자가 Campaign v8로 전환하는 경우 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}에서 이 전환에 대해 자세히 알아보세요.

### 새로운 기능 {#features-8-7-4}

* **SMS REST API 지원** - 이제 SMS 채널에 트랜잭션 메시지 REST API를 사용할 수 있습니다. 페이로드에 이메일과 휴대폰이 모두 있는 경우 “wishedChannel” 필드를 사용하여 채널을 지정할 수 있습니다. 제공하지 않을 경우 wiredChannel이 명시적으로 SMS를 요청하지 않는 한 이메일이 기본적으로 사용됩니다.

* **다국어 게재** - Campaign 웹 사용자 인터페이스 4월 릴리스를 시작하면 여러 언어로 여러 이메일 게재를 보내고 관련 동적 보고서에 액세스할 수 있습니다. 이 기능은 4월 말에 Adobe Campaign 웹 사용자 인터페이스에서만 사용할 수 있으며 Campaign v8.7.4로 서버를 업데이트해야 합니다.

### 수정 사항 {#fixes-8-7-4}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-80245, NEO-83559

## 릴리스 8.6.4 {#release-8-6-4}

_2025년 1월 15일_

### 일반 개선 사항 {#improvements-8-6-4}

* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)의 컨텍스트에서 게재 분석 중에 캠페인 응용 프로그램 안정성이 향상되었습니다.
* 이 릴리스에는 주요 관리, 스테이징 및 데이터 복제를 비롯한 향상된 FFDA 아키텍처 메커니즘이 함께 제공됩니다.
* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에 새로운 기술 워크플로우가 도입되었습니다. 이러한 워크플로우는 해당 테이블에 병렬 복제 요청을 중앙에서 관리하여 게재 및 관련 데이터를 복제합니다. 이 워크플로는 `Replicate nms`(으)로 시작합니다. [자세히 알아보기](../architecture/replication.md)
* 이제 워크플로 속성에서 **워크플로를 영구적으로 실행할 수 있도록 감시장치 감독자를 활성화** 옵션을 사용할 수 있습니다. 이 옵션을 활성화하면 오류가 발생한 후 워크플로가 자동으로 다시 시작됩니다. 워크플로우가 여전히 오류인 경우 기본적으로 30초마다 다시 시작됩니다. 이 간격을 조정하려면 새 `XtkWorkflow_WatchdogRestartTimerTimeout` 옵션을 만들고 Integer 데이터 형식을 설정하여 새 지연을 지정할 수 있습니다. 이 옵션은 기술 워크플로우에서만 활성화해야 합니다. [자세히 알아보기](../../automation/workflow/workflow-properties.md#execution)

### 보안 개선 사항 {#security-8-6-4}

보안을 강화하기 위해 **[!UICONTROL Adobe Experience Cloud]** 외부 계정을 통한 Adobe 솔루션 및 앱 연결을 업데이트했습니다.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 호환성 업데이트 {#comp-8-6-4}

다음 FDA 커넥터가 추가되었습니다. 이 [페이지](compatibility-matrix.md#FederatedDataAccessFDA)를 참조하세요.

* 이제 데이터 블록은 Adobe Campaign FDA(Federated Data Access)를 통해 외부 데이터베이스로 지원됩니다.

* 이제 새로운 Amazon Redshift FDA ODBC 커넥터를 사용할 수 있습니다. 향상된 연결성, 쉬운 유지 관리 및 향상된 호환성을 제공합니다. 이 새 버전은 다음과 같은 개선 사항을 제공합니다.

   * 새 커넥터는 최신 FDA 커넥터에 맞는 ODBC 인터페이스를 기반으로 합니다. 이를 통해 장기적인 지원이 보장됩니다.
   * 또한 s3 버킷을 사용하는 새로운 데이터 로드 메커니즘을 도입하여 성능이 크게 향상되었습니다.

  레거시 커넥터는 계속 사용할 수 있습니다. 새로운 기능을 사용해 보려면 Adobe 담당자에게 문의하십시오.

### 수정 사항 {#fixes-8-6-4}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640 82665 82781 82920 83081 83096 83137 83143.

