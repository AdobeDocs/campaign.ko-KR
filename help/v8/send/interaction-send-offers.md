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
source-wordcount: '1297'
ht-degree: 2%

---

# 오퍼 보내기

오퍼 엔진에서 오퍼를 선택하려면 이 오퍼가 승인되고 **라이브** 환경에서 사용할 수 있습니다. [자세히 알아보기](interaction-offer.md#approve-offers)

아웃바운드 커뮤니케이션 채널을 통한 오퍼 프레젠테이션은 다이렉트 메일, 이메일 또는 모바일 배달을 통해 수행됩니다. 트랜잭션 메시지(메시지 센터)와 함께 단일 모드를 사용할 수도 있습니다.

## 배달 {#offer-into-a-delivery}에 오퍼 삽입

오퍼에 오퍼 위치를 삽입하려면 아래 절차를 따르십시오.

1. 배달 창에서 **오퍼** 아이콘을 클릭합니다.

   ![](assets/offer_delivery_001.png)

1. 오퍼 환경과 일치하는 공간을 선택합니다.

   ![](assets/offer_delivery_002.png)

1. 엔진에서 선택한 오퍼를 세분화하려면 제공할 오퍼가 속한 카테고리 또는 하나/여러 테마를 선택합니다. 제한 사항을 과도하게 로드하지 않도록 이러한 필드 중 하나만 사용하는 것이 좋습니다.

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. 전달 본문에 삽입할 오퍼 수를 지정합니다.

   ![](assets/offer_delivery_005.png)

1. 필요한 경우 **[!UICONTROL Exclude non-eligible recipients]** 옵션을 선택합니다. [자세히 알아보기](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_006.png)

1. 필요한 경우 **[!UICONTROL Do not display anything if no offers are selected]** 옵션을 선택합니다. [자세히 알아보기](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_007.png)

1. 병합 필드를 사용하여 배달 내용에 속성을 삽입합니다. 사용 가능한 제안 수는 엔진 호출이 구성되는 방식에 따라 다르며 해당 주문은 오퍼의 우선 순위에 따라 달라집니다.

   ![](assets/offer_delivery_008.png)

1. 컨텐츠를 완성하고 테스트하여 배달을 보냅니다.

   ![](assets/offer_delivery_010.png)


### 오퍼 엔진 매개 변수 {#parameters-for-calling-offer-engine}

* **[!UICONTROL Space]** :오퍼 엔진을 활성화하기 위해 선택해야 하는 오퍼 환경의 공간입니다.
* **[!UICONTROL Category]** :오퍼가 정렬되는 특정 폴더. 카테고리를 지정하지 않으면 테마를 선택하지 않는 한 환경에 포함된 모든 오퍼가 오퍼 엔진에서 고려됩니다.
* **[!UICONTROL Themes]** :카테고리에서 업스트림 키 단어 정의 이러한 오퍼는 필터로 작동하며 카테고리 세트에서 오퍼를 선택하여 제공할 오퍼 수를 세분화할 수 있습니다.
* **[!UICONTROL Number of propositions]** :전달 본문에 삽입할 수 있는 엔진에서 반환된 오퍼 수입니다. 오퍼가 메시지에 삽입되지 않으면 오퍼는 여전히 생성되지만 표시되지 않습니다.
* **[!UICONTROL Exclude non-eligible recipients]** :이 옵션을 사용하면 적합한 오퍼가 부족한 수신자의 제외를 활성화하거나 비활성화할 수 있습니다. 해당되는 제안 개수는 요청된 제안 개수보다 작을 수 있습니다. 이 확인란을 선택하면 제대로 표시되지 않는 수신자는 전달에서 제외됩니다. 이 옵션을 선택하지 않으면 이러한 수신자는 제외되지 않지만 요청된 제안 수는 없습니다.
* **[!UICONTROL Do not display anything if no offer is selected]** :이 옵션을 사용하면 제안 중 하나가 존재하지 않을 경우에 메시지가 처리되는 방식을 선택할 수 있습니다. 이 상자를 선택하면 누락된 제안 내용이 표시되지 않고 이 제안에 대한 메시지에 아무런 컨텐트도 나타나지 않습니다. 상자를 선택하지 않으면 전송 중에 메시지 자체가 취소되고 받는 사람은 더 이상 메시지를 받지 않습니다.

## 워크플로우에서 오퍼 보내기

여러 워크플로우 활동을 통해 오퍼가 표시되는 방식을 정의할 수 있습니다.

* 데이터 보강
* 오퍼 엔진
* 셀별 오퍼

### 데이터 보강 {#enrichment}

**데이터 연계 강화** 활동을 사용하면 전달 받는 사람을 위한 오퍼나 링크를 추가할 수 있습니다.

:arrow_upper_right:농축 활동에 대한 자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/enrichment.html)를 참조하십시오.

