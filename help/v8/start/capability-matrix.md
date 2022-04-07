---
title: Campaign Classic v7 - Campaign v8 기능 매트릭스
description: Campaign Classic v7과 Campaign v8 간의 차이점 이해
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 98%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 기능{#gs-matrix}

기존 [!DNL Campaign Classic] v7 사용자라면 [!DNL Adobe Campaign]과의 상호 작용 방식을 크게 바꿀 필요가 없습니다. v8의 변경 사항 대부분은 UI 및 구성 단계에 나타나는 작은 변경 사항을 제외하고는 사용자에게 표시되지 않습니다.

주요 변경 사항:

* 최대 200배 더 빠르게 세그먼트 만들기
* 게재 속도 향상
* 실시간 보고 (Cubes 사용)

[!DNL Campaign Classic] 사용자는 [!DNL Campaign Classic] v7 기능 중 대부분을 [!DNL Campaign] v8에서도 사용할 수 있습니다(일부 예외: [이 섹션](#gs-removed) 참조). 다른 기능은 향후 릴리스에서 제공될 예정입니다. [이 섹션에서 자세히 알아보기](#gs-unavailable-features)

![](../assets/do-not-localize/glass.png) [!DNL Campaign] v8 아키텍처에 대한 자세한 내용은 [이 페이지](../dev/architecture.md)를 참조하세요.

## 제품 구성 변경 사항

### [!DNL Campaign] 및 [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8은 두 개의 데이터베이스를 사용합니다. 하나는 사용자 인터페이스 실시간 메시지 보내기와 API를 통한 단일 쿼리 및 쓰기를 위한 로컬 데이터베이스이고, 다른 하나는 캠페인 실행, 쿼리 일괄 처리 및 워크플로우 실행을 위한 클라우드 데이터베이스입니다.

소프트웨어 아키텍처의 근본적인 변화입니다. 이제 데이터는 원격지에 있으며 Campaign은 프로필을 포함한 전체 데이터를 통합합니다. 이제 [!DNL Campaign] 프로세스가 타기팅에서 메시지 실행에 이르기까지 전체 프로세스를 확장합니다. 데이터 수집, 세분화, 타기팅, 쿼리, 게재는 이제 일반적으로 몇 분 내에 실행됩니다. 이 새로운 버전은 동일한 수준의 유연성과 확장성을 유지하면서 크기를 조절해야 하는 문제 전체를 해결합니다. 프로필 수는 거의 제한이 없으며 데이터 유지율을 확장할 수 있습니다.

클라우드 스토리지는 **[!DNL Snowflake]**&#x200B;에서 수행됩니다. Snowflake는 새로운 기본 제공 **외부 계정**&#x200B;으로 클라우드 데이터베이스와의 연결을 보장합니다. 이는 Adobe에서 구성하며 수정해서는 안 됩니다. [자세히 알아보기](../config/external-accounts.md)

클라우드 데이터베이스에서 이동하거나 복제해야 하는 내장 스키마/테이블은 **xxl** 네임스페이스 아래에 내장된 스키마 확장과 함께 제공됩니다. 이 확장에는 내장된 스키마를 [!DNL Campaign] 로컬 데이터베이스에서 [!DNL Snowflake] 클라우드 데이터베이스로 이동하고 그에 따라 새로운 UUID, 업데이트된 링크 등 해당 구조를 조정하는 데 필요한 수정 사항이 모두 포함됩니다.

>[!CAUTION]
>
> 고객 데이터는 [!DNL Campaign] 로컬 데이터베이스에 저장되지 않습니다. 따라서 모든 사용자 정의 테이블을 클라우드 데이터베이스에서 만들어야 합니다.

로컬 및 클라우드 데이터베이스 간에 데이터를 관리하는 데 특정 API를 사용할 수 있습니다. [이 페이지](../dev/new-apis.md)에서는 이 새로운 API의 작동 방식과 사용법을 알아봅니다.

### 데이터 복제

특정 기술 워크플로우는 양쪽(Campaign 로컬 데이터베이스와 클라우드 데이터베이스)에 모두 표시되어야 하는 테이블 복제를 처리합니다. 이 워크플로우는 매 시간마다 트리거되며 새로운 내장 JavaScript 라이브러리를 사용합니다.

>[!NOTE]
>
> 테이블 크기(XS, XL 등)에 따라 여러 복제 정책이 생성되었습니다.
> 일부 테이블은 실시간으로 복제되고 다른 테이블은 시간별로 복제됩니다. 일부 테이블에는 증분 업데이트가 적용되고 다른 테이블에는 전체 업데이트가 적용됩니다.

[데이터 복제 자세히 알아보기](../config/replication.md)

### ID 관리

이제 Campaign v8 개체에는 데이터를 식별하는 데 제한 없는 고유 값을 사용할 수 있는 **UUID(범용 고유 ID)**&#x200B;가 사용됩니다.

이 ID는 문자열 기반이며 순차적이 아님에 유의하세요. 기본 키는 Campaign v8에서 숫자 값이 아니므로 스키마에서 **autouid** 및 **autok** 속성을 사용해야 합니다.

Campaign Classic v7 및 이전 버전에서 스키마(즉 테이블) 내의 키 독자성은 데이터베이스 엔진 수준에서 처리됩니다. 일반적으로 PostgreSQL, Oracle 또는 SQL Server와 같은 클래식 데이터베이스 엔진에는 기본 키 및/또는 고유 인덱스를 통해 열 또는 열 세트를 기반으로 중복 행 삽입을 방지하는 기본 메커니즘이 포함되어 있습니다. 이 버전에서는 데이터베이스 수준에서 적절한 인덱스 및 기본 키를 설정한 경우 중복 ID가 존재하지 않습니다.

Adobe Campaign v8에는 핵심 데이터베이스로 Snowflake이 포함되어 있습니다. 쿼리 크기가 크게 증가함에 따라 Snowflake 데이터베이스의 분산 아키텍처는 이와 같이 테이블 내에서 키 독자성을 관리하는 메커니즘을 제공하지 않습니다. 따라서 Adobe Campaign v8에서는 테이블에서 중복 키를 수집하는 것을 방지하는 장치가 없습니다. 이제 Adobe Campaign 데이터베이스 내의 키 독자성을 유지할 책임은 최종 사용자에게 있습니다. [자세히 알아보기](../dev/keys.md)

### 유지 관리 간소화

Campaign 사용자는 데이터베이스 전문가가 될 필요가 없습니다. 더 이상 복잡한 데이터베이스 유지 관리 작업이나 복잡한 테이블 인덱싱을 수행할 필요가 없습니다.

## Campaign에 연결

Campaign 사용자는 Adobe ID을 통해 연결합니다. 동일한 Adobe ID을 사용하여 모든 Adobe 계획 및 제품을 단일 계정과 연결된 상태로 유지합니다.

![](../assets/do-not-localize/glass.png) [!DNL Campaign]에 연결하는 방법은 [이 페이지](connect.md)를 참조하세요.

## 보고

Adobe Campaign 보고서는 최적화되어 있으며 Campaign Classic v7보다 더 나은 확장 기능을 제공합니다. 큐브에 대한 제한 사항은 적용되지 않습니다.

## 워크플로우 {#workflow}

Campaign v8에서는 추가적인 타겟팅 워크플로우 활동으로 **[!UICONTROL Change data source]**&#x200B;를 제공합니다.

**[!UICONTROL Change data source]** 활동을 사용하면 워크플로우의 데이터 소스 **[!UICONTROL Working table]**&#x200B;을 변경하여 FDA, FFDA 및 로컬 데이터베이스와 같은 다양한 데이터 소스에 걸쳐 데이터를 관리할 수 있습니다.

![](../assets/do-not-localize/glass.png) **[!UICONTROL Change data source]** 활동에 대한 자세한 내용은 [이 페이지](../config/workflows.md#change-data-source-activity)를 참조하세요.

## 사용할 수 없는 기능{#gs-unavailable-features}

다음과 같은 일부 기능은 이 버전에서 아직 사용할 수 없습니다.

* 마케팅 리소스 관리
* 분산 마케팅
* 반응 관리자
* 하이브리드/온-프레미스 배포 모델

>[!CAUTION]
>
>* 현재 Campaign v8은 관리 클라우드 서비스로&#x200B;**만** 사용할 수 있으며, 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.
>
>* 기존 Campaign Classic v7 환경에서의 마이그레이션은 아직 불가능합니다.
>
>* 가지고 있는 배포 모델을 잘 모르거나 질문이 있는 경우 계정 팀에 문의해 주세요.


## 지원되지 않는 기능{#gs-removed}

Campaign v8의 새로운 아키텍처 및 배포 모델에 맞게 이전 Campaign Classic v7의 일부 기능은 Campaign v8에서 더 이상 사용할 수 없습니다:

* 쿠폰
* 웹 추적
* 설문 조사
* 소셜 마케팅 Facebook
* ACS 커넥터(프라임 제공)
* LDAP와 통합
* 사용자/암호 로그인

>[!NOTE]
>
>사용할 수 없거나 제거된 기능 중 일부는 계속 사용자 인터페이스에 표시됩니다.
