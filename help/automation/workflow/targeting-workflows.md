---
title: 타겟팅 워크플로우 만들기
description: 워크플로우에서 타겟 대상자를 만드는 방법을 알아봅니다
feature: Query Editor, Data Management
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '2248'
ht-degree: 4%

---

# 타기팅 워크플로우 만들기{#target-data}

워크플로우를 사용하여 데이터베이스를 쿼리하고 데이터를 세그먼트화할 수 있습니다. Campaign 워크플로우 모듈은 데이터 관리 활동을 수행하고, 데이터를 추출, 보강 및 변형하고, 대상을 관리하고, 모집단을 정교화할 수 있는 강력한 도구입니다.

타겟팅 워크플로우를 사용하여 여러 게재 타겟을 만들 수 있습니다. 워크플로우 활동을 통해 쿼리를 만들고, 특정 기준에 따라 결합 또는 제외를 정의하고, 예약을 추가할 수 있습니다. 이 타겟팅의 결과는 게재 작업의 타겟으로 사용할 수 있는 목록으로 자동으로 전송될 수 있습니다

데이터 관리 옵션을 사용하면 이러한 활동 외에도 데이터를 조작하고 고급 기능에 액세스하여 복잡한 타겟팅 문제를 해결할 수 있습니다. 자세한 내용은 [데이터 관리](targeting-workflows.md#data-management).

이러한 모든 활동은 첫 번째 워크플로우 탭에서 찾을 수 있습니다.

>[!NOTE]
>
>타겟팅 활동은 [이 섹션](activities.md).

을 통해 타겟팅 워크플로우를 만들고 편집할 수 있습니다. **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** Adobe Campaign 트리의 노드 또는 **[!UICONTROL Profiles and Targets > Targeting workflows]** 홈 페이지의 메뉴.

![](assets/target_wf.png)

캠페인의 프레임워크 내에 있는 타깃팅 워크플로우는 모든 캠페인 워크플로우와 함께 저장됩니다.

## 타겟팅 워크플로우를 만드는 주요 단계 {#implementation-steps-}

타겟팅 워크플로우를 만드는 단계는 다음 섹션에 자세히 설명되어 있습니다.

1. **식별** 데이터베이스의 데이터 - [쿼리 만들기](#create-queries)
1. **준비** 게재 요구 사항을 충족하는 데이터 - 참조 [데이터 보강 및 수정](#enrich-and-modify-data)
1. **사용** 업데이트 또는 게재 내에서 수행할 데이터 - [데이터베이스 업데이트](use-workflow-data.md#update-the-database)

타겟팅 중에 수행한 모든 데이터 보강 및 모든 핸들의 결과는 개인화 필드에 저장되고 액세스할 수 있으며, 특히 개인화된 메시지를 만들 때 사용할 수 있습니다. 자세한 내용은 [Target 데이터](use-workflow-data.md#target-data).

## 차원 타겟팅 및 필터링 {#targeting-and-filtering-dimensions}

데이터 세분화 작업 중에 타겟팅 키가 필터링 차원에 매핑됩니다. 타겟팅 차원을 사용하면 작업의 타겟팅된 모집단을 정의할 수 있습니다. 수신자, 계약 수혜자, 운영자, 가입자 등 필터링 차원을 사용하면 특정 기준에 따라 모집단을 선택할 수 있습니다. 계약자, 뉴스레터 구독자 등

예를 들어, 5년 이상 생명 보험 계약이 있는 클라이언트를 선택하려면 다음 타겟팅 차원을 선택합니다. **클라이언트** 및 다음 필터링 차원: **계약자**. 그런 다음 쿼리 활동 내에서 필터링 조건을 정의할 수 있습니다

타겟팅 차원 선택 단계 중에는 호환되는 필터링 차원만 인터페이스에 제공됩니다.

이 두 차원은 관련되어 있어야 합니다. 따라서, **[!UICONTROL Filtering dimension]** 목록은 첫 번째 필드에 지정된 타겟팅 차원에 따라 다릅니다.

예를 들어 수신자(**수신자**)에서 다음 필터링 차원을 사용할 수 있습니다.

![](assets/query-filter-dimensions.png)

기간 **방문자 수**, 목록에는 다음 필터링 차원이 포함됩니다.

![](assets/query-filter-dimension-2.png)

## 쿼리 만들기 {#create-queries}

### 추가 데이터를 사용한 작업 {#select-data}

A **[!UICONTROL Query]** 활동을 통해 기본 데이터를 선택하여 대상 모집단을 작성할 수 있습니다. 이 작업에 대한 자세한 정보는 [이 섹션](query.md#create-a-query)을 참조하십시오.

다음 활동을 사용하여 데이터베이스에서 데이터를 쿼리하고 세분화할 수도 있습니다. [증분 쿼리](incremental-query.md), [목록 읽기](read-list.md).

워크플로우의 수명 주기 동안 전달 및 처리할 추가 데이터를 수집할 수 있습니다. 자세한 내용은 [데이터 추가](query.md#add-data) 및 [추가 데이터 편집](#edit-additional-data).

### 추가 데이터 편집 {#edit-additional-data}

데이터가 추가되면 편집하거나 사용하여 쿼리 활동에 정의된 타겟을 세분화할 수 있습니다.

다음 **[!UICONTROL Edit additional data...]** 링크를 사용하면 추가된 데이터를 보고 수정하거나 추가할 수 있습니다.

![](assets/edit-additional-data.png)

이전에 정의한 출력 열에 데이터를 추가하려면 사용 가능한 필드 목록에서 해당 데이터를 선택합니다. 새 출력 열을 만들려면 **[!UICONTROL Add]** 아이콘을 선택한 다음 필드를 선택하고 을(를) 클릭합니다 **[!UICONTROL Edit expression]**.

![](assets/query_add_an_output_column.png)

을(를) 클릭합니다. **고급 선택** 버튼을 클릭합니다.

![](assets/query_add_an_output_column_formula.png)

예를 들어 합계와 같이 추가할 필드에 대한 계산 모드를 정의합니다.

![](assets/query_add_aggregate.png)

다음 **[!UICONTROL Add a sub-item]** 옵션을 사용하면 계산된 데이터를 컬렉션에 첨부할 수 있습니다. 이를 통해 컬렉션에서 추가 데이터를 선택하거나 수집 요소에 대한 집계 계산을 정의할 수 있습니다.

하위 요소는 매핑된 컬렉션의 하위 트리에 표시됩니다.

컬렉션은 **[!UICONTROL Collections]** 하위 탭. 를 클릭하여 수집된 요소를 필터링할 수 있습니다 **[!UICONTROL Detail]** 선택한 컬렉션의 아이콘입니다. 필터 마법사를 사용하여 수집된 데이터를 선택하고 컬렉션의 데이터에 적용할 필터링 조건을 지정할 수 있습니다.

### 추가 데이터를 사용하여 타겟 세분화 {#refine-the-target-using-additional-data}

수집된 추가 데이터를 사용하면 데이터베이스에서 데이터 필터링을 세분화할 수 있습니다. 이렇게 하려면 **[!UICONTROL Refine the target using additional data...]** 링크: 이렇게 하면 추가된 데이터를 오버필터링할 수 있습니다.

![](assets/wf_add_data_use_additional_data.png)

### 데이터 균질화 {#homogenize-data}

in **[!UICONTROL Union]** 또는 **[!UICONTROL Intersection]** 유형 활동을 사용하면 데이터를 일관되게 유지하기 위해 공유된 추가 데이터만 유지하도록 선택할 수 있습니다. 이 경우 이 활동의 임시 출력 작업 테이블에는 모든 인바운드 집합에 있는 추가 데이터만 포함됩니다.

![](assets/use-common-add-data-only.png)

### 추가 데이터와 조정 {#reconciliation-with-additional-data}

데이터 조정 단계(**[!UICONTROL Union]**, **[!UICONTROL Intersection]**&#x200B;등 활동)을 만들 경우, 추가 열에서 데이터 조정에 사용할 열을 선택할 수 있습니다. 이렇게 하려면 선택한 열에 대한 조정을 구성하고 기본 세트를 지정합니다. 그런 다음 창의 아래 열에서 다음 예와 같이 열을 선택합니다.

![](assets/select-column-and-join.png)

표현식을 선택하고 확인합니다.

![](assets/select-column-and-join-2.png)


### 하위 집합 만들기 {#create-subsets}

다음 **[!UICONTROL Split]** 활동을 사용하면 추출 쿼리를 통해 정의된 기준에 하위 집합을 만들 수 있습니다. 각 하위 세트에 대해 모집단에서 필터 조건을 편집할 때 대상 세그먼테이션 조건을 정의할 수 있는 표준 쿼리 활동에 액세스합니다.

추가 데이터만 필터링 조건으로 사용하거나 타겟 데이터 외에 사용하여 대상을 여러 하위 집합으로 분할할 수 있습니다. 를 구입한 경우 외부 데이터를 사용할 수도 있습니다 **페더레이션 데이터 액세스** 선택 사항입니다.

이 작업에 대한 자세한 정보는 [이 섹션](#create-subsets-using-the-split-activity)을 참조하십시오.

## 세그먼트 데이터 {#segment-data}

### 여러 대상 결합(결합) {#combine-several-targets--union-}

결합 활동을 사용하면 하나의 전환 내에 여러 활동의 결과를 결합할 수 있습니다. 세트가 꼭 동질적이어야 할 필요는 없습니다.

![](assets/union-keys-only.png)

다음 데이터 조정 옵션을 사용할 수 있습니다.

* **[!UICONTROL Keys only]**

   입력 모집단이 동질적일 경우 이 옵션을 사용할 수 있습니다.

* **[!UICONTROL All columns in common]**

   이 옵션을 사용하면 타겟의 다양한 모집단에 공통되는 모든 열을 기준으로 데이터를 조정할 수 있습니다.

   Adobe Campaign은 해당 이름에 따라 열을 식별합니다. 허용한도 임계값은 다음과 같습니다. 예를 들어 &#39;이메일&#39; 열은 &#39;@email&#39; 열과 동일하게 인식될 수 있습니다.

* **[!UICONTROL A selection of columns]**

   데이터 조정을 적용할 열 목록을 정의하려면 이 옵션을 선택합니다.

   먼저 기본 세트(소스 데이터가 포함된 세트)를 선택한 다음 조인에 사용할 열을 선택합니다.

   ![](assets/join-reconciliation-options.png)

   >[!CAUTION]
   >
   >데이터 조정 중에 모집단은 중복 제거되지 않습니다.

   모집단 크기를 주어진 레코드 수로 제한할 수 있습니다. 이렇게 하려면 적절한 옵션을 클릭하고 보관할 레코드 수를 지정합니다.

   또한 인바운드 모집단의 우선 순위를 지정합니다. 창의 아래 섹션에는 결합 활동의 인바운드 전환이 나열되며 창 오른쪽의 파란색 화살표를 사용하여 정렬할 수 있습니다.

   레코드는 목록에서 첫 번째 인바운드 전환의 모집단에서 먼저 가져온 다음 최대값에 도달하지 않은 경우 두 번째 인바운드 전환의 모집단에서 가져옵니다.

   ![](assets/join_limit_nb_priority.png)

### 결합 데이터 추출(교차) {#extract-joint-data--intersection-}

![](assets/traitements.png)

교차 영역을 사용하면 인바운드 전환 모집단이 공유하는 라인만 복구할 수 있습니다. 이 활동은 결합 활동처럼 구성해야 합니다.

또한 선택한 열만 유지하거나 인바운드 모집단에 의해 공유된 열만 유지할 수 있습니다.

교차 활동은 [교차](intersection.md) 섹션을 참조하십시오.

### 모집단 제외(제외) {#exclude-a-population--exclusion-}

제외 활동을 사용하면 타겟의 요소를 다른 대상 모집단에서 제외할 수 있습니다. 이 활동의 출력 타깃팅 차원은 기본 세트의 차원이 됩니다.

필요한 경우 인바운드 테이블을 조작할 수 있습니다. 실제로 다른 차원에서 타겟을 제외하려면 이 타겟을 기본 타겟과 동일한 타겟팅 차원으로 반환해야 합니다. 이렇게 하려면 **[!UICONTROL Add]** 버튼을 클릭하고 차원 변경 조건을 지정합니다.

데이터 조정은 식별자, 축 변경 또는 조인을 통해 수행됩니다.

![](assets/exclusion-add-rule.png)

### 분할 활동을 사용하여 하위 집합 만들기 {#create-subsets-using-the-split-activity}

다음 **[!UICONTROL Split]** 활동은 하나 또는 여러 필터링 차원을 통해 필요한 만큼 많은 설정을 만들고, 하위 집합당 하나의 출력 전환 또는 고유한 전환을 생성할 수 있는 표준 활동입니다.

인바운드 전환에서 전달한 추가 데이터는 필터링 기준에 사용할 수 있습니다.

구성하려면 먼저 기준을 선택해야 합니다.

1. 워크플로우에서 **[!UICONTROL Split]** 활동.
1. 에서 **[!UICONTROL General]** 탭에서 원하는 옵션을 선택합니다. **[!UICONTROL Use data from the target and additional data]**, **[!UICONTROL Use the additional data only]** 또는 **[!UICONTROL Use external data]**.
1. 만약 **[!UICONTROL Use data from the target and additional data]** 선택 사항이 선택되면 타겟팅 차원을 사용하면 인바운드 전환에서 전달한 모든 데이터를 사용할 수 있습니다.

   ![](assets/split-general-tab-options.png)

   하위 세트를 만들면 위의 필터링 매개 변수가 사용됩니다.

   필터링 조건을 정의하려면 **[!UICONTROL Add a filtering condition on the inbound population]** 옵션을 선택하고 **[!UICONTROL Edit...]** 링크를 클릭합니다. 그런 다음 이 하위 집합을 만들기 위한 필터링 조건을 지정합니다.

   ![](assets/split-subset-config-all-data.png)

   에서 필터링 조건을 사용하는 방법을 보여주는 예 **[!UICONTROL Split]** 타겟을 다른 모집단으로 세분화하는 활동은 다음과 같이 설명되어 있습니다. [이 섹션](cross-channel-delivery-workflow.md).

   다음 **[!UICONTROL Label]** 필드에서는 새로 만든 하위 세트에 아웃바운드 전환과 일치하는 이름을 지정할 수 있습니다.

   하위 세트에 세그먼트 코드를 할당하여 식별하고 해당 모집단을 타겟팅하는 데 사용할 수도 있습니다.

   필요한 경우 만들려는 각 하위 세트에 대해 개별적으로 타겟팅 및 필터링 차원을 변경할 수 있습니다. 이렇게 하려면 하위 집합의 필터링 조건을 편집하고 을(를) 확인합니다. **[!UICONTROL Use a specific filtering dimension]** 선택 사항입니다.

   ![](assets/split-subset-config-specific-filtering.png)

1. 만약 **[!UICONTROL Use the additional data only]** 옵션을 선택하면 하위 집합 필터링에 추가 데이터만 제공됩니다.

1. 만약 **페더레이션 데이터 액세스** 옵션이 활성화되어 있으면 **[!UICONTROL Use external data]** 이미 구성된 외부 데이터베이스에서 데이터를 처리하거나 데이터베이스에 대한 새 연결을 만들 수 있습니다.

그런 다음 새 하위 세트를 추가해야 합니다.

1. 을(를) 클릭합니다. **[!UICONTROL Add]** 을 클릭하고 필터링 조건을 정의합니다.

   ![](assets/wf_split_add_a_tab.png)

1. 에서 필터링 차원을 정의합니다 **[!UICONTROL General]** 활동의 탭(위 참조). 기본적으로 모든 하위 집합에 적용됩니다.

   ![](assets/wf_split_edit_filtering.png)

1. 필요한 경우 각 하위 세트에 대한 필터링 차원을 개별적으로 변경할 수 있습니다. 이렇게 하면 모든 골드 카드 보유자에 대한 세트를 만들 수 있습니다. 마지막 뉴스레터를 클릭한 모든 수신자에 대해 1개씩, 지난 30일 이내에 매장 내 구매를 한 18세에서 25세 사이의 사람들에게 모두 동일한 분할 활동을 사용하여 1개씩 만들 수 있습니다. 이렇게 하려면 **[!UICONTROL Use a specific filtering dimension]** 옵션을 선택하고 데이터 필터링 컨텍스트를 선택합니다.

하위 세트가 만들어지면 기본적으로 분할 활동에는 하위 세트만큼 출력 전환이 표시됩니다.

![](assets/wf_split_multi_outputs.png)

이러한 모든 하위 세트를 하나의 출력 전환으로 그룹화할 수 있습니다. 이 경우 각 하위 세트에 대한 링크는 세그먼트 코드에 표시됩니다(예: ). 이렇게 하려면 **[!UICONTROL Generate all subsets in the same table]** 선택 사항입니다.

![](assets/wf_split_single_output.png)

예를 들어 단일 게재 활동을 배치하고 각 수신자 세트의 세그먼트 코드를 기반으로 게재 콘텐츠를 개인화할 수 있습니다.


하위 집합은 **[!UICONTROL Cells]** 활동. 자세한 내용은 [셀](cells.md) 섹션을 참조하십시오.

### 타겟팅된 데이터 사용 {#using-targeted-data}

데이터가 식별되고 준비되면 다음 컨텍스트에서 사용할 수 있습니다.

* 다양한 워크플로우 단계에서 데이터 조작에 따라 데이터베이스의 데이터를 업데이트할 수 있습니다.

   자세한 내용은 [데이터 업데이트](update-data.md).

* 기존 목록의 내용을 새로 고칠 수도 있습니다.

   자세한 내용은 [목록 업데이트](list-update.md).

* 워크플로우에서 직접 게재를 준비하거나 시작할 수 있습니다.

   자세한 내용은 [배달](delivery.md), [게재 제어](delivery-control.md) 및 [지속적인 게재](continuous-delivery.md).

## 데이터 관리 {#data-management}

Adobe Campaign에서 데이터 관리는 보다 효율적이고 유연한 도구를 제공하여 복잡한 타깃팅 문제를 해결하는 활동 집합을 결합합니다. 이를 통해 계약, 구독, 게재 반응성 등과 관련된 정보를 사용하여 연락처와 모든 커뮤니케이션을 일관성 있게 관리할 수 있습니다. 데이터 관리를 사용하면 세분화 작업 중 특히 다음의 데이터 라이프 사이클을 추적할 수 있습니다.

* 데이터 마트에서 모델링되지 않은 데이터를 포함하여 타겟팅 프로세스를 단순화 및 최적화(새 테이블 만들기: 구성에 따라 각 타겟팅 워크플로우에 대한 로컬 확장).
* 특히 타겟 구성 단계 또는 데이터베이스 관리 동안 버퍼 계산 보관 및 전달
* 외부 베이스 액세스(선택 사항): 타겟팅 프로세스 중에 고려된 다른 유형의 데이터베이스

Adobe Campaign에서는 이러한 작업을 구현하기 위해 다음을 제공합니다.

* 데이터 수집 활동: [파일 전송](file-transfer.md), [데이터 로드(파일)](data-loading--file-.md), [데이터 로드(RDBMS)](data-loading--rdbms-.md), [데이터 업데이트](update-data.md). 데이터를 수집하는 이 첫 번째 단계는 데이터를 다른 활동에서 처리할 수 있도록 준비합니다. 워크플로우가 올바르게 실행되고 예상 결과를 제공하기 위해 몇 가지 매개 변수를 모니터링해야 합니다. 예를 들어 데이터를 가져올 때 이 데이터의 기본 키(Pkey)는 각 레코드에 대해 고유해야 합니다.
* 데이터 관리 옵션으로 보강된 타겟팅 활동: [쿼리](query.md), [결합](union.md), [교차](intersection.md), [분할](split.md). 이렇게 하면 데이터 조정이 가능한 한 여러 다른 타겟팅 차원의 데이터 간의 결합 또는 교차를 구성할 수 있습니다.
* 데이터 변환 활동: [데이터 보강](enrichment.md), [차원 변경](change-dimension.md).

>[!CAUTION]
>
>두 개의 워크플로우가 연결되어 있을 때 소스 테이블 요소를 삭제하면 여기에 연결된 모든 데이터가 삭제되지 않습니다.
>  
>예를 들어 워크플로우를 통해 수신자를 삭제해도 수신자의 게재 기록이 모두 삭제되지 않습니다. 그러나 &#39;수신자&#39; 폴더에서 직접 수신자를 삭제하면 이 수신자와 연결된 모든 데이터가 삭제됩니다.

### 데이터 보강 및 수정 {#enrich-and-modify-data}

타겟팅 차원 외에도 필터링 차원을 사용하면 수집된 데이터의 특성을 지정할 수 있습니다. [이 섹션](targeting-workflows.md#targeting-and-filtering-dimensions)을 참조하십시오.

식별되고 수집된 데이터는 보강, 집계 및 조작하여 대상 구성을 최적화할 수 있습니다. 이렇게 하려면 다음에 자세히 설명된 데이터 조작 활동 외에 [이 섹션](#segmen-data)를 채울 때는 다음을 사용합니다.

* 다음 **[!UICONTROL Enrichment]** 활동을 사용하면 스키마에 열을 잠시 추가할 수 있을 뿐만 아니라 특정 요소에 정보를 추가할 수 있습니다. 세부 사항은 [데이터 보강](enrichment.md) 활동 저장소의 섹션을 참조하십시오.
* 다음 **[!UICONTROL Edit schema]** 활동을 통해 스키마 구조를 수정할 수 있습니다. 세부 사항은 [스키마 편집](edit-schema.md) 활동 저장소의 섹션을 참조하십시오.
* 다음 **[!UICONTROL Change dimension]** 활동을 사용하면 타겟 구성 주기 동안 타겟팅 차원을 변경할 수 있습니다. 세부 사항은 [차원 변경](change-dimension.md) 섹션을 참조하십시오.
