---
product: campaign
title: 반복 및 정기 캠페인 만들기
description: 반복 및 정기 캠페인을 만들고 실행하는 방법에 대해 알아봅니다
feature: Campaigns, Cross Channel Orchestration, Programs
role: User
exl-id: 68c5b903-5043-4e74-b3f6-90a7f2fb3b9a
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---

# 반복 및 정기 캠페인 {#recurring-and-periodic-campaigns}

A **반복 캠페인** 연결된 일정에 따라 워크플로우를 실행하도록 구성된 특정 템플릿을 기반으로 하는 캠페인입니다. 타겟팅은 각 실행에 대해 복제되며, 다양한 프로세스 및 타겟 모집단을 추적합니다.  구성이 완료되면 반복 캠페인은 워크플로 템플릿을 복제하여 새 워크플로를 자동으로 만들고 실행합니다. 예를 들어 대상 세그먼트에 월별 미리 알림을 보내야 하는 경우 매년 초에 월별 하나씩 12개의 워크플로우를 만들도록 반복 캠페인을 구성합니다. [자세히 알아보기](#create-a-recurring-campaign)

A **정기 캠페인** 는 실행 일정에 따라 캠페인 인스턴스를 만들 수 있는 특정 템플릿을 기반으로 하는 캠페인입니다. 캠페인 인스턴스는 템플릿 일정에 정의된 빈도에 따라 정기 캠페인 템플릿을 기반으로 자동으로 생성됩니다. [자세히 알아보기](#create-a-periodic-campaign)

## 반복 캠페인 만들기 {#create-a-recurring-campaign}

반복 캠페인은 실행할 워크플로우 템플릿 및 실행 일정을 정의하는 특정 템플릿에서 만들어집니다.

### 반복 캠페인용 템플릿 만들기 {#create-the-campaign-template}

반복 캠페인용 템플릿을 만들려면 아래 단계를 수행하십시오.

1. Campaign 탐색기를 열고 다음으로 이동 **[!UICONTROL Resources > Templates > Campaign templates]**.
1. 기본 제공 복제 **[!UICONTROL Recurring campaign]** 템플릿.
   ![](assets/recurring-campaign-duplicate.png)
1. 템플릿 이름과 캠페인 기간을 입력합니다.
1. 이 유형의 캠페인의 경우 **[!UICONTROL Schedule]** 템플릿 실행 일정을 만들기 위해 탭이 추가됩니다. 이 탭을 사용하여 이 템플릿을 기반으로 하는 캠페인의 실행 날짜를 정의합니다.
   ![](assets/recurring-campaign-schedule.png)

   실행 일정의 구성 모드는 **[!UICONTROL Scheduler]** 워크플로우의 개체입니다. [자세히 알아보기](../workflow/scheduler.md)

   >[!CAUTION]
   >
   >실행 일정 구성은 신중하게 수행해야 합니다. 반복 캠페인은 지정된 일정에 따라 템플릿의 워크플로우를 복제합니다. 이 작업을 수행하면 데이터베이스가 오버로드될 수 있습니다.

1. 에서 값 지정 **[!UICONTROL Create in advance for]** 지정된 기간 동안 해당 워크플로우를 만들기 위한 필드입니다.
1. 다음에서 **[!UICONTROL Targeting and workflows]** 탭에서 이 템플릿을 기반으로 캠페인에 사용할 워크플로우 템플릿을 디자인합니다. 이 워크플로는 일반적으로 타겟팅 매개 변수와 하나 이상의 게재를 포함합니다.

   >[!NOTE]
   >
   >이 워크플로는 반복 워크플로 템플릿으로 저장해야 합니다. 이렇게 하려면 워크플로우 속성을 편집하고 **[!UICONTROL Recurring workflow template]** 의 옵션 **[!UICONTROL Execution]** 탭.

   ![](assets/recurring-campaign-wf-properties.png)

### 반복 캠페인 만들기 {#create-the-recurring-campaign}

반복 캠페인을 만들고 템플릿에 정의된 일정에 따라 워크플로우를 실행하려면 다음을 수행해야 합니다.

1. 반복 캠페인 템플릿을 기반으로 새 캠페인을 만듭니다.
1. 워크플로우 실행 일정 을 **[!UICONTROL Schedule]** 탭. 캠페인 일정을 사용하면 각 라인에 대해 자동 워크플로우 생성 또는 실행 시작 날짜를 입력할 수 있습니다.

   각 행에 대해 다음과 같은 추가 옵션을 추가할 수 있습니다.

   * 활성화 **[!UICONTROL To be approved]** 워크플로우에서 게재 승인 요청을 강제 적용하는 옵션.
   * 활성화 **[!UICONTROL To be started]** 시작 날짜에 도달하면 워크플로를 시작하는 옵션입니다.

   다음 **[!UICONTROL Create in advance for]** 필드를 사용하면 입력한 기간을 다루는 모든 워크플로우를 만들 수 있습니다.

   실행 시 **[!UICONTROL Jobs on campaigns]** 워크플로우 - 전용 워크플로우가 캠페인 스케줄에 정의된 발생 횟수를 기반으로 만들어집니다. 따라서 워크플로우는 각 실행 날짜에 대해 생성됩니다.

1. 반복 워크플로우는 캠페인에 있는 워크플로 템플릿에서 자동으로 만들어집니다. 다음에서 볼 수 있습니다. **[!UICONTROL Targeting and workflows]** 캠페인의 탭.

   ![](assets/recurring-wf-created.png)

   반복 워크플로우 인스턴스의 레이블은 템플릿 레이블과 워크플로우 번호로 구성되며 # 문자는 그 사이에 있습니다.

   일정에서 생성된 워크플로는에서 워크플로와 자동으로 연결됩니다. **[!UICONTROL Workflow]** 열 **[!UICONTROL Schedule]** 탭.

   ![](assets/recurring-wf-schedule-executed.png)

   이 탭에서 각 워크플로우를 편집할 수 있습니다.

   >[!NOTE]
   >
   >워크플로우와 연관된 일정 라인의 시작 일자는 다음 구문과 함께 워크플로우의 변수에서 사용할 수 있습니다.\
   >`$date(instance/vars/@startPlanningDate)`

## 정기 캠페인 만들기 {#create-a-periodic-campaign}

정기 캠페인은 실행 일정에 따라 캠페인 인스턴스를 만들 수 있는 특정 템플릿을 기반으로 하는 캠페인입니다. 캠페인 인스턴스는 템플릿 일정에 정의된 빈도에 따라 정기 캠페인 템플릿을 기반으로 자동으로 생성됩니다.

### 캠페인 템플릿 만들기 {#create-the-campaign-template-1}

1. Campaign 탐색기를 열고 다음으로 이동 **[!UICONTROL Resources > Templates > Campaign templates]**.
1. 기본 제공 복제 **[!UICONTROL Periodic campaign]** 템플릿.
1. 템플릿의 속성을 입력합니다.

   >[!NOTE]
   >
   >템플릿이 할당된 운영자는 선택한 프로그램에서 캠페인을 만들 수 있는 적절한 권한이 있어야 합니다.

1. 이 템플릿과 연결된 워크플로우를 만듭니다. 이 워크플로우는 템플릿으로 만든 모든 정기 캠페인에서 복제됩니다.

   >[!NOTE]
   >
   >이 워크플로는 워크플로 템플릿입니다. 캠페인 템플릿에서 실행할 수 없습니다.

1. 반복 캠페인 템플릿에 대한 실행 일정을 완료합니다. 다음을 클릭하십시오. **[!UICONTROL Add]** 버튼을 클릭하고 시작 및 종료 날짜를 정의하거나 링크를 통해 실행 일정을 입력합니다.

   >[!CAUTION]
   >
   >정기 캠페인 템플릿은 위에 정의된 일정에 따라 새 캠페인을 만듭니다. 따라서 Adobe Campaign 데이터베이스를 오버로드할 수 없도록 신중하게 완료해야 합니다.

1. 실행 시작 날짜에 도달하면 일치하는 캠페인이 자동으로 만들어집니다. 템플릿의 모든 특성을 사용합니다.

   각 캠페인은 템플릿 일정을 통해 편집할 수 있습니다.

   각 정기 캠페인에는 동일한 요소가 포함되어 있습니다. 생성되면 표준 캠페인으로 관리됩니다.
