---
solution: Campaign v8
product: Adobe Campaign
title: Campaign Classic v7 - Campaign v8 기능 매트릭스
description: Campaign Classic v7와 Campaign v8 간의 차이점 이해
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 2%

---

# [!DNL Campaign Classic] v7 -  [!DNL Campaign] v8 기능{#gs-matrix}

기존 [!DNL Campaign Classic] v7 사용자는 일반적으로 [!DNL Adobe Campaign]과 상호 작용하는 방식으로 큰 중단을 예상해서는 안 됩니다. v8의 대부분의 변경 사항은 UI와 구성 단계에 표시된 작은 변경 사항을 제외하고 표시되지 않습니다.

주요 변경 사항:

* 세그먼트를 최대 200배 더 빠르게 생성
* 게재 속도 향상
* 큐브를 사용한 실시간 보고

[!DNL Campaign Classic] 사용자는 [!DNL Campaign Classic] v7 기능 중 대부분 [!DNL Campaign] v8에서 사용할 수 있으며, 단, [이 섹션](#gs-removed)에 나열된 작은 기능 세트를 제외합니다. 다른 항목은 향후 릴리스에 제공될 예정입니다. [자세한 내용은 이 섹션에서 확인하십시오](#gs-unavailable-features)

:[이 페이지](../dev/architecture.md)에서 [!DNL Campaign] v8 아키텍처에 대해 자세히 알아보십시오.

## 제품 구성 변경 사항

### [!DNL Campaign] 및  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8은 두 개의 데이터베이스에서 작동합니다.API를 통해 실시간 메시징 및 단일 쿼리 및 쓰기를 위한 사용자 인터페이스의 로컬 데이터베이스, 캠페인 실행, 배치 쿼리 및 워크플로우 실행을 위한 클라우드 데이터베이스.

소프트웨어 아키텍처의 근본적인 변화입니다. 이제 데이터는 원격이며 Campaign은 프로필을 포함하여 전체 데이터를 통합합니다. [!DNL Campaign] 이제 프로세스는 타깃팅에서 메시지 실행까지 일괄적으로 확장됩니다.이제 데이터 수집, 세그먼테이션, 타깃팅, 쿼리, 게재 기능은 일반적으로 분 단위로 실행됩니다. 이 새로운 버전은 동일한 수준의 유연성과 확장성을 유지하면서 전체적인 확장 문제를 해결합니다. 프로필 수는 거의 무제한으로 데이터 보존 기간을 연장할 수 있습니다.

클라우드 스토리지는 **[!DNL Snowflake]**&#x200B;에서 수행됩니다.새로 내장된 **외부 계정**&#x200B;은(는) 클라우드 데이터베이스와의 연결을 보장합니다. Adobe에 의해 구성되므로 수정해서는 안 됩니다. [자세히 알아보기](../config/external-accounts.md)

클라우드 데이터베이스에서 이동하거나 복제해야 하는 기본 제공 스키마/테이블에는 **xxl** 네임스페이스 아래에 내장 스키마 확장이 있습니다. 이러한 확장에는 기본 제공 스키마를 [!DNL Campaign] 로컬 데이터베이스에서 [!DNL Snowflake] Cloud 데이터베이스로 이동하고 그에 따라 구조를 조정하는 데 필요한 수정 사항이 포함되어 있습니다.새로운 UUID, 업데이트된 링크 등

>[!CAUTION]
>
> 고객 데이터가 로컬 [!DNL Campaign] 데이터베이스에 저장되지 않습니다. 따라서 클라우드 데이터베이스에서 모든 사용자 지정 테이블을 만들어야 합니다.


특정 API는 로컬 및 클라우드 데이터베이스 간의 데이터를 관리하는 데 사용할 수 있습니다. 이러한 새 API가 작동하는 방식과 [이 페이지](../dev/new-apis.md)에서 사용하는 방법을 알아봅니다.

### 데이터 복제

특정 기술 워크플로우는 양쪽에 있어야 하는 테이블(Campaign 로컬 데이터베이스 및 클라우드 데이터베이스) 복제를 처리합니다. 이 워크플로우는 매시간마다 트리거되며, 새로운 내장된 JavaScript 라이브러리를 사용합니다.

>[!NOTE]
>
> 테이블 크기(XS, XL 등)를 기준으로 여러 복제 정책이 작성되었습니다.
> 일부 테이블은 실시간으로 복제되고 다른 테이블은 시간별로 복제됩니다. 일부 테이블에는 증분 업데이트가 있고 다른 테이블에는 전체 업데이트가 있습니다.


[데이터 복제에 대해 자세히 알아보기](../config/replication.md)

### ID 관리

이제 Campaign v8 개체는 **Universally Unique ID(UUID)**&#x200B;를 사용하므로 고유한 값을 무제한으로 확인하여 데이터를 식별할 수 있습니다

이 ID는 문자열 기반이며 순차적이지 않습니다.

### 간편한 유지 관리

Campaign 사용자는 데이터베이스 전문가가 될 필요가 없습니다.더 이상 복잡한 데이터베이스 유지 관리 작업이나 복잡한 테이블 색인화가 필요하지 않습니다.

## 일시적으로 사용할 수 없는 기능{#gs-unavailable-features}

일부 기능은 다음과 같이 이 첫 번째 버전에서 아직 사용할 수 없습니다.

* 마케팅 리소스 관리
* 분산 마케팅
* 인바운드 오퍼 관리(상호 작용 모듈)
* 캠페인 최적화
* 반응 관리자
* 하이브리드/온-프레미스 배포 모델

## 제거된 기능{#gs-removed}

Campaign v8의 새로운 아키텍처 및 배포 모델에 맞춰 일부 이전 Campaign Classic v7 기능을 Campaign v8에서 더 이상 사용할 수 없습니다.

* 쿠폰
* 웹 추적
* 설문 조사
* 소셜 마케팅
* ACS 커넥터(Prime Offering)

