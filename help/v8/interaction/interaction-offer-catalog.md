---
title: Campaign 상호 작용 오퍼 카탈로그
description: 오퍼 카탈로그를 만드는 방법을 알아봅니다
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# 오퍼 카탈로그 만들기

로서의 **오퍼 관리자**, 사용자는 오퍼 카탈로그를 만들어야 합니다.

오퍼 카탈로그는 기존 단일 환경에 연결됩니다. 이 카탈로그의 오퍼는 이 동일한 환경에 지정된 공간에만 연결할 수 있습니다.

오퍼를 만들려면 먼저 오퍼를 지정해야 합니다 [환경](interaction-env.md) 카테고리로 정렬된 오퍼 세트의 모든 특성(자격, 대상에 대한 제한 사항, 프레젠테이션 규칙)과 해당 공간 목록을 포함합니다.

## 오퍼 카테고리 만들기{#creating-offer-categories}

오퍼는 카테고리/하위 카테고리로 구성됩니다. 카테고리는 **[!UICONTROL Design]** 환경에 자동으로 배포 **[!UICONTROL Live]** 환경(즉, 사용자가 포함하는 오퍼가 승인될 때 사용 가능함). 다음 **[!UICONTROL Design]** 환경에는 모든 오퍼를 받을 기본 카테고리가 포함되어 있습니다. 카탈로그 오퍼에 계층 구조를 추가하도록 하위 카테고리를 만들 수 있습니다.

각 카테고리에 대해 다음을 정의할 수 있습니다 **자격 조건 날짜**: 카테고리에 포함된 오퍼를 해당 대상에 표시할 수 있는 기간입니다. 카테고리의 가중치를 조정하여 오퍼 프레젠테이션의 우선 순위를 지정할 수도 있습니다.

새 카테고리를 만들려면 아래 단계를 수행하십시오.

1. 브라우저로 **[!UICONTROL Offer catalog]** 폴더를 입력합니다.

   ![](assets/offer_cat_create_001.png)

1. 마우스 오른쪽 단추를 클릭하고 을 선택합니다 **[!UICONTROL Create a new "Offer category" folder]** 드롭다운 목록에서 을 선택합니다.

   ![](assets/offer_cat_create_002.png)

1. 카테고리의 이름을 다시 지정합니다. 레이블을 나중에 **[!UICONTROL General]** 탭.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >필요한 만큼 카테고리를 만들려면 이 단계를 반복합니다.

   그런 다음 필요에 따라 다음을 수행할 수 있습니다.

   * 자격 일자를 다음 위치에서 지정합니다. **[!UICONTROL Eligibility]** 탭.

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** 필터를 오퍼 타겟에 적용하려면

   * 자격 규칙 요약 **[!UICONTROL Schedule and eligibility rules of the offer]** 링크를 클릭합니다.

## 대체 카테고리 추가

모든 수신자가 오퍼 제안을 수신하도록 하기 위해 추천에 하나 또는 여러 오퍼 카테고리를 체계적으로 추가할 수 있습니다.

이러한 대체 오퍼에는 낮은(하지만 null은 아님) 가중치가 있어야 더 높은 웨이트 오퍼가 자격이 없는 경우에만 고려됩니다.

또한 이러한 오퍼가 항상 권장 사항에 포함되도록 하려면 이러한 오퍼에 적용된 프레젠테이션 규칙이 없어야 합니다. 즉, 제안 중에 더 높은 가중치 오퍼를 사용할 수 없는 경우 수신자는 이 카테고리에서 하나 이상의 오퍼를 받게 됩니다.

권장 사항에 대체 카테고리를 포함하려면 아래 단계를 따르십시오.

1. 오퍼 카탈로그를 찾습니다.
1. 을(를) 클릭합니다. **[!UICONTROL Eligibility]** 탭을 선택하고 을(를) 선택합니다 **[!UICONTROL Always include this category in the recommendations]** 선택 사항입니다.
1. **[!UICONTROL Save]**&#x200B;를 클릭합니다.

   ![](assets/offer_cat_default_001.png)
