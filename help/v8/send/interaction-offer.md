---
solution: Campaign v8
product: Adobe Campaign
title: Campaign 상호 작용 오퍼
description: 오퍼를 만드는 방법을 알아봅니다
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 3%

---

# 오퍼 만들기

오퍼를 만들려면 아래 단계를 수행하십시오.

1. **[!UICONTROL Campaigns]** 탭으로 이동하여 **[!UICONTROL Offers]** 링크를 클릭합니다.

1. **[!UICONTROL Create]** 버튼을 클릭합니다.

1. 레이블을 변경하고 오퍼가 속해야 하는 카테고리를 선택합니다.

1. **[!UICONTROL Save]** 을 클릭하여 오퍼를 만듭니다.

   오퍼는 플랫폼에서 사용할 수 있으며 해당 콘텐츠를 구성할 수 있습니다.

## 자격 설정

이제 **[!UICONTROL Eligibility]** 탭을 사용하여 다음을 정의할 수 있습니다.

* 오퍼의 자격 기간입니다. [자세히 알아보기](#eligibility-period)
* 오퍼 대상 모집단의 필터. [자세히 알아보기](#filters-on-the-target)
* 오퍼 가중치. [자세히 알아보기](#offer-weight)

### 오퍼 자격 기간{#eligibility-period}

오퍼의 **[!UICONTROL Eligibility]** 탭에서 오퍼의 자격 기간을 정의합니다. 드롭다운 목록을 사용하여 달력에서 시작 날짜와 종료 날짜를 선택합니다.

![](assets/offer_eligibility_create_002.png)

이 기간이 지나면 오퍼가 선택되지 않습니다. 오퍼 카테고리에 대한 자격 날짜도 구성한 경우 가장 제한적인 기간이 적용됩니다.

### 대상 {#filters-on-the-target}에 필터 추가

오퍼의 **[!UICONTROL Eligibility]** 탭에서 필터를 오퍼 대상에 적용합니다.

이렇게 하려면 **[!UICONTROL Edit query]** 링크를 클릭하고 적용할 필터를 선택합니다.

![](assets/offer_eligibility_create_003.png)

사전 정의된 필터가 이미 만들어진 경우 사용자 필터 목록에서 해당 필터를 선택할 수 있습니다. [자세히 알아보기](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### 오퍼 가중치 {#offer-weight} 설정

엔진이 Target이 사용할 수 있는 여러 오퍼 중에서 결정하도록 하려면 오퍼에 하나 이상의 가중치를 지정해야 합니다. 필요한 경우 필터를 대상에 적용하거나 가중치가 적용될 오퍼 공간을 제한할 수도 있습니다. 가중치가 더 큰 오퍼는 더 적은 무게의 오퍼보다 선호될 것이다.

예를 들어 동일한 오퍼에 대해 여러 가중치를 구성할 수 있습니다. 예를 들어 지원 기간, 특정 타겟 또는 오퍼 공간을 구별할 수 있습니다.

예를 들어, 오퍼는 18~25세 사이의 연락처에 대해 A 중량이고 해당 범위 이상의 연락처에 대해서는 B 중량일 수 있습니다. 만약 제안이 여름 내내 자격이 된다면, 그것은 또한 7월에 A의 중량과 8월에 B의 중량을 가질 수 있습니다.

>[!NOTE]
>
>지정된 가중치는 오퍼가 속한 카테고리의 매개 변수에 따라 일시적으로 수정할 수 있습니다. [자세히 알아보기](interaction-offer-catalog.md#creating-offer-categories)

오퍼에서 가중치를 만들려면 다음 단계를 적용합니다.

1. 오퍼의 **[!UICONTROL Eligibility]** 탭에서 **[!UICONTROL Add]** 을 클릭합니다.

   ![](assets/offer_weight_create_001.png)

1. 레이블을 변경하고 가중치를 지정합니다. 기본값은 1입니다.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >가중치를 입력하지 않으면(0) 오퍼에 적합한 것으로 간주되지 않습니다.

1. 특정 기간에 대해 가중치를 적용하려면 자격 일자를 정의합니다.

   ![](assets/offer_weight_create_002.png)

1. 필요한 경우 가중치를 특정 오퍼 공간으로 제한합니다.

   ![](assets/offer_weight_create_003.png)

1. 대상에 필터를 적용합니다.

   ![](assets/offer_weight_create_004.png)

1. **[!UICONTROL OK]** 을 클릭하여 가중치를 저장합니다.

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >선택한 오퍼에 대해 대상이 다중 가중치에 적합한 경우 엔진이 가장 높은(가장 높은) 가중치를 유지합니다. 오퍼 엔진을 호출하면 오퍼가 연락처당 최대 한 번 선택됩니다.

### 오퍼 자격 규칙 요약 {#a-summary-of-offer-eligibility-rules}

구성이 완료되면 오퍼 대시보드에서 자격 규칙 요약을 사용할 수 있습니다.

보려면 **[!UICONTROL Schedule and eligibility rules]** 링크를 클릭합니다.

![](assets/offer_eligibility_create_005.png)

## 오퍼 컨텐츠 {#creating-the-offer-content} 를 만듭니다

**[!UICONTROL Content]** 탭을 사용하여 오퍼 컨텐츠를 정의합니다.

![](assets/offer_content_create_001.png)

1. 오퍼 컨텐츠의 다양한 매개 변수를 정의합니다.

   * **[!UICONTROL Title]** :오퍼에 표시할 제목을 지정합니다. 경고:이것은 **[!UICONTROL General]** 탭에 정의된 오퍼의 레이블을 참조하지 않습니다.
   * **[!UICONTROL Destination URL]** :오퍼의 URL을 지정합니다. &quot;http://&quot; 또는 &quot;https://&quot;으로 시작해야 합니다.
   * **[!UICONTROL Image URL]** :오퍼 이미지에 대한 URL 또는 액세스 경로를 지정합니다.
   * **[!UICONTROL HTML content]** /  **[!UICONTROL Text content]** :원하는 탭에 오퍼 본문을 입력합니다. 추적을 생성하려면 **[!UICONTROL HTML content]** 을 `<div>` 유형 요소로 묶을 수 있는 HTML 요소로 구성해야 합니다. 예를 들어 HTML 페이지에서 `<table>` 요소의 결과는 다음과 같습니다.

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

   [이 섹션](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted)에서 수락 URL을 정의하는 방법을 알아봅니다.

   ![](assets/offer_content_create_002.png)

   오퍼 공간 구성 중에 정의된 필수 필드를 찾으려면 **[!UICONTROL Content definitions]** 링크를 클릭하여 목록을 표시합니다. [자세히 알아보기](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   이 예에서 오퍼에는 제목, 이미지, HTML 콘텐츠 및 대상 URL이 포함되어야 합니다.

## 오퍼 {#previewing-the-offer} 미리 보기

오퍼 컨텐츠가 구성되면 수신자에 대해 표시될 오퍼를 미리 볼 수 있습니다.

방법은 다음과 같습니다.

1. **[!UICONTROL Preview]** 탭을 클릭합니다.

   ![](assets/offer_preview_create_001.png)

1. 보려는 오퍼 표현을 선택합니다.

   ![](assets/offer_preview_create_002.png)

1. 오퍼 콘텐츠를 개인화한 경우 개인화할 오퍼 대상을 선택합니다.

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

이제 오퍼를 승인하고 활성화하여 **Live** 환경에서 사용할 수 있도록 할 수 있습니다.

:[!DNL :arrow_upper_right:]:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content) 를 참조하십시오

## 오퍼 프레젠테이션 관리{#offer-presentation}

Campaign을 사용하면 프레젠테이션 규칙을 사용하여 오퍼 프로필의 흐름을 제어할 수 있습니다. Campaign 상호 작용에 고유한 이러한 규칙은 **유형화 규칙**&#x200B;입니다. 수신자에게 이미 수행된 proposition 내역을 기반으로 오퍼를 제외할 수 있습니다. 환경에서 참조됩니다.

:[!DNL :arrow_upper_right:]:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=en#managing-offers) 를 참조하십시오

## 오퍼 시뮬레이션

시뮬레이션 모듈을 사용하면 수신자에게 제안을 보내기 전에 카테고리 또는 환경에 속하는 오퍼의 분포를 테스트할 수 있습니다.

시뮬레이션은 오퍼와 해당 프레젠테이션 규칙에 이전에 적용된 컨텍스트 및 자격 규칙을 고려합니다. 이렇게 하면 시뮬레이션이 타겟팅된 수신자에게 영향을 주지 않으므로 오퍼를 실제로 사용하거나 대상을 지나치게 모집하지 않고 다양한 버전의 오퍼 제안을 테스트하고 세분화할 수 있습니다.

:[!DNL :arrow_upper_right:]:오퍼 시뮬레이션에 대한 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.htm) 를 참조하십시오
