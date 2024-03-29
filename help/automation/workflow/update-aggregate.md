---
product: campaign
title: 집계 업데이트
description: 업데이트 집계 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# 집계 업데이트{#update-aggregate}

다음에 정의된 집계 [큐브](../../v8/reporting/gs-cubes.md) 보고 목적으로 특정 활동으로 업데이트할 수 있습니다. A **[!UICONTROL Workflow]** 합계를 구성할 때 탭을 사용할 수 있습니다.

에서 큐브 및 합계에 대해 자세히 알아봅니다. [이 섹션](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

합계를 업데이트하려면 **[!UICONTROL Update aggregate]** 활동을 참조하고 업데이트할 큐브와 합계를 선택합니다.

다음을 구성할 수 있습니다. **전체 업데이트** 또는 **부분 업데이트**.

![](assets/update-aggregate-details.png)

기본적으로 각 계산 중에 전체 업데이트가 실행됩니다. 부분 업데이트를 활성화하려면 옵션을 선택하고 업데이트 조건을 정의합니다.

![](assets/update-aggregate-partial.png)

를 추가하는 것이 좋습니다. **[!UICONTROL Scheduler]** 계산 업데이트 빈도를 설정하는 활동.
