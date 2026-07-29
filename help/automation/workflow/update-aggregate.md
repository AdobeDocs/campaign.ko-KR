---
product: campaign
title: 집계 업데이트
description: 업데이트 집계 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 108
ht-degree: 3%

---

# 집계 업데이트{#update-aggregate}

보고용으로 [큐브](../../v8/reporting/gs-cubes.md)에 정의된 집계는 특정 활동으로 업데이트할 수 있습니다. 합계를 구성할 때 **[!UICONTROL Workflow]** 탭을 사용할 수 있습니다.

[이 섹션](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates)에서 큐브 및 합계에 대해 자세히 알아보세요.

집계를 업데이트하려면 **[!UICONTROL Update aggregate]** 활동을 편집하고 업데이트할 큐브와 집계를 선택하십시오.

**전체 업데이트** 또는 **부분 업데이트**&#x200B;를 구성할 수 있습니다.

![](assets/update-aggregate-details.png)

기본적으로 각 계산 중에 전체 업데이트가 실행됩니다. 부분 업데이트를 활성화하려면 옵션을 선택하고 업데이트 조건을 정의합니다.

![](assets/update-aggregate-partial.png)

계산 업데이트 빈도를 설정하려면 **[!UICONTROL Scheduler]** 활동을 추가하는 것이 좋습니다.
