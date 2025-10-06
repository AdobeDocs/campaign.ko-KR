---
title: Adobe Campaign에서 큐브 만들기
description: 큐브를 만드는 방법 알아보기
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: 03a6816b-e51a-4eaf-ab76-02d24f97ba46
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 3%

---

# 큐브 만들기{#create-a-cube}

## 큐브 작업 영역 {#cube-workspace}

큐브에 액세스하려면 캠페인 탐색기에서 **[!UICONTROL Administration > Configuration > Cubes]**&#x200B;을(를) 찾습니다.

![](assets/cube-node.png)

큐브를 사용하여 다음을 수행할 수 있습니다.

* Adobe Campaign 플랫폼의 **[!UICONTROL Reports]** 탭에서 설계된 보고서에서 데이터를 직접 내보냅니다.

  이렇게 하려면 새 보고서를 만들고 사용할 큐브를 선택합니다.

  ![](assets/create-new-cube.png)

  큐브는 보고서를 작성하는 데 사용하는 템플릿처럼 표시됩니다. 템플릿을 선택한 후 **[!UICONTROL Create]**&#x200B;을(를) 클릭하여 새 보고서를 구성하고 봅니다.

  측정값을 조정하거나 표시 모드를 변경하거나 테이블을 구성한 다음 기본 단추를 사용하여 보고서를 표시할 수 있습니다.

  ![](assets/display-cube-table.png)

* 아래와 같이 보고서의 **[!UICONTROL Query]** 상자에서 큐브를 참조하여 해당 지표를 사용합니다.

  ![](assets/cube-report-query.png)

