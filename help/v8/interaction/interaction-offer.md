---
title: 캠페인 상호 작용 오퍼
description: 오퍼를 만드는 방법 알아보기
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 4dc2008d-681c-4a79-8fc8-c270c9224ab9
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 5%

---

# 오퍼 만들기

오퍼를 만들려면 아래 단계를 수행하십시오.

1. 다음으로 이동 **[!UICONTROL Campaigns]** 탭을 클릭하고 **[!UICONTROL Offers]** 링크를 클릭합니다.

1. **[!UICONTROL Create]** 버튼을 클릭합니다.

1. 레이블을 변경하고 오퍼가 속해야 하는 범주를 선택합니다.

1. 클릭 **[!UICONTROL Save]** 을 클릭하여 오퍼를 만듭니다.

   오퍼는 플랫폼에서 사용할 수 있으며 해당 콘텐츠를 구성할 수 있습니다.

## 자격 설정

이제 다음을 사용할 수 있습니다. **[!UICONTROL Eligibility]** 정의할 탭:

* 오퍼의 자격 기간. [자세히 알아보기](#eligibility-period)
* 오퍼 대상 모집단을 필터링합니다. [자세히 알아보기](#filters-on-the-target)
* 오퍼 가중치. [자세히 알아보기](#offer-weight)

### 오퍼 자격 기간{#eligibility-period}

다음에서 **[!UICONTROL Eligibility]** 오퍼의 탭에서 오퍼의 자격 기간을 정의합니다. 드롭다운 목록을 사용하여 달력에서 시작 날짜와 종료 날짜를 선택합니다.

![](assets/offer_eligibility_create_002.png)

이 기간이 지나면 오퍼가 선택되지 않습니다. 오퍼 범주에 대한 자격 날짜를 구성한 경우 가장 제한적인 기간이 적용됩니다.

### 대상에 필터 추가 {#filters-on-the-target}

다음에서 **[!UICONTROL Eligibility]** 오퍼의 탭에서 오퍼 대상에 필터를 적용합니다.

이렇게 하려면 **[!UICONTROL Edit query]** 을(를) 연결하고 적용할 필터를 선택합니다.

![](assets/offer_eligibility_create_003.png)

미리 정의된 필터가 이미 만들어진 경우 사용자 필터 목록에서 해당 필터를 선택할 수 있습니다. [자세히 알아보기](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### 오퍼 가중치 설정 {#offer-weight}

엔진이 대상이 적합한 여러 오퍼 중에서 결정할 수 있도록 하려면 오퍼에 하나 이상의 가중치를 할당해야 합니다. 필요한 경우 대상에 필터를 적용하거나 가중치가 적용될 오퍼 공간을 제한할 수도 있습니다. 가중치가 더 낮은 오퍼보다 가중치가 더 큰 오퍼가 선호될 것입니다.

예를 들어 기간, 특정 타겟 또는 오퍼 공간을 구분하도록 동일한 오퍼에 대해 여러 개의 가중치를 구성할 수 있습니다.

예를 들어, 오퍼는 18~25세의 연락처에 대해 A의 가중치를 가질 수 있고, 해당 범위 이상의 연락처에 대해 B의 가중치를 가질 수 있다. 여름 내내 오퍼를 받을 수 있다면 7월에 A의 가중치를, 8월에 B의 가중치를 가질 수도 있다.

>[!NOTE]
>
>할당된 가중치는 오퍼가 속한 카테고리의 매개 변수에 따라 일시적으로 수정할 수 있습니다. [자세히 알아보기](interaction-offer-catalog.md#creating-offer-categories)

오퍼에 가중치를 만들려면 다음 단계를 적용합니다.

1. 다음에서 **[!UICONTROL Eligibility]** 오퍼의 탭에서 **[!UICONTROL Add]**.

   ![](assets/offer_weight_create_001.png)

1. 레이블을 변경하고 가중치를 할당합니다. 기본값은 1입니다.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >가중치를 입력하지 않으면(0) 타겟은 오퍼에 적합한 것으로 간주되지 않습니다.

1. 주어진 기간에 가중치를 적용하려면 자격 일자를 정의합니다.

   ![](assets/offer_weight_create_002.png)

1. 필요한 경우 가중치를 특정 오퍼 공간으로 제한합니다.

   ![](assets/offer_weight_create_003.png)

1. 대상에 필터를 적용합니다.

   ![](assets/offer_weight_create_004.png)

1. 클릭 **[!UICONTROL OK]** 무게를 줄이려면

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >타겟이 선택한 오퍼에 대해 여러 가중치에 적격인 경우, 엔진은 최상의(가장 높은) 가중치를 유지합니다. 오퍼 엔진을 호출할 때 오퍼는 연락처당 최대 한 번만 선택됩니다.

### 오퍼 자격 규칙 요약 {#a-summary-of-offer-eligibility-rules}

구성이 완료되면 자격 규칙에 대한 요약을 오퍼 대시보드에서 사용할 수 있습니다.

보려면 **[!UICONTROL Schedule and eligibility rules]** 링크를 클릭합니다.

![](assets/offer_eligibility_create_005.png)

## 오퍼 콘텐츠 만들기 {#creating-the-offer-content}

사용 **[!UICONTROL Content]** 탭으로 이동하여 오퍼 콘텐츠를 정의합니다.

![](assets/offer_content_create_001.png)

1. 오퍼 컨텐츠의 다양한 매개 변수를 정의합니다.

   * **[!UICONTROL Title]** : 오퍼에 표시할 제목을 지정합니다. 경고: 오퍼의 레이블을 참조하지 않는데, 이는 오퍼에 정의되어 있습니다. **[!UICONTROL General]** 탭.
   * **[!UICONTROL Destination URL]** : 오퍼의 URL을 지정합니다. &quot;http://&quot; 또는 &quot;https://&quot;로 시작해야 합니다.
   * **[!UICONTROL Image URL]** : 오퍼 이미지에 대한 URL 또는 액세스 경로를 지정합니다.
   * **[!UICONTROL HTML content]** / **[!UICONTROL Text content]** : 원하는 탭에 오퍼의 본문을 입력합니다. 추적을 생성하려면 다음을 수행합니다 **[!UICONTROL HTML content]** 은(는) HTML 요소로 구성되어야 하며 `<div>` 요소를 입력합니다. 예를 들어, `<table>` HTML 페이지의 요소는 다음과 같습니다.

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   에서 수락 URL을 정의하는 방법 알아보기 [이 섹션](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted).

   ![](assets/offer_content_create_002.png)

   오퍼 공간 구성 중에 정의된 필수 필드를 찾으려면 **[!UICONTROL Content definitions]** 링크를 클릭하여 목록을 표시합니다. [자세히 알아보기](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   이 예에서 오퍼는 제목, 이미지, HTML 컨텐츠 및 대상 URL을 포함해야 합니다.

## 오퍼 미리 보기 {#previewing-the-offer}

오퍼 콘텐츠가 구성되면 수신자에게 표시되는 오퍼를 미리 볼 수 있습니다.

방법은 다음과 같습니다.

1. 다음을 클릭합니다. **[!UICONTROL Preview]** 탭.

   ![](assets/offer_preview_create_001.png)

1. 보려는 오퍼의 표현을 선택합니다.

   ![](assets/offer_preview_create_002.png)

1. 오퍼 콘텐츠를 개인화한 경우 오퍼 타겟을 선택하여 개인화를 확인하십시오.

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## 오퍼 승인 및 활성화{#approve-offers}

이제에서 사용할 수 있도록 오퍼를 승인하고 활성화할 수 있습니다. **라이브** 환경.

![](../assets/do-not-localize/book.png) 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content)를 참조하세요

## 오퍼 프레젠테이션 관리{#offer-presentation}

Campaign을 사용하면 프레젠테이션 규칙을 사용하여 오퍼 제안의 흐름을 제어할 수 있습니다. Campaign 상호 작용에만 해당되는 이러한 규칙은 다음과 같습니다 **유형화 규칙**. 수신자에게 이미 제안된 이력을 기반으로 오퍼를 제외할 수 있습니다. 환경에서 참조됩니다.

![](../assets/do-not-localize/book.png) 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html#managing-offers)를 참조하세요

## 오퍼 시뮬레이션

다음 **시뮬레이션** 모듈을 사용하면 제안을 수신자에게 보내기 전에 카테고리 또는 환경에 속한 오퍼의 배포를 테스트할 수 있습니다.

시뮬레이션은 오퍼에 이전에 적용된 컨텍스트 및 자격 규칙과 해당 프레젠테이션 규칙을 고려합니다. 시뮬레이션은 타겟팅된 수신자에게 영향을 주지 않으므로 실제로 오퍼를 사용하지 않거나 대상을 초과/요청하지 않고 오퍼 제안의 다양한 버전을 테스트하고 세분화할 수 있습니다.

![](../assets/do-not-localize/book.png) 오퍼 시뮬레이션에 대한 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.html)
