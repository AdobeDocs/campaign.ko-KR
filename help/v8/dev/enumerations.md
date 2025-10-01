---
title: 열거 관리
description: 열거형으로 작업하는 방법을 알아봅니다.
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# 열거 관리 {#manage-enumerations}

열거형(항목별 목록이라고도 함)은 특정 필드를 채우는 데 사용할 수 있는 미리 정의된 값 목록입니다. 열거형을 사용하면 필드 값을 표준화하여 데이터 항목을 보다 일관되게 만들고 쿼리를 단순화할 수 있습니다.

사용 가능한 경우 값이 드롭다운 목록에 나타납니다. 값을 직접 선택하거나 입력을 시작할 수 있습니다. 예측 입력은 일치하는 값을 제안하고 자동으로 완료합니다.

![](assets/enum_values.png)

일부 콘솔 필드는 열거형으로 구성됩니다. 열거형이 **open**&#x200B;인 경우 필드에 직접 새 값을 추가할 수도 있습니다.

## 열거형 액세스

이러한 필드에 사용된 값은 중앙에서 관리됩니다. 탐색기 트리의 **관리** `>` **플랫폼** `>` **열거형**&#x200B;에서 해당 트리를 추가, 편집, 업데이트 또는 삭제할 수 있습니다.

* 상단 섹션은 열거형이 정의된 필드 목록을 제공합니다.
* 아래 섹션에는 사용 가능한 값이 나열됩니다.

열거형이 **[!UICONTROL Open]**&#x200B;인 경우 사용자는 사용자 인터페이스의 해당 필드에 직접 새 값을 입력할 수 있습니다.

열거형이 **[!UICONTROL Closed]**&#x200B;인 경우 새 값은 **열거형** 메뉴에서만 추가할 수 있습니다.

## 새 값 추가

새 열거형 값을 만들려면 **[!UICONTROL Add]** 단추를 클릭하십시오.

![](assets/enumeration_screen.png)

값의 레이블을 입력합니다.


## 별칭 정리 {#alias-cleansing}

열거형 필드에 열거형 값을 제외한 값을 입력할 수 있습니다. 이러한 지표는 그대로 보관하거나 세척할 수 있습니다.

>[!CAUTION]
>
>데이터 정리는 데이터베이스의 데이터에 영향을 주는 중요한 프로세스입니다. Adobe Campaign은 대량 데이터 업데이트를 수행하여 일부 값이 삭제될 수 있습니다. 따라서 이 작업은 전문가 사용자용으로 예약되어 있습니다.

입력한 값은 다음 중 하나입니다.

* 항목별 목록 값에 추가됨: 이 경우 **[!UICONTROL Open]** 옵션을 선택해야 합니다.
* 또는 해당 별칭으로 자동으로 대체됩니다. 이 경우 항목별 목록의 **[!UICONTROL Alias]** 탭에서 이 대/소문자를 정의해야 합니다.
* 또는 는 별칭 목록에 저장됩니다. 나중에 별칭을 할당할 수 있습니다.

### 별칭 만들기 {#creating-an-alias}

**[!UICONTROL Alias cleansing]** 옵션을 사용하면 선택한 항목별 목록에 별칭을 사용할 수 있습니다. 이 옵션을 선택하면 **[!UICONTROL Alias]** 탭이 창 하단에 표시됩니다.

별칭을 만들려면 다음 단계를 수행하십시오.

1. 열거형으로 이동하여 업데이트하고 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.

   ![](assets/enumeration_alias_create.png)

1. 변환할 별칭과 적용할 값을 입력하고 **[!UICONTROL Ok]**&#x200B;을(를) 클릭합니다.

1. 이 작업을 확인하기 전에 매개 변수를 확인하십시오.

>[!CAUTION]
>
>이 단계가 확인되면 이전 값이 복구되지 않을 수 있습니다. 이 값은 대체됩니다.

따라서 사용자가 &quot;회사&quot; 필드(Adobe Campaign 콘솔 또는 양식)에서 값 **NEILSEN**&#x200B;을(를) 입력하면 자동으로 값 **NIELSEN Ltd**(으)로 바뀝니다. 값 교체는 **별칭 정리** 워크플로우에서 수행됩니다. [데이터 정리 실행](#running-data-cleansing)을 참조하세요.