* 큐브를 기반으로 한 피벗 테이블을 보고서의 페이지에 삽입합니다. 이렇게 하려면 관련 페이지의 피벗 테이블의 **[!UICONTROL Data]** 탭에서 사용할 큐브를 참조합니다.

  ![](assets/cube-in-a-report.png)

  자세한 내용은 [보고서의 데이터 탐색](cube-tables.md#explore-the-data-in-a-report)을 참조하세요.


>[!CAUTION]
>
>큐브를 만들려면 관리자 권한이 필요합니다.
>

## 큐브 작성{#cube-create}

큐브 보고서 작성을 시작하기 전에 관련 차원 및 측정값을 식별하고 큐브에서 만듭니다.

큐브를 생성하려면 다음 단계를 적용합니다.

1. 작업 테이블을 선택합니다. [자세히 알아보기](#select-the-work-table)
1. 차원을 정의합니다. [자세히 알아보기](#define-dimensions)
1. 측정값을 정의합니다. [자세히 알아보기](#build-indicators)
1. 집계 만들기(선택 사항). [자세히 알아보기](customize-cubes.md#calculate-and-use-aggregates)

아래 예에서는 보고서에서 간단한 큐브를 빠르게 생성하여 해당 측정 단위를 내보내는 방법을 알아봅니다.

### 작업 테이블 선택 {#select-the-work-table}

큐브를 생성하려면 아래 단계를 수행합니다.

1. 큐브 목록 위에 있는 **[!UICONTROL New]** 단추를 클릭합니다.

   ![](assets/create-a-cube.png)

1. 탐색할 요소(&#39;팩트 스키마&#39;라고도 함)가 포함된 스키마를 선택합니다. 이 예제에서는 기본 **받는 사람** 테이블을 선택합니다.
1. 큐브를 만들려면 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다. 큐브가 큐브 목록에 추가됩니다. 이제 탭을 사용하여 구성할 수 있습니다.

1. **[!UICONTROL Filter the source data...]** 링크를 클릭하여 이 큐브의 계산을 데이터베이스의 데이터에 적용합니다.

   ![](assets/cube-filter-source.png)

### 차원 정의 {#define-dimensions}

큐브가 생성되면 해당 차원을 정의합니다. 차원은 관련 팩트 스키마를 기반으로 각 큐브에 대해 정의된 분석 축입니다. 시간(연도, 월, 날짜), 제품 또는 계약의 분류(가족, 참조 등), 인구 세그먼트(도시, 연령 그룹, 상태 등)와 같이 분석에서 탐색한 차원입니다.

차원을 생성하려면 아래 단계를 수행합니다.

1. 큐브의 **[!UICONTROL Dimension]** 탭으로 이동한 다음 **[!UICONTROL Add]** 단추를 클릭하여 새 차원을 만듭니다.
1. **[!UICONTROL Expression field]**&#x200B;에서 **[!UICONTROL Edit expression]** 아이콘을 클릭하여 관련 데이터가 포함된 필드를 선택합니다.

   ![](assets/cube-add-dimension.png)

1. 이 예제에서는 받는 사람 **Age**&#x200B;을(를) 선택합니다. 이 필드의 경우, 나이를 그룹화하고 정보를 더 쉽게 읽을 수 있도록 비닝을 정의할 수 있습니다. 여러 개의 별도 값이 있을 가능성이 있는 경우 비닝을 사용하는 것이 좋습니다.

이렇게 하려면 **[!UICONTROL Enable binning]** 옵션을 선택하십시오. [자세히 알아보기](customize-cubes.md#data-binning)

1. **날짜** 유형 차원을 추가합니다. 여기에서는 수신자 프로필 생성 날짜를 표시하려고 합니다. 이렇게 하려면 **[!UICONTROL Add]**&#x200B;을(를) 클릭하고 받는 사람 테이블에서 **[!UICONTROL Creation date]** 필드를 선택합니다.
날짜 표시 모드를 사용자 정의할 수 있습니다. 이렇게 하려면 사용할 계층과 생성할 레벨을 선택합니다.

![](assets/cube-date-dimension.png)

이 예제에서는 연도, 월, 일만 표시하려고 합니다. 주 및 학기/월을 동시에 사용하여 작업할 수 없습니다. 이러한 수준은 호환되지 않습니다.

1. 수신자의 도시를 기준으로 데이터를 분석할 다른 차원을 만듭니다. 이렇게 하려면 새 차원을 추가하고 수신자 스키마의 **[!UICONTROL Location]** 노드에서 도시를 선택합니다.

비닝을 사용하면 정보를 더 쉽게 읽고 값을 [열거형](../config/enumerations.md)에 연결할 수 있습니다.

드롭다운 목록에서 열거형을 선택합니다. 이 열거형은 **[!UICONTROL Reserved for binning]**(으)로 정의해야 합니다.

![](assets/cube-dimension-with-enum.png)

열거형의 값만 표시됩니다. 다른 항목은 **[!UICONTROL Label of the other values]** 필드에 정의된 레이블 아래에 그룹화됩니다.

이 작업에 대한 자세한 정보는 [이 섹션](customize-cubes.md#dynamically-manage-bins)을 참조하십시오.

### 지표 작성 {#build-indicators}

차원이 정의되면 셀에 표시할 값에 대한 계산 모드를 지정합니다.

이렇게 하려면 **[!UICONTROL Measures]** 탭에서 지표를 만듭니다. 이 큐브를 기반으로 보고서에 표시할 열이 있는 수만큼 측정값을 만듭니다.

지표를 만들려면 아래 단계를 수행하십시오.

1. **[!UICONTROL Measures]** 탭으로 이동하여 **[!UICONTROL Add]** 단추를 클릭합니다.
1. 적용할 측정 유형과 공식을 선택합니다. 이 예에서는 수신자 중 여성의 수를 세고 있습니다. 이 측정은 팩트 스키마를 기반으로 하며 **[!UICONTROL Count]** 연산자를 사용합니다.

   ![](assets/cube-new-measure.png)

   **[!UICONTROL Filter the measure data...]** 링크를 사용하여 여성만 선택하십시오. [자세히 알아보기](customize-cubes.md#define-measures)

   ![](assets/cube-filter-measure-data.png)

1. 측정값의 레이블을 입력하고 저장합니다.

   ![](assets/cube-save-measure.png)

1. 큐브를 저장합니다.


이제 이 큐브를 기반으로 보고서를 만들 수 있습니다. [자세히 알아보기](cube-tables.md)
