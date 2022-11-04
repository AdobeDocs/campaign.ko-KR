---
product: campaign
title: 집계 업데이트
description: 업데이트 집계 워크플로우 활동에 대해 자세히 알아보십시오
feature: Workflows
role: Data Engineer
level: Beginner
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# 집계 업데이트{#update-aggregate}

에 정의된 합계 [큐브](../../v8/reporting/gs-cubes.md) 보고 목적으로 특정 활동으로 업데이트할 수 있습니다. A **[!UICONTROL Workflow]** 합계를 구성할 때 탭을 사용할 수 있습니다.

의 큐브 및 집계에 대해 자세히 알아보십시오 [이 섹션](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

집계를 업데이트하려면 **[!UICONTROL Update aggregate]** 활동을 선택하고 업데이트할 큐브와 합계를 선택합니다.

을(를) 구성할 수 있습니다 **전체 업데이트** 또는 **부분 업데이트**.

![](assets/update-aggregate-details.png)

기본적으로 각 계산 중에 전체 업데이트가 실행됩니다. 부분 업데이트를 활성화하려면 옵션을 선택하고 업데이트 조건을 정의합니다.

![](assets/update-aggregate-partial.png)

좋은 방법은 **[!UICONTROL Scheduler]** 활동을 사용하여 계산 업데이트 빈도를 설정합니다.