![](assets/enumeration_alias_use.png)

### 값을 별칭으로 변환 {#values-into-aliases}

기존 값을 별칭으로 변환할 수 있습니다. 이렇게 하려면 다음 단계를 수행합니다.

1. 값 목록을 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Convert values into aliases...]**&#x200B;을(를) 선택합니다.

1. 변환할 값을 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.

1. 변환을 실행하려면 **[!UICONTROL Start]**&#x200B;을(를) 클릭합니다.

실행이 완료되면 별칭이 별칭 목록에 추가됩니다.

### 별칭 히트 검색 {#alias-hits}

사용자가 열거에 포함되지 않은 값을 입력하면 **[!UICONTROL Alias]** 탭에 저장됩니다.

**별칭 정리** 기술 워크플로는 매일 밤 이러한 값을 복구하여 열거형을 업데이트합니다. [데이터 정리 실행](#running-data-cleansing)을 참조하세요.

필요한 경우 **[!UICONTROL Hits]** 열에 이 값이 입력된 횟수를 표시할 수 있습니다. 그러나 이 값을 계산하는 데는 시간과 메모리가 모두 소모될 수 있습니다. 자세한 내용은 [항목 발생 횟수 계산](#calculating-entry-occurrences)을 참조하세요.

### 데이터 정리 실행 {#run-data-cleansing}

데이터 정리는 **[!UICONTROL Alias cleansing]** 기술 워크플로우에서 수행됩니다. 열거형에 대해 정의된 구성은 실행 중에 적용됩니다. [별칭 정리 워크플로우](#alias-cleansing-workflow)를 참조하세요.

**[!UICONTROL Cleanse values...]** 링크를 통해 정리를 트리거할 수 있습니다.

**[!UICONTROL Advanced parameters...]** 링크를 사용하여 수집된 값을 고려하는 시작 날짜를 설정할 수 있습니다.

데이터 정리를 실행하려면 **[!UICONTROL Start]** 단추를 클릭하세요.

### 시작 발생 횟수 계산 {#entry-occurrences}

항목별 목록의 **[!UICONTROL Alias]** 하위 탭에는 입력된 모든 값 중에서 별칭이 발생한 횟수가 표시됩니다. 이 정보는 예상 정보이며 **[!UICONTROL Hits]** 열에 표시됩니다.

>[!CAUTION]
>
>별칭 항목 발생 횟수를 계산하는 데 시간이 오래 걸릴 수 있습니다. 그렇기 때문에 이 기능을 사용할 때는 주의해야 한다.

**[!UICONTROL Cleanse values...]** 링크를 통해 히트 계산을 수동으로 실행할 수 있습니다. 이렇게 하려면 **[!UICONTROL Advanced parameters...]** 링크를 클릭하고 원하는 옵션을 선택합니다.

* **[!UICONTROL Update the number of alias hits]**: 입력한 날짜에 따라 이미 계산된 히트를 업데이트할 수 있습니다.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: 전체 Adobe Campaign 플랫폼에서 계산을 실행할 수 있습니다.

예를 들어 일주일에 한 번, 주어진 기간 동안 자동으로 계산이 실행되도록 전용 워크플로우를 만들 수도 있습니다.

이렇게 하려면 **[!UICONTROL Alias cleansing]** 워크플로우의 복사본을 만들고 스케줄러를 변경한 후 **[!UICONTROL Enumeration value cleansing]** 활동에서 다음 설정을 사용하십시오.

* 별칭 히트 수를 업데이트하려면 **-updateHits**&#x200B;을(를) 업데이트하십시오.
* 모든 별칭 히트를 다시 계산하기 위해 **-updateHits:full**.

### 별칭 정리 워크플로우 {#alias-cleansing-workflow}

**별칭 정리** 워크플로는 열거형 값 정리를 실행합니다. 기본적으로 매일 실행됩니다.

**[!UICONTROL Administration > Production > Technical workflows]** 노드를 통해 액세스합니다.


