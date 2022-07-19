---
product: campaign
title: 집계 업데이트
description: 업데이트 집계 워크플로우 활동에 대해 자세히 알아보십시오
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%

---

# 집계 업데이트{#update-aggregate}

집계는 보고를 위해 큐브 수준에서 정의됩니다. A **[!UICONTROL Workflow]** 합계를 구성할 때 탭을 사용할 수 있습니다.

큐브와 Adobe Campaign에서 합계를 사용하는 방법에 대한 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target=&quot;_blank&quot;}.


집계를 업데이트하려면 **[!UICONTROL Update aggregate]** 활동을 선택하고 업데이트할 큐브와 합계를 선택합니다.

다음을 수행할 수 있습니다 **전체 업데이트** 또는&#x200B;**부분 업데이트**.

기본적으로 각 계산 중에 전체 업데이트가 실행됩니다. 부분 업데이트를 활성화하려면 관련 옵션을 선택하고 업데이트 조건을 정의합니다.

**모범 사례**: a **[!UICONTROL Scheduler]** 활동을 사용하여 계산 업데이트 빈도를 지정할 수 있습니다.

![](assets/scheduler-and-cube-aggregate.png)
