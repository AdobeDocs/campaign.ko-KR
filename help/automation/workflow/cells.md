---
product: campaign
title: 셀
description: 셀
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 2%

---

# 셀{#cells}

다음 **[!UICONTROL Cells]** 활동은 데이터 열로 다양한 하위 집합 보기를 제공합니다. Labs를 통해 하위 집합 조작을 용이하게 하고 개인화 기능을 활용하도록 설계되었습니다.

![](assets/wf_split_cells.png)

사용자 요구 사항에 따라 특정 매개 변수를 입력하도록 이 활동을 구성할 수 있습니다. 기본적으로 각 서브세트의 세부 정보는 를 통해 전용 창에 자세히 표시됩니다 **[!UICONTROL Cells]** 및 **[!UICONTROL Advanced]** 탭.

![](assets/wf_split_cells_with_customization.png)

아래 예에서는 입력 양식이 수정되었습니다. a **[!UICONTROL Data]** 각 하위 세트에 대한 오퍼 및 우선 순위 수준을 연결할 수 있도록 탭이 추가되었습니다.

![](assets/cells-activity-sample.png)

이 구성의 경우 다음 정보가 워크플로우 양식의 **[!UICONTROL Administration > Configurations > Input forms]** Adobe Campaign 탐색기 노드:

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

Adobe Campaign의 입력 양식 개인화는 전문가 사용자를 위해 예약되어 있습니다. 자세한 정보는 이 문서를 참조하십시오.
