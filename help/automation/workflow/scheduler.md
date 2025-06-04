---
product: campaign
title: 예약
description: 예약 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 8%

---

# 예약 {#scheduler}



**스케줄러**&#x200B;은(는) 예약에 지정된 시간에 전환을 활성화하는 영구 작업입니다.

**[!UICONTROL Scheduler]** 활동은 시작을 예약하는 것으로 생각해야 합니다. 차트 내에서의 활동 위치 지정 규칙은 **[!UICONTROL Start]** 활동과 동일합니다. 이 활동에는 인바운드 전환이 없어야 합니다.

## 모범 사례 {#best-practices}

**스케줄러 타이밍을 변경한 후 워크플로우를 다시 시작** - **[!UICONTROL Scheduler]** 활동의 예약된 시간을 변경할 때 워크플로우를 다시 시작하는 것이 중요합니다. 이렇게 하면 워크플로우가 업데이트된 시간에 실행됩니다. 다시 시작하지 않으면 워크플로우는 이전 일정에 따라 계속 실행됩니다.

**스케줄러 빈도 제한** - 15분마다 더 자주 실행되도록 워크플로우를 예약하지 마십시오. 실행 빈도가 증가하면 시스템 성능이 저하되고 데이터베이스가 정체될 수 있습니다.

**분기당 하나의 일정을 사용** - 워크플로우의 각 분기에는 하나의 **[!UICONTROL Scheduler]** 활동만 있어야 합니다. 워크플로우에서 활동을 사용하는 모범 사례에 대한 자세한 내용은 [워크플로우 모범 사례 페이지](workflow-best-practices.md#using-activities)를 참조하세요.

**워크플로우 동시 실행 방지** - 워크플로우가 스케줄러에 의해 트리거되는 경우 워크플로우의 여러 인스턴스가 동시에 실행될 수 있음을 유의하십시오. 예를 들어 스케줄러가 매시간마다 워크플로우를 트리거하지만 워크플로우 실행이 한 시간 이상 걸리는 경우 실행이 중복될 수 있습니다. 이 문제를 방지하려면 여러 개의 동시 실행을 방지하는 확인 설정을 고려하십시오. [동시 여러 워크플로우 실행을 방지하는 방법을 알아봅니다](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

**지연된 전환에 대한 계정** - 워크플로우가 장기 실행 작업(가져오기 등)을 실행 중이거나 wfserver 모듈이 일시적으로 중지된 경우 스케줄러에 의해 트리거된 전환이 지연될 수 있습니다. 이를 완화하려면 스케줄러의 활성화 시간을 제한하여 작업이 정의된 시간 범위 내에서 실행되도록 합니다.

## 스케줄러 활동 구성 {#configuring-scheduler-activity}

스케줄러는 전환의 활성화 일정을 정의합니다. 이를 구성하려면 그래픽 개체를 두 번 클릭한 다음 **[!UICONTROL Change...]**&#x200B;을(를) 클릭합니다

![](assets/s_user_segmentation_scheduler.png)

마법사를 사용하여 활동의 빈도와 유효 기간을 정의할 수 있습니다. 구성 단계는 다음과 같습니다.

1. 활성화 빈도를 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.

   ![](assets/s_user_segmentation_scheduler2.png)

1. 활성화 시간 및 일을 지정합니다. 이 단계의 매개 변수는 이전 단계에서 선택한 빈도에 따라 다릅니다. 하루에 여러 번 활동을 시작하도록 선택하는 경우 구성 옵션은 다음과 같습니다.

   ![](assets/s_user_segmentation_scheduler3.png)

1. 일정의 유효 기간을 정의하거나 실행할 횟수를 지정합니다.

   ![](assets/s_user_segmentation_scheduler4.png)

1. 구성을 확인하고 **[!UICONTROL Finish]**&#x200B;을(를) 클릭하여 저장합니다.

   ![](assets/s_user_segmentation_scheduler5.png)