예를 들어 배달하기 전에 수신자 쿼리에 대한 데이터를 보강할 수 있습니다.

![](assets/int_enrichment_offer1.png)

오퍼 제안을 지정하는 방법에는 두 가지가 있습니다.

* 오퍼 또는 오퍼 엔진 호출 지정
* 오퍼에 대한 링크 참조.

#### 오퍼 엔진 {#specifying-an-offer-or-a-call-to-the-offer-engine} 호출을 지정합니다.

**쿼리** 활동을 구성한 후:

1. **Enrichment** 활동을 추가하고 엽니다.
1. **[!UICONTROL Enrichment]** 탭에서 **[!UICONTROL Add data]**&#x200B;를 선택합니다.
1. 추가할 데이터 유형에서 **[!UICONTROL An offer proposition]**&#x200B;을 선택합니다.

   ![](assets/int_enrichment_offer2.png)

1. 추가할 제안에 대한 레이블과 식별자를 지정합니다.
1. 오퍼 선택을 지정합니다. 다음과 같은 두 가지 옵션을 사용할 수 있습니다.

   * **[!UICONTROL Search for the best offer in a category]** :이 옵션을 선택하고 오퍼 엔진 호출 매개 변수(오퍼 공간, 카테고리 또는 테마, 연락처 날짜, 유지할 오퍼 수)를 지정합니다. 엔진은 이러한 매개 변수에 따라 추가할 오퍼를 자동으로 계산합니다. 두 필드를 동시에 수료하지 않고 **[!UICONTROL Category]** 또는 **[!UICONTROL Theme]** 필드를 완료하는 것이 좋습니다.

      ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A predefined offer]** :이 옵션을 선택하고 오퍼 엔진을 호출하지 않고 추가할 오퍼를 직접 구성할 오퍼 공간, 특정 오퍼 및 연락처 날짜를 지정합니다.

      ![](assets/int_enrichment_offer4.png)

