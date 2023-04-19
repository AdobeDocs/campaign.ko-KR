---
title: Campaign 인터페이스 설정
description: Campaign 인터페이스 설정을 사용자 지정하는 방법 알아보기
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Campaign 사용자 인터페이스 설정 {#ui-settings}

## 열거형 {#enumerations}

열거형(&#39;항목별 목록&#39;이라고도 함)은 필드를 채우기 위해 시스템에서 제안하는 값 목록입니다. 열거형을 사용하여 이러한 필드의 값을 표준화하고 데이터 입력 또는 쿼리 내에서 사용할 수 있습니다.

값 목록이 드롭다운 목록으로 나타납니다. 이 목록에서 필드에 입력할 값을 선택할 수 있습니다. 드롭다운 목록에서 예측 입력을 사용할 수도 있습니다. 첫 번째 문자를 입력하면 나머지는 애플리케이션에 입력됩니다.

이 유형의 필드에 대한 값이 정의되며, 이러한 필드의 전체 관리(값 추가/삭제)는 **[!UICONTROL Administration > Platform > Enumerations]** 노드 아래에 있어야 합니다.

![열거형 액세스](assets/enumerations-menu.png)

### 열거형 유형 {#types-of-enum}

열거형은 **[!UICONTROL Administration > Platform > Enumerations]** 탐색기 폴더

다음 항목을 지정할 수 있습니다. 열기, 시스템, 이모티콘 또는 닫힘.

* An **열기** 열거형을 사용하면 이 열거형을 기반으로 필드에 직접 새 값을 추가할 수 있습니다.
* A **닫힘** 열거형에는 **[!UICONTROL Administration > Platform > Enumerations]** 탐색기 폴더
* An **이모티콘** 열거형은 이모티콘 목록을 업데이트하는 데 사용됩니다. 자세히 알아보기
* A **시스템** 열거형은 시스템 필드에 연결되며 내부 이름과 함께 제공됩니다.

대상 **열기** 및 **닫힘** 열거형, 특정 옵션을 사용할 수 있습니다.

* **단순 열거형** 는 기본 표준 유형입니다.
* **별칭 정리** 열거형은 데이터베이스에 저장된 열거형 값을 일치시키는 데 사용됩니다. [자세히 알아보기](#alias-cleansing)
* **시작용으로 예약됨** 는 큐브 값을 이 열거형에 연결할 수 있는 옵션입니다. [자세히 알아보기](../reporting/gs-cubes.md)


### 별칭 정리 {#alias-cleansing}

열거형 필드에서 값을 선택하거나 드롭다운 목록에서 사용할 수 없는 사용자 지정 값을 입력할 수 있습니다. 사용자 지정 값을 기존 열거형 값에 추가할 수 있습니다. 이 경우 **[!UICONTROL Open]** 옵션을 선택해야 합니다. 이러한 사용자 지정 값은 별칭 정리 기능을 사용하여 정리할 수 있습니다. 예를 들어, 사용자가 `Adob` 대신 `Adobe`, 별칭 정리 프로세스는 자동으로 올바른 용어로 대체할 수 있습니다.

>[!CAUTION]
>
>데이터 청소는 데이터베이스의 데이터에 영향을 주는 중요한 프로세스입니다. Adobe Campaign은 대량 데이터 업데이트를 수행하므로 일부 값이 삭제될 수 있습니다. 따라서 이 작업은 전문가 사용자를 위해 예약되어 있습니다.

를 활성화합니다 **[!UICONTROL Alias cleansing]** 열거형에 데이터 정리 기능을 사용하는 옵션입니다. 이 옵션을 선택하면 **[!UICONTROL Alias]** 창의 아래쪽에 탭이 표시됩니다.

사용자가 별칭 정리 열거형에 없는 값을 입력하면 **값** 목록. 다음을 수행할 수 있습니다 [이 값에서 별칭 생성](#convert-to-alias), 또는 [처음부터 새로운 별칭 만들기](#create-alias).

#### 별칭 만들기{#create-alias}

별칭을 만들려면 다음 단계를 수행합니다.

1. 클릭 **[!UICONTROL Add]** 버튼 **[!UICONTROL Alias]** 탭.
1. 변환할 별칭을 입력하고 드롭다운 목록에서 적용할 값을 선택합니다.

   ![새 별칭 만들기](assets/new-alias.png)

1. 클릭 **[!UICONTROL Ok]** 확인

1. 변경 내용을 저장합니다. 값은 **별칭 정리** 매일 밤 실행되는 작업 과정. 을(를) 참조하십시오. [데이터 정리 실행](#running-data-cleansing).

이 열거형을 기반으로 하는 모든 필드의 경우 사용자가 값을 입력할 때 **Adobe** 회사 필드(Adobe Campaign 콘솔의 웹 양식)에서는 자동으로 값으로 대체됩니다 **Adobe**.

#### 잘못된 값을 별칭으로 변환{#convert-to-alias}

기존 열거형 값을 별칭으로 변환할 수도 있습니다. 다음을 수행하십시오.

1. 열거형의 값 목록에서 마우스 오른쪽 단추를 클릭하고 **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![값을 별칭으로 변환](assets/convert-into-aliases.png)

1. 별칭으로 변환할 값을 선택하고 를 클릭합니다 **[!UICONTROL Next]**.
1. 클릭 **[!UICONTROL Start]** 변환 실행

   실행이 완료되면 별칭이 목록에 추가되고 **별칭** 탭. 잘못된 항목을 대체하기 위해 올바른 값을 연결할 수 있습니다. 다음을 수행하십시오.

1. 정리할 값을 선택합니다.
1. 을(를) 클릭합니다. **세부 정보...** 버튼을 클릭합니다.
1. 드롭다운 목록에서 새 값을 선택합니다.

   ![새 별칭 만들기](assets/define-new-alias.png)


>[!CAUTION]
>
>에서 별칭 발생 항목을 추적할 수 있습니다 **[!UICONTROL Hits]** 열 **[!UICONTROL Alias]** 하위 탭. 이 값을 입력한 횟수를 표시할 수 있습니다.  [자세히 알아보기](#calculate-entry-occurrences)

#### 데이터 정리 실행 {#running-data-cleansing}

데이터 정리는 **[!UICONTROL Alias cleansing]** 기술 워크플로우입니다. 기본적으로 매일 실행됩니다.

클렌징은 를 통해 트리거될 수도 있습니다 **[!UICONTROL Cleanse values...]** 링크를 클릭합니다.

다음 **[!UICONTROL Advanced parameters...]** 링크를 사용하면 수집된 값을 고려하는 시작일을 설정할 수 있습니다.

을(를) 클릭합니다. **[!UICONTROL Start]** 데이터 정리 실행 단추.

##### 발생 횟수 모니터링 {#calculate-entry-occurrences}

다음 **[!UICONTROL Alias]** 열거형의 하위 탭에는 입력한 모든 값 중에서 별칭 발생 횟수가 표시될 수 있습니다. 이 정보는 추정치이며 **[!UICONTROL Hits]** 열.

>[!CAUTION]
>
>별칭 항목 발생 수를 계산하는 데 시간이 오래 걸릴 수 있습니다.

를 통해 수동으로 히트 계산을 실행할 수 있습니다 **[!UICONTROL Cleanse values...]** 링크를 클릭합니다. 이렇게 하려면 **[!UICONTROL Advanced parameters...]** 링크와 옵션을 선택합니다.

* **[!UICONTROL Update the number of alias hits]**: 이렇게 하면 입력한 날짜를 기준으로 이미 계산된 히트를 업데이트할 수 있습니다.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: 전체 Adobe Campaign 플랫폼에서 계산을 실행할 수 있습니다.

예를 들어 일주일에 한 번, 지정한 기간 동안 계산이 자동으로 실행되도록 전용 워크플로우를 만들 수도 있습니다.

이렇게 하려면 복사본을 만듭니다 **[!UICONTROL Alias cleansing]** 워크플로우에서 스케줄러를 변경하고, **[!UICONTROL Enumeration value cleansing]** 활동:

* **-updateHits** 별칭 히트 수를 업데이트하려면
* **-updateHits:full** 모든 별칭 히트를 재계산하려면
