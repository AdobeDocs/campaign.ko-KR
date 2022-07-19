---
product: campaign
title: 캠페인 시뮬레이션 시작
description: 캠페인 시뮬레이션을 구성하는 방법 알아보기
feature: Campaigns
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# 캠페인 시뮬레이션{#campaign-simulations}

캠페인 최적화를 사용하면 시뮬레이션을 사용하여 캠페인 계획의 효율성을 테스트할 수 있습니다. 이를 통해 캠페인의 잠재적인 성공을 측정할 수 있습니다. 적용된 유형화 규칙 등을 기반으로 생성된 매출, 타겟 볼륨

시뮬레이션을 사용하면 게재의 영향을 모니터링하고 비교할 수 있습니다.

## 시뮬레이션 설정 {#set-up-a-simulation}

### 주의


에서 준비한 게재 **테스트** 분산 마케팅에서 캠페인을 평가할 때 또는 임시 달력에서 게재가 예약되지 않은 한 모드는 서로 영향을 주지 않습니다.

즉, 압력 및 용량 규칙은 **[!UICONTROL Target estimation and message personalization]** 모드. 전달 위치 **[!UICONTROL Estimation and approval of the provisional target]** 모드 및 **[!UICONTROL Target evaluation]** 모드가 고려되지 않습니다.

게재 모드는 **[!UICONTROL Typology]** 게재 속성의 하위 탭.

![](assets/simu_campaign_select_delivery_mode.png)


### 시뮬레이션 만들기 {#create-a-simulation}

시뮬레이션을 만들려면 다음 단계를 적용합니다.

1. 를 엽니다. **[!UICONTROL Campaigns]** 탭에서 **[!UICONTROL More]** 링크 내 **[!UICONTROL Create]** 섹션을 선택하고 을(를) 선택합니다. **[!UICONTROL Simulation]** 선택 사항입니다.

   ![](assets/simu_campaign_opti_01.png)

1. 템플릿과 시뮬레이션 이름을 입력합니다. 클릭 **[!UICONTROL Save]** 시뮬레이션을 만들려면

   ![](assets/simu_campaign_opti_02.png)

1. 을(를) 클릭합니다. **[!UICONTROL Edit]** 탭을 클릭하여 구성합니다.

   ![](assets/simu_campaign_opti_edit.png)

1. 에서 **[!UICONTROL Scope]** 탭에서 이 시뮬레이션에 고려할 게재를 지정합니다. 이렇게 하려면 **[!UICONTROL Add]** 버튼을 클릭하고 고려할 게재 선택 모드를 지정합니다.

   ![](assets/simu_campaign_opti_edit_scope.png)

   각 게재를 하나씩 선택하거나 캠페인, 프로그램 또는 계획별로 정렬할 수 있습니다.

   >[!NOTE]
   >
   >계획, 프로그램 또는 캠페인을 통해 게재를 선택하는 경우, Adobe Campaign에서는 시뮬레이션이 시작될 때마다 고려하도록 게재 목록을 자동으로 새로 고칠 수 있습니다. 이렇게 하려면 **[!UICONTROL Refresh the selection of deliveries each time the simulation is started]** 선택 사항입니다.
   >  
   >이렇게 하지 않으면 시뮬레이션을 만들 때 계획, 프로그램 또는 캠페인에서 사용할 수 없는 게재는 고려되지 않습니다. 나중에 추가된 게재는 무시됩니다.

   ![](assets/simu_campaign_opti_edit_scope_update.png)

1. 시뮬레이션 범위에 포함할 요소를 선택합니다. 필요한 경우 Shift 및 Ctrl 키를 사용하여 여러 요소를 선택합니다.

   ![](assets/simu_campaign_opti_edit_scope_select.png)

   클릭 **[!UICONTROL Finish]** 을 눌러 선택 사항을 승인합니다.

   계획, 프로그램 또는 캠페인에 속하는 선택된 게재와 게재를 수동으로 결합할 수 있습니다.

   ![](assets/simu_campaign_opti_edit_scope_save.png)

   필요한 경우 **[!UICONTROL Edit the dynamic condition...]** 링크를 클릭합니다.

   클릭 **[!UICONTROL Save]** 이 구성을 승인하려면 다음을 수행하십시오.

   >[!NOTE]
   >
   >시뮬레이션(상태: **Target 준비** 또는 **제공 준비**).

1. 에서 **[!UICONTROL Calculations]** 탭에서 예를 들어 수신자 스키마와 같은 분석 차원을 선택합니다.

   ![](assets/simu_campaign_opti_dimension.png)

1. 그런 다음 표현식을 추가할 수 있습니다.

   ![](assets/simu_campaign_opti_dimension_02.png)

### 실행 설정 {#execution-settings}