1. 그런 다음 선택한 채널에 해당하는 배달 활동을 구성합니다. [자세히 알아보기](#offer-into-a-delivery)

   >[!NOTE]
   >
   >미리 보기에 사용할 수 있는 제안의 수는 전달에서 직접 수행되는 가능한 구성이 아니라 농축 활동에서 수행되는 구성에 따라 다릅니다.

#### 오퍼 {#referencing-a-link-to-an-offer} 링크 참조

또한 **Enrichment** 활동에서 오퍼에 대한 링크를 참조할 수도 있습니다.

이렇게 하려면 아래 단계를 수행합니다:

1. 활동의 **[!UICONTROL Enrichment]** 탭에서 **[!UICONTROL Add data]**&#x200B;을 선택합니다.
1. 추가할 데이터 유형을 선택하는 창에서 **[!UICONTROL A link]**&#x200B;을 선택합니다.
1. 설정하려는 링크 유형과 대상을 선택합니다. 이 경우 대상은 오퍼 스키마입니다.

   ![](assets/int_enrichment_link1.png)

1. 농축활동의 인바운드 테이블 데이터(수신자 테이블)와 오퍼 테이블 간의 연결을 지정합니다. 예를 들어 오퍼 코드를 수신자에게 연결할 수 있습니다.

   ![](assets/int_enrichment_link2.png)

1. 그런 다음 선택한 채널에 해당하는 배달 활동을 구성합니다. [자세히 알아보기](#offer-into-a-delivery)

   >[!NOTE]
   >
   >미리 보기에 사용할 수 있는 제안 수는 전달에서 수행한 구성에 따라 다릅니다.

#### 스토어 오퍼 등급 및 가중치 {#storing-offer-rankings-and-weights}

기본적으로 **Enrichment** 활동이 오퍼를 제공하는 데 사용될 경우 순위 및 가중치는 제안 표에 저장되지 않습니다.

>[!NOTE]
>
>**[!UICONTROL Offer engine]** 활동은 기본적으로 이 정보를 저장합니다.

그러나 다음과 같이 이 정보를 저장할 수 있습니다.

1. 쿼리 후와 배달 활동 전에 제출한 데이터 연계 강화 활동에서 오퍼 엔진에 대한 호출을 만듭니다. [자세히 알아보기](../../interaction/using/integrating-an-offer-via-a-workflow.md#specifying-an-offer-or-a-call-to-the-offer-engine)
1. 활동의 기본 창에서 **[!UICONTROL Edit additional data...]**&#x200B;을 선택합니다.

   ![](assets/ita_enrichment_rankweight_1.png)

1. 등급 및 오퍼 가중치에 대해 **[!UICONTROL @rank]** 열을 추가하고 **[!UICONTROL @weight]** 값을 추가합니다.

   ![](assets/ita_enrichment_rankweight_2.png)

1. 추가를 확인하고 워크플로우를 저장합니다.

배달은 오퍼의 등급과 중량을 자동으로 저장합니다. 이 정보는 전달의 **[!UICONTROL Offers]** 탭에 표시됩니다.

### 오퍼 엔진 {#offer-engine}

또한 **[!UICONTROL Offer engine]** 활동을 사용하면 배달 전에 오퍼 엔진에 대한 호출을 지정할 수 있습니다.

:arrow_upper_right:**오퍼 엔진** 활동에 대한 자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offer-engine.html)를 참조하십시오.

이 활동은 배달 전 엔진에서 계산된 오퍼로 인바운드 모집단 데이터를 증가시켜 엔진 호출을 통한 **Enrichment** 활동과 동일한 원리로 작동합니다.

![](assets/int_offerengine_activity2.png)

**쿼리** 활동을 구성한 후:

1. **[!UICONTROL Offer engine]** 활동을 추가하고 엽니다.
1. 다양한 사용 가능한 필드를 작성하여 오퍼 엔진 매개 변수(오퍼 공간, 카테고리 또는 테마, 연락처 날짜, 유지할 오퍼 수)에 대한 호출을 지정합니다. 엔진은 이러한 매개 변수에 따라 추가할 오퍼를 자동으로 계산합니다.

   >[!CAUTION]
   >
   >이 활동을 사용하는 경우 게재에 사용된 오퍼 제안만 저장됩니다.

   ![](assets/int_offerengine_activity1.png)

1. 그런 다음 선택한 채널에 해당하는 배달 활동을 구성합니다. [자세히 알아보기](inserting-an-offer-proposition-into-a-delivery)

### 셀별 오퍼 {#offers-by-cell}

**[!UICONTROL Offers by cell]** 활동을 사용하면 질의 예제의 인바운드 모집단(예: 쿼리)을 여러 세그먼트로 배포하고 이러한 각 세그먼트에 제공할 오퍼를 지정할 수 있습니다.

:arrow_upper_right:**셀**&#x200B;별 오퍼 활동에 대한 자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offers-by-cell.html)를 참조하십시오.

이렇게 하려면 다음 프로세스를 사용하십시오.

1. 타겟 모집단을 지정한 후 **[!UICONTROL Offers by cell]** 활동을 추가한 다음 엽니다.
1. **[!UICONTROL General]** 탭에서 오퍼를 표시할 오퍼 공간을 선택합니다.
1. **[!UICONTROL Cells]** 탭에서 **[!UICONTROL Add]** 단추를 사용하여 다른 하위 세트를 지정합니다.

   * 사용 가능한 필터링 및 제한 규칙을 사용하여 하위 집합 채우기를 지정합니다.
   * 그런 다음 하위 세트에 표시할 오퍼를 선택합니다. 사용 가능한 오퍼는 이전 단계에서 선택한 오퍼 환경에서 사용할 수 있는 오퍼입니다.

      ![](assets/int_offer_per_cell1.png)

1. 그런 다음 선택한 채널에 해당하는 배달 활동을 구성합니다. 이에 대한 자세한 내용은 [전달](../../interaction/using/integrating-an-offer-via-the-wizard.md#inserting-an-offer-proposition-into-a-delivery) 섹션에 오퍼 제안 삽입 섹션을 참조하십시오.


<!--

## Delivering with delivery outlines {#delivering-with-delivery-outlines}

You can also present offers in a delivery using delivery outlines.

For more information on delivery outlines, refer to the Campaign - MRM guide.

1. Create a new campaign or access an existing campaign.
1. Access the delivery outlines via the campaign's **[!UICONTROL Edit]** > **[!UICONTROL Documents]** tab.
1. Add an outline then insert as many offers as you like into it by right-clicking on the outline and selecting **[!UICONTROL New]** > **[!UICONTROL Offer]**, then save the campaign.


1. Create a delivery whose delivery outlines you have access to (for example, a direct mail delivery).
1. When editing the delivery, click **[!UICONTROL Select a delivery outline]**.

   >[!NOTE]
   >
   >Depending on the type of delivery, this option can be found in the **[!UICONTROL Properties]** > **[!UICONTROL Advanced]** menu (for email deliveries for example).


1. Using the **[!UICONTROL Offers]** button, you can then configure the offer space as well as the number of offers to present in the delivery.


1. Add the propositions into the delivery body using the personalization fields (for more on this, refer to the [Inserting an offer proposition into a delivery](#inserting-an-offer-proposition-into-a-delivery) section), or in the case of a direct mail delivery, by editing the extraction file format.

   Propositions will be selected from the offers referenced in the delivery outline.

   >[!NOTE]
   >
   >Information regarding the offer rankings and weights is only saved in the proposition table if the offers are generated directly in the delivery.
-->
