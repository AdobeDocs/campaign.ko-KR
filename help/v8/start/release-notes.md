---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 28%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 최신 Campaign v8 릴리스(콘솔)의 최신 릴리스와 함께 새로운 기능, 개선 및 수정 사항이 나와 있습니다. [이 페이지](upgrades.md)에서 Campaign 릴리스와 버전, 업그레이드에 대해 자세히 알아보십시오.

## 릴리스 8.6.4 {#release-8-6-4}

_2025년 1월 15일_


### 일반 개선 사항 {#improvements-8-6-4}

* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)의 컨텍스트에서 게재 분석 중에 캠페인 응용 프로그램 안정성이 향상되었습니다.
* 이 릴리스에는 주요 관리, 스테이징 및 데이터 복제를 비롯한 향상된 FFDA 아키텍처 메커니즘이 함께 제공됩니다.
* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에 새로운 기술 워크플로우가 도입되었습니다. 이러한 워크플로우는 해당 테이블에 병렬 복제 요청을 중앙에서 관리하여 게재 및 관련 데이터를 복제합니다. 이 워크플로는 `Replicate nms`(으)로 시작합니다.
* 이제 워크플로 속성에서 **워크플로를 영구적으로 실행할 수 있도록 감시장치 감독자를 활성화** 옵션을 사용할 수 있습니다. 이 옵션을 활성화하면 오류가 발생한 후 워크플로가 자동으로 다시 시작됩니다. 기본적으로 30초마다 다시 시작됩니다. 이 간격을 조정하려면 새 `XtkWorkflow_WatchdogTimerTimeout` 옵션을 만들고 Integer 데이터 형식을 설정하여 새 지연을 지정할 수 있습니다. 이 옵션은 기술 워크플로우에서만 활성화해야 합니다.

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