다음 **[!UICONTROL General]** 시뮬레이션의 탭에서 실행 설정을 입력할 수 있습니다.

* 다음 **[!UICONTROL Schedule execution for down-time]** 선택 사항을 사용하면 선택한 우선순위 수준에 따라 시뮬레이션 실행을 덜 바쁜 기간으로 정의합니다. 시뮬레이션은 중요한 데이터베이스 리소스를 사용하므로, 예를 들어, 야간 시뮬레이션을 실행하도록 예약해야 합니다.
* 다음 **[!UICONTROL Priority]** 은 트리거가 지연되도록 시뮬레이션에 적용되는 수준입니다.
* **[!UICONTROL Save SQL queries in the log]**. SQL 로그를 사용하면 시뮬레이션이 오류로 끝나는 경우 진단할 수 있습니다. 또한 시뮬레이션이 너무 느린 이유를 확인하는 데 도움이 될 수 있습니다. 다음 메시지는 의 시뮬레이션 후에 표시됩니다 **[!UICONTROL SQL logs]** 의 하위 탭 **[!UICONTROL Audit]** 탭.

## 시뮬레이션 실행 {#execute-a-simulation}

### 시뮬레이션 시작 {#start-a-simulation}

시뮬레이션 범위가 정의되면 실행할 수 있습니다.

이렇게 하려면 시뮬레이션 대시보드를 열고 을(를) 클릭합니다 **[!UICONTROL Start simulation]**.

![](assets/simu_campaign_opti_start.png)

실행이 완료되면 시뮬레이션을 열고 **[!UICONTROL Results]** 탭하여 각 게재에 대해 계산된 타겟을 볼 수 있습니다.

![](assets/simu_campaign_opti_results.png)

1. 다음 **[!UICONTROL Deliveries]** 하위 탭에는 시뮬레이션에서 고려하는 모든 게재가 나열됩니다. 두 가지 카운트가 표시됩니다.

   * 다음 **[!UICONTROL Initial count]** 은 게재에서 예상 중에 계산된 목표입니다.
   * 다음 **[!UICONTROL Final count]** 은 시뮬레이션 후 계산되는 수신자 수입니다.

      초기 및 최종 수의 차이는 시뮬레이션 전에 구성된 다양한 규칙 또는 필터의 적용을 반영합니다.

      이 계산에 대해 자세히 알아보려면 **[!UICONTROL Exclusions]** 하위 탭.

1. 다음 **[!UICONTROL Exclusions]** 하위 탭에서는 제외 분류를 볼 수 있습니다.

   ![](assets/simu_campaign_opti_14.png)

