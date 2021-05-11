---
solution: Campaign
product: Adobe Campaign
title: 캠페인 상호 작용 오퍼 카탈로그
description: 오퍼 카탈로그를 만드는 방법 학습
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 1%

---

# 오퍼 카탈로그 만들기

**오퍼 관리자**&#x200B;에서는 오퍼 카탈로그를 만들 책임이 있습니다.

오퍼 카탈로그는 기존의 단일 환경에 연결됩니다. 이 카탈로그의 오퍼는 동일한 환경에서 지정된 공간에만 연결할 수 있습니다.

오퍼를 만들기 전에 먼저 카테고리로 정렬된 오퍼 세트의 모든 특성(자격 조건, 대상에 대한 제한, 프레젠테이션 규칙)과 해당 공간 목록이 포함된 [environment](interaction-env.md)을 지정해야 합니다.

## 오퍼 카테고리 만들기{#creating-offer-categories}

오퍼는 카테고리/하위 카테고리로 구성됩니다. 카테고리는 **[!UICONTROL Design]** 환경에서 만들어지며 포함된 오퍼가 승인될 때 **[!UICONTROL Live]** 환경(즉, 사용 가능하게 만들어짐)에 자동으로 배포됩니다. **[!UICONTROL Design]** 환경에는 모든 오퍼를 수신할 기본 카테고리가 포함되어 있습니다. 카탈로그 오퍼에 계층을 추가하기 위해 하위 카테고리를 만들 수 있습니다.

각 카테고리에 대해 카테고리에 포함된 오퍼를 대상에 표시할 수 있는 기간인 **자격 날짜**&#x200B;를 정의할 수 있습니다. 카테고리의 가중치를 조정하여 오퍼 프레젠테이션의 우선 순위를 정할 수도 있습니다.

새 카테고리를 만들려면 아래 단계를 수행하십시오.

1. **[!UICONTROL Offer catalog]** 폴더로 이동합니다.

   ![](assets/offer_cat_create_001.png)

1. 마우스 오른쪽 단추를 클릭하고 드롭다운 목록에서 **[!UICONTROL Create a new "Offer category" folder]**&#x200B;을 선택합니다.

   ![](assets/offer_cat_create_002.png)

1. 카테고리의 이름을 다시 지정합니다. 나중에 **[!UICONTROL General]** 탭을 사용하여 레이블을 편집할 수 있습니다.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >이 단계를 반복하여 필요한 만큼의 카테고리를 만듭니다.

   이후 필요에 따라 다음을 수행할 수 있습니다.

   * **[!UICONTROL Eligibility]** 탭에서 자격 조건 날짜를 지정합니다.

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Themes]** 필드를 사용하여 이 카테고리 내에서 오퍼를 선택하는 데 사용할 수 있는 키워드를 입력합니다.

      ![](assets/offer_cat_create_005.png)

      >[!NOTE]
      >
      >오퍼 엔진을 호출할 때 테마나 카테고리가 매개 변수와 일치하는 카탈로그의 일부만 선택합니다.

   * **[!UICONTROL Multiplier weight]** 필드를 통해 지정된 기간 동안 카테고리의 오퍼 가중치를 일시적으로 &quot;증폭&quot;합니다.

      ![](assets/offer_cat_create_006.png)

자격 조건 규칙 요약 정보는 카테고리에 포함된 오퍼의 대시보드에서 사용할 수 있습니다. 보려면 **[!UICONTROL Schedule and eligibility rules of the offer]** 링크를 클릭합니다.

## 대체 범주 추가

모든 수신자가 제안 제안을 받을 수 있도록 추천에 하나 이상의 다양한 오퍼 카테고리를 체계적으로 추가할 수 있습니다.

이러한 폴백 오퍼는 더 높은 가중치 오퍼를 사용할 수 없는 경우에만 고려되도록(null이 아님) 무게가 낮아야 합니다.

또한 이러한 오퍼가 항상 권장 사항에 포함되도록 하기 위해 이러한 오퍼에 적용된 프레젠테이션 규칙이 없어야 합니다. 이것은 제안 중에 더 높은 무게 제안이 제공되지 않을 경우 받는 사람은 이 카테고리에서 최소한 한 개의 제안을 받게 된다는 것을 의미합니다.

권장 사항에 폴백 카테고리를 포함하려면 아래 단계를 따르십시오.

1. 오퍼 카탈로그를 찾습니다.
1. **[!UICONTROL Eligibility]** 탭을 클릭하고 **[!UICONTROL Always include this category in the recommendations]** 옵션을 선택합니다.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   ![](assets/offer_cat_default_001.png)

