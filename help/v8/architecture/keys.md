---
title: Campaign의 키 관리
description: 키 관리 시작
feature: FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---

# 키 관리 및 독자성 {#key-management}

의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](enterprise-deployment.md)기본 키는 문자열에서 가져오는 UUID(Universally Unique IDentifier)입니다. 이 UUID를 만들려면 스키마의 기본 요소에 **autouid** 및 **자동** 으로 설정된 속성 **true**.

Adobe Campaign v8의 사용 [!DNL Snowflake] 를 핵심 데이터베이스로 설정합니다. EMC의 [!DNL Snowflake] 데이터베이스에서는 테이블 내의 키가 일반적이지 않도록 하는 메커니즘을 제공하지 않습니다. 최종 사용자는 Adobe Campaign 데이터베이스 내의 키 일관성을 책임집니다.

관계형 데이터베이스 일관성을 유지하려면 키에 대한 중복 방지, 특히 기본 키에 대한 중복을 방지해야 합니다. 기본 키에 중복되면 다음과 같은 데이터 관리 워크플로우 활동에 문제가 발생합니다. **쿼리**, **조정**, **데이터 업데이트**, 등. 업데이트할 때 적절한 조정 기준을 정의하는 데 중요합니다 [!DNL Snowflake] 표.


>[!CAUTION]
>
>중복되는 키는 UUID로 제한되지 않습니다. 사용자 지정 테이블에서 만들어진 사용자 지정 키를 포함하여 ID에서 발생할 수 있습니다.


## 단일성 서비스{#unicity-service}

Unity Service는 클라우드 데이터베이스 테이블 내에서 고유한 키 제약 조건의 무결성을 유지 및 모니터링하는 데 도움이 되는 클라우드 데이터베이스 관리자 구성 요소입니다. 이를 통해 중복 키를 삽입할 위험을 줄일 수 있습니다.

클라우드 데이터베이스가 원자성 제약 조건을 적용하지 않으므로 Adobe Campaign을 사용하여 데이터를 관리할 때 중복 항목을 삽입할 위험이 줄어듭니다.

### 비원자성 워크플로우{#unicity-wf}

유니시티 서비스는 전용 **[!UICONTROL Unicity alerting]** 기본 제공 워크플로우에서 중복이 검색되면 비상성 제한 및 경고를 모니터링합니다.

이 기술 워크플로우는 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** campaign Explorer 노드 아래에 있습니다. **수정해서는 안 됩니다**.

이 워크플로우는 모든 사용자 지정 및 내장 스키마를 확인하여 중복된 행을 검색합니다.

![](assets/unicity-alerting-wf.png)

만약 **[!UICONTROL Unicity alerting]** (ffdaUnity) 워크플로우에서 일부 중복 키를 감지하면 특정 키에 추가됩니다 **Audit Unity** 표의 이름, 키 유형, 영향을 받은 행 수 및 날짜가 포함된 테이블입니다. 에서 중복된 키에 액세스할 수 있습니다 **[!UICONTROL Administration > Audit > Key Unicity]** 노드 아래에 있어야 합니다.

![](assets/unicity-table.png)

데이터베이스 관리자는 SQL 활동을 사용하여 중복을 제거하거나 Adobe 고객 지원 센터에 문의하여 추가 지침을 받을 수 있습니다.

### 경고{#unicity-wf-alerting}

특정 알림이 **[!UICONTROL Workflow Supervisors]** 중복 키가 검색되면 운영자 그룹 을 지정합니다. 이 경고의 콘텐츠와 대상은 **경고** 의 활동 **[!UICONTROL Unicity alerting]** 워크플로우.

![](assets/wf-alert-activity.png)


## 추가 보호 기능{#duplicates-guardrails}

Campaign에는 중복된 키가 삽입되지 않도록 하는 새 보호 기능이 포함되어 있습니다 [!DNL Snowflake] 데이터베이스.

>[!NOTE]
>
>이러한 경고는 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 다음을 참조하십시오 [이 섹션](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### 게재 준비{#remove-duplicates-delivery-preparation}

Adobe Campaign은 게재를 준비하는 동안 대상자에서 중복되는 UUID를 자동으로 제거합니다. 이 메커니즘은 게재를 준비하는 동안 오류가 발생하지 않도록 합니다. 최종 사용자는 게재 로그에서 이 정보를 확인할 수 있습니다. 중복 키로 인해 일부 수신자는 기본 대상에서 제외할 수 있습니다. 이 경우 다음 경고가 표시됩니다. `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### 워크플로우에서 데이터 업데이트{#duplicates-update-data}

의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](enterprise-deployment.md)를 채울 경우 내부 키(UUID)를 필드로 선택하여 워크플로우에서 데이터를 업데이트할 수 없습니다.

![](assets/update-data-no-internal-key.png)

명시적 조정 키를 사용하는 경우 **데이터 업데이트** 활동은 다음 방법으로 이 키를 기반으로 대상 스키마를 자동으로 만듭니다.

1. 들어오는 데이터 중복 제거(전환에서)
1. 대상 테이블을 사용하여 데이터 중복 제거(병합)


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>이 보증은 선택 사항에만 적용됩니다 **[!UICONTROL Using reconciliation keys]**.


### 중복 항목을 사용하여 스키마 쿼리{#query-with-duplicates}

워크플로우가 스키마에서 쿼리 실행을 시작하면 Adobe Campaign은 중복된 레코드가 [감사 불가능성 테이블](#unicity-wf). 그럴 경우, 중복된 데이터에 대한 후속 작업이 워크플로우 결과에 영향을 줄 수 있으므로 워크플로우는 경고를 기록합니다.

![](assets/query-with-duplicates.png)

이 검사는 다음 워크플로우 활동에서 수행됩니다.

* 쿼리
* 증분 쿼리
* 목록 읽기