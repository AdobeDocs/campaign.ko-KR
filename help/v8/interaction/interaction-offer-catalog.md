---
title: 캠페인 상호 작용 오퍼 카탈로그
description: 오퍼 카탈로그를 만드는 방법에 대해 알아봅니다.
feature: Interaction, Offers
role: Developer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# 오퍼 카탈로그 만들기

**오퍼 관리자**&#x200B;로서 오퍼 카탈로그를 만들어야 합니다.

오퍼 카탈로그는 하나의 기존 환경에 연결되어 있습니다. 이 카탈로그의 오퍼는 동일한 환경에 지정된 공간에만 연결할 수 있습니다.

오퍼를 만들기 전에 먼저 카테고리별로 정렬된 오퍼 집합의 모든 특성(자격 조건, 대상에 대한 제한 사항, 프레젠테이션 규칙)과 해당 공간 목록을 포함하는 [환경](interaction-env.md)을 지정해야 합니다.

## 오퍼 카테고리 만들기{#creating-offer-categories}

오퍼는 카테고리/하위 카테고리로 구성됩니다. 범주는 **[!UICONTROL Design]** 환경에서 만들어지며, 포함된 오퍼가 승인될 때 **[!UICONTROL Live]** 환경에서 자동으로 배포됩니다(즉, 사용 가능함). **[!UICONTROL Design]** 환경에 모든 오퍼를 받을 기본 범주가 있습니다. 하위 범주를 만들어 카탈로그 오퍼에 계층을 추가할 수 있습니다.

각 범주에 대해 **자격 조건 날짜**&#x200B;를 정의할 수 있습니다. 이 기간은 범주에 포함된 오퍼를 대상으로 표시할 수 있는 기간입니다. 카테고리 가중치를 조정하여 오퍼 표시 우선 순위를 지정할 수도 있습니다.

새 카테고리를 만들려면 아래 단계를 수행합니다.

1. 브라우저를 **[!UICONTROL Offer catalog]** 폴더로 이동합니다.

   ![](assets/offer_cat_create_001.png)

1. 마우스 오른쪽 단추를 클릭하고 드롭다운 목록에서 **[!UICONTROL Create a new "Offer category" folder]**&#x200B;을(를) 선택합니다.

   ![](assets/offer_cat_create_002.png)

1. 카테고리 이름을 다시 지정합니다. 나중에 **[!UICONTROL General]** 탭을 사용하여 레이블을 편집할 수 있습니다.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >이 단계를 반복하여 필요한 만큼 범주를 만듭니다.

   그런 다음 필요에 따라 다음을 수행할 수 있습니다.

   * **[!UICONTROL Eligibility]** 탭에서 자격 날짜를 할당하십시오.

     ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]**: 오퍼 대상에 필터를 적용합니다.

   * 자격 규칙을 다시 정리합니다. 보려면 **[!UICONTROL Schedule and eligibility rules of the offer]** 링크를 클릭하십시오.

## 대체 범주 추가

모든 수신자가 오퍼 제안을 받도록 하기 위해, 추천에서 하나 또는 다양한 오퍼 카테고리를 체계적으로 추가하는 것이 가능하다.

이러한 대체 오퍼는 낮은(하지만 null이 아님) 가중치를 가져야 하므로 더 높은 가중치 오퍼가 적격하지 않은 경우에만 고려됩니다.

또한 이러한 오퍼가 권장 사항에 항상 포함되도록 하려면 이러한 오퍼에 적용되는 프레젠테이션 규칙이 없어야 합니다. 즉, 제안 중에 더 높은 가중치의 오퍼를 사용할 수 없는 경우 수신자는 이 범주에서 하나 이상의 오퍼를 받습니다.

권장 사항에 대체 범주를 포함하려면 아래 단계를 따르십시오.

1. 오퍼 카탈로그를 찾습니다.
1. **[!UICONTROL Eligibility]** 탭을 클릭하고 **[!UICONTROL Always include this category in the recommendations]** 옵션을 선택합니다.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   ![](assets/offer_cat_default_001.png)