1. 다음 **[!UICONTROL Alerts]** 하위 탭에서는 시뮬레이션 중에 생성된 모든 경고 메시지를 그룹화합니다. 용량 과부하 시 경고 메시지를 보낼 수 있습니다(타겟팅된 수신자 수가 설정된 용량을 초과하는 경우 등).
1. 다음 **[!UICONTROL Exploration of the exclusions]** 하위 탭에서는 결과 분석 테이블을 만들 수 있습니다. 사용자는 abscissa/ordinates 축에 변수를 표시해야 합니다.

   분석 테이블 만들기의 예는 의 끝을 참조하십시오 [이 섹션](#explore-results).

### 결과 보기 {#view-results}

#### 감사 {#audit}

다음 **[!UICONTROL Audit]** 탭에서 시뮬레이션 실행을 모니터링할 수 있습니다. 다음 **[!UICONTROL SQL Logs]** 하위 탭은 전문가 사용자에게 유용합니다. SQL 형식의 실행 로그가 나열됩니다. 이러한 로그는 **[!UICONTROL Save SQL queries in the log]** 선택 사항이 **[!UICONTROL General]** 탭으로 시뮬레이션 실행 전.

![](assets/simu_campaign_opti_11.png)

#### 결과 탐색 {#explore-results}

다음 **[!UICONTROL Exploration of the exclusions]** 하위 탭에서는 시뮬레이션으로 인한 데이터를 분석할 수 있습니다.

<!--
Descriptive analysis is detailed in [this section](../../reporting/using/about-adobe-campaign-reporting-tools.md).
-->

## 시뮬레이션 결과 {#results-of-a-simulation}

의 지표 **[!UICONTROL Log]** 및 **[!UICONTROL Results]** 탭은 시뮬레이션 결과에 대한 첫 번째 개요를 제공합니다. 자세한 결과 보기를 보려면 **[!UICONTROL Reports]** 탭.

### 보고서 {#reports}

시뮬레이션 결과를 분석하려면 보고서를 편집합니다. 제외 및 원인을 표시합니다.

기본적으로 다음 보고서가 제공됩니다.

* **[!UICONTROL Detail of simulation exclusions]** : 이 보고서는 관련된 모든 게재에 대한 제외 원인 세부 차트를 제공합니다.
* **[!UICONTROL Simulation summary]** : 이 보고서는 다양한 게재에서 시뮬레이션에서 제외된 모집단을 보여줍니다.
* **[!UICONTROL Summary of exclusions linked to the simulation]** : 이 보고서는 적용된 유형화 규칙과 함께 시뮬레이션에 의한 제외 차트와 규칙당 제외 비율을 보여주는 차트를 보여줍니다.

<!--
>[!NOTE]
>
>You can create new reports and add them to the ones offered. For more on this, refer to [this section](../../reporting/using/about-adobe-campaign-reporting-tools.md).
-->

보고서에 액세스하려면 **[!UICONTROL Reports]** 대시보드를 통해 타깃팅된 시뮬레이션의 링크입니다.

![](assets/campaign_opt_reporting_edit_from_board.png)

보고서를 **[!UICONTROL Reports]** 시뮬레이션 대시보드에서 액세스할 수 있는 링크.

### 시뮬레이션 비교 {#compare-simulations-}

시뮬레이션이 실행될 때마다 이전 결과가 바뀝니다. 한 실행의 결과를 표시하고 다른 실행과 비교할 수 없습니다.

결과를 비교하려면 보고서를 사용해야 합니다. 실제로 Adobe Campaign을 사용하면 보고서 기록을 저장하여 나중에 다시 볼 수 있습니다. 이 기록은 시뮬레이션의 라이프 사이클 전체에서 저장됩니다.

**예제:**

1. 유형화를 유형화하는 게재에 대한 시뮬레이션 만들기 **A** 에 적용됩니다.
1. 에서 **[!UICONTROL Reports]** 탭에서 사용 가능한 보고서(예: **[!UICONTROL Detail of simulation exclusions]** 예.
1. 보고서의 오른쪽 위 섹션에서 아이콘을 클릭하여 새 내역을 만듭니다.

   ![](assets/campaign_opt_reporting_create_hist.png)

1. 시뮬레이션을 닫고 유형화 구성을 변경합니다 **A**.
1. 시뮬레이션을 다시 실행하고 기록을 생성한 보고서에 표시된 결과와 결과를 비교합니다.

   ![](assets/campaign_opt_reporting_edit_hist.png)

   필요한 만큼 보고서 기록을 저장할 수 있습니다.

### 보고 축 {#reporting-axes}

다음 **[!UICONTROL Calculations]** 탭에서 타겟에서 보고 축을 정의할 수 있습니다. 다음 축이 [결과 분석](#explore-results).

>[!NOTE]
>
>각 시뮬레이션에 대해 개별적으로 정의하지 않고 시뮬레이션 템플릿에서 계산 축을 정의하는 것이 좋습니다.\
>시뮬레이션 템플릿은 **[!UICONTROL Resources > Templates > Simulation templates]** 노드 아래에 나열된 상태로 남아 있습니다.

**예제:**

아래 예에서는 수신자의 상태(&quot;고객&quot;, &quot;잠재 고객&quot; 또는 없음)를 기반으로 추가 보고 축을 생성하려고 합니다.

1. 보고 축을 정의하려면 **[!UICONTROL Analysis dimension]** 필드. 이 정보는 필수입니다.
1. 여기에서는 수신자 테이블의 세그먼트 필드를 선택하려고 합니다.

   ![](assets/simu_campaign_opti_09.png)

1. 다음 옵션을 사용할 수 있습니다.

   * **[!UICONTROL Generate target overlap statistics]** 시뮬레이션 보고서에서 모든 중복 통계를 복구할 수 있습니다. 중복은 하나의 시뮬레이션 내에서 두 개 이상의 게재에서 타겟팅된 수신자입니다.

      >[!CAUTION]
      >
      >이 옵션을 선택하면 시뮬레이션 실행 시간이 크게 늘어납니다.

   * **[!UICONTROL Keep the simulation work table]** 시뮬레이션 추적을 유지할 수 있습니다.

      >[!CAUTION]
      >
      >이러한 테이블을 자동으로 저장하려면 상당한 스토리지 용량이 필요합니다. 데이터베이스가 충분한지 확인합니다.

시뮬레이션 결과가 표시되면 선택한 표현식에 대한 정보가 **[!UICONTROL Overlaps]** 하위 탭.

게재 대상이 겹치면 시뮬레이션의 두 개 이상의 게재에서 타겟팅된 수신자가 겹칩니다.

![](assets/simu_campaign_opti_13.png)

>[!NOTE]
>
>이 하위 탭은 **[!UICONTROL Generate target recovery statistics]** 옵션이 활성화되었습니다.

보고 축에 대한 정보는 **[!UICONTROL Exploring exclusions]** 하위 탭. [자세히 알아보기](#explore-results)
