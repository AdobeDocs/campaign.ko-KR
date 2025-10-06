---
title: 열거 관리
description: 열거형으로 작업하는 방법을 알아봅니다.
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: a1f479538a2d93a2ec13e35cb6813e09c8c4a5f8
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# 열거형을 사용한 작업 {#enumerations}

열거형(항목별 목록이라고도 함)은 특정 필드를 채우는 데 사용할 수 있는 미리 정의된 값 목록입니다. 열거형을 사용하면 필드 값을 표준화하여 데이터 항목을 보다 일관되게 만들고 쿼리를 단순화할 수 있습니다.

정의된 값은 드롭다운 목록에 표시됩니다. 값을 직접 선택하거나 일치하는 항목을 제안하고 완료하는 예측 입력을 사용하여 입력할 수 있습니다. 일부 필드에는 사전 정의된 열거형이 포함되어 있으며, 필요한 경우 추가 열거형을 만들 수 있습니다.

![](assets/enum_values.png)


## 열거형 유형 {#types-of-enum}

열거형은 탐색기의 **[!UICONTROL Administration > Platform > Enumerations]** 폴더에 저장됩니다.

![열거형 액세스](../config/assets/enumerations-menu.png)


열거형은 **열기**, **시스템**, **이모티콘** 또는 **닫힘**&#x200B;일 수 있습니다.

* **Open** 열거형을 사용하면 이 열거형을 기반으로 필드에 직접 새 값을 추가할 수 있습니다.
* **Closed** 열거형에는 탐색기의 **[!UICONTROL Administration > Platform > Enumerations]** 폴더에서만 수정할 수 있는 고정 값 목록이 있습니다.
* **이모티콘** 열거형을 사용하여 이모티콘 목록을 업데이트합니다. 자세히 알아보기
* **System** 열거형은 시스템 필드에 연결되어 있으며 내부 이름으로 제공됩니다.

**Open** 및 **Closed** 열거형의 경우 특정 옵션을 사용할 수 있습니다.

