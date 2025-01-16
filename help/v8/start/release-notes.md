---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b83222774b026348ae70f41a8193f88856af99a9
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 55%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 Campaign v8(콘솔) **최신 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. [이 페이지](upgrades.md)에서 Campaign 릴리스, 버전 및 업그레이드에 대해 자세히 알아보세요. 다른 릴리스는 이 설명서의 이전 릴리스 섹션에 나열되어 있습니다.

## 릴리스 8.6.4 {#release-8-6-4}

_2025년 1월 15일_

### 일반 개선 사항 {#improvements-8-6-4}

* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)의 컨텍스트에서 게재 분석 중에 캠페인 응용 프로그램 안정성이 향상되었습니다.
* 이 릴리스에는 주요 관리, 스테이징 및 데이터 복제를 비롯한 향상된 FFDA 아키텍처 메커니즘이 함께 제공됩니다.
* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에 새로운 기술 워크플로우가 도입되었습니다. 이러한 워크플로우는 해당 테이블에 병렬 복제 요청을 중앙에서 관리하여 게재 및 관련 데이터를 복제합니다. 이 워크플로는 `Replicate nms`(으)로 시작합니다.
* 이제 워크플로 속성에서 **워크플로를 영구적으로 실행할 수 있도록 감시장치 감독자를 활성화** 옵션을 사용할 수 있습니다. 이 옵션을 활성화하면 오류가 발생한 후 워크플로가 자동으로 다시 시작됩니다. 워크플로우가 여전히 오류인 경우 기본적으로 30초마다 다시 시작됩니다. 이 간격을 조정하려면 새 `XtkWorkflow_WatchdogTimerTimeout` 옵션을 만들고 Integer 데이터 형식을 설정하여 새 지연을 지정할 수 있습니다. 이 옵션은 기술 워크플로우에서만 활성화해야 합니다. [자세히 알아보기](../../automation/workflow/workflow-properties.md#execution)

### 보안 개선 사항 {#security-8-6-4}

보안을 강화하기 위해 **[!UICONTROL Adobe Experience Cloud]** 외부 계정을 통해 Adobe 솔루션 및 앱과의 연결이 업데이트되었습니다.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 호환성 업데이트 {#comp-8-6-4}

이제 Databricks는 Adobe Campaign FDA(Federated Data Access)를 통해 외부 데이터베이스로 지원됩니다. [이 페이지](compatibility-matrix.md#FederatedDataAccessFDA)에서 자세히 알아보십시오.

### 수정 사항 {#fixes-8-6-4}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704 83096 83081.

## 릴리스 8.7.2 {#release-8-7-2}

_2024년 9월 3일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}를 통해 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#new-8-7-2}

* **새로운 SMS 전송 커넥터** - SMS 전송 커넥터가 최신화되고 개선되었습니다. 송수신기 모드 SMPP 연결 및 영구 SMPP 연결을 사용할 수 있으며 Adobe Campaign Standard에서 전환할 때 환경에 대해 보다 나은 호환성을 보장합니다. 이제 모든 새 SMS 구현에 새 SMS 외부 계정을 사용할 수 있습니다. 기존 구현도 여전히 지원하지만 새롭게 확장된 최신형 커넥터로 옮기는 것을 권장합니다. [자세히 보기](../send/sms/sms.md).

* **리치 푸시 알림(GA)** - 이제 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이번 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림을 위한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push-android.md).

* **브랜딩** - 이제 SMS 및 다이렉트 메일을 포함한 모든 채널에서 브랜딩 옵션을 사용할 수 있습니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}

### 수정 사항 {#fixes-8-7-2}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.