* **단순 열거**&#x200B;은(는) 기본 표준 형식입니다.
* **별칭 정리** 열거형은 데이터베이스에 저장된 열거형 값을 조합하는 데 사용됩니다. [자세히 알아보기](#alias-cleansing)
* **비닝용으로 예약됨**&#x200B;은(는) 큐브 값을 이 열거형에 연결할 수 있는 옵션입니다. [자세히 알아보기](../reporting/gs-cubes.md)


## 별칭 정리 {#alias-cleansing}

열거형 필드의 드롭다운 목록에서 값을 선택하거나, 목록에서 값을 사용할 수 없는 경우 수동으로 입력할 수 있습니다. **[!UICONTROL Open]** 옵션을 사용하도록 설정하면 사용자 지정 값을 열거에 추가할 수 있습니다. 이러한 값은 나중에 별칭 정리를 통해 표준화할 수 있습니다. 별칭 정리는 올바른 용어로 변형을 자동으로 바꿉니다(예: `Adob`을(를) `Adobe`(으)로 변환).


>[!CAUTION]
>
>데이터 정리는 데이터베이스 값에 영향을 주는 중요한 작업입니다. Adobe Campaign은 대량 데이터 업데이트를 수행하여 특정 값이 삭제될 수 있습니다. 이 작업은 전문가 사용자만을 대상으로 합니다.

열거에 데이터 정리 기능을 사용하려면 **[!UICONTROL Alias cleansing]** 옵션을 활성화하십시오. 이 옵션을 선택하면 **[!UICONTROL Alias]** 탭이 창 하단에 표시됩니다.

사용자가 별칭 정리 열거에 없는 값을 입력하면 **값** 목록에 추가됩니다. [이 값으로 별칭을 만들거나](#convert-to-alias) [처음부터 새 별칭을 만들 수 있습니다](#create-alias).

### 별칭 만들기{#create-alias}

별칭을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Add]** 탭의 **[!UICONTROL Alias]** 단추를 클릭합니다.
1. 변환할 별칭을 입력하고 드롭다운 목록에서 적용할 값을 선택합니다.

   ![새 별칭 만들기](assets/new-alias.png)

1. **[!UICONTROL Ok]**&#x200B;을(를) 클릭하고 확인합니다.

1. 변경 내용을 저장합니다. 매일 밤 실행되는 **별칭 정리** 워크플로우에서 값 대체를 수행합니다. [데이터 정리 실행](#running-data-cleansing)을 참조하세요.

이 열거를 기반으로 하는 모든 필드의 경우, 사용자가 &quot;회사&quot; 필드(Adobe Campaign 클라이언트 콘솔의 웹 양식)에 값 **Adobe**&#x200B;을(를) 입력하면 자동으로 값 **Adobe**(으)로 바뀝니다.

### 잘못된 값을 별칭으로 변환{#convert-to-alias}

기존 열거형 값을 별칭으로 변환할 수도 있습니다. 다음을 수행하십시오.

1. 열거형의 값 목록에서 마우스 오른쪽 단추를 클릭하고 **[!UICONTROL Actions... > Convert values into aliases...]**&#x200B;을(를) 찾습니다.

   ![값을 별칭으로 변환](assets/convert-into-aliases.png)

1. 별칭으로 변환할 값을 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.
1. 변환을 실행하려면 **[!UICONTROL Start]**&#x200B;을(를) 클릭합니다.

   실행이 완료되면 **별칭** 탭에서 별칭이 목록에 추가됩니다. 올바른 값을 연결하여 잘못된 항목을 바꿀 수 있습니다. 다음을 수행하십시오.

1. 정리할 값을 선택합니다.
1. **세부 정보...** 단추를 클릭합니다.
1. 드롭다운 목록에서 새 값을 선택합니다.

   ![새 별칭 만들기](assets/define-new-alias.png)


>[!NOTE]
>
>**[!UICONTROL Hits]** 하위 탭의 **[!UICONTROL Alias]** 열에서 별칭 발생을 추적할 수 있습니다. 이 값이 입력된 횟수를 표시할 수 있습니다.  [자세히 알아보기](#calculate-entry-occurrences)

### 데이터 정리 실행 {#running-data-cleansing}

데이터 정리는 **[!UICONTROL Alias cleansing]** 기술 워크플로우에서 수행됩니다. 기본적으로 매일 실행됩니다.

**[!UICONTROL Cleanse values...]** 링크를 통해 정리 작업을 트리거할 수도 있습니다.

**[!UICONTROL Advanced parameters...]** 링크를 사용하여 수집된 값을 고려하는 시작 날짜를 설정할 수 있습니다.

데이터 정리를 실행하려면 **[!UICONTROL Start]** 단추를 클릭하세요.

### 발생 횟수 모니터링 {#calculate-entry-occurrences}

열거형의 **[!UICONTROL Alias]** 하위 탭에는 입력된 모든 값 중에서 별칭이 발생한 횟수가 표시됩니다. 이 정보는 예상 정보이며 **[!UICONTROL Hits]** 열에 표시됩니다.

>[!CAUTION]
>
>별칭 항목 발생 횟수를 계산하는 데 시간이 오래 걸릴 수 있습니다.
>

**[!UICONTROL Cleanse values...]** 링크를 통해 히트 계산을 수동으로 실행할 수 있습니다. 이렇게 하려면 **[!UICONTROL Advanced parameters...]** 링크를 클릭하고 옵션을 선택합니다.

* **[!UICONTROL Update the number of alias hits]**: 입력한 날짜에 따라 이미 계산된 히트를 업데이트할 수 있습니다.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: 전체 Adobe Campaign 플랫폼에서 계산을 실행할 수 있습니다.

예를 들어 일주일에 한 번, 주어진 기간 동안 자동으로 계산이 실행되도록 전용 워크플로우를 만들 수도 있습니다.

이렇게 하려면 **[!UICONTROL Alias cleansing]** 워크플로우의 복사본을 만들고 스케줄러를 변경한 후 **[!UICONTROL Enumeration value cleansing]** 활동에서 다음 설정을 사용하십시오.

* 별칭 히트 수를 업데이트하려면 **-updateHits**&#x200B;을(를) 업데이트하십시오.
* 모든 별칭 히트를 다시 계산하기 위해 **-updateHits:full**.
