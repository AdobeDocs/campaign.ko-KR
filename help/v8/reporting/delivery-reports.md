---
title: Adobe Campaign 기본 제공 게재 보고서
description: Adobe Campaign 기본 제공 게재 보고서
feature: Reporting
source-git-commit: 60db4c2e8cd280845ddd0176bd10dc1b7edbb767
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 2%

---


# 게재 보고서 {#delivery-reports}

게재 개요에서 액세스할 수 있는 다양한 보고서를 통해 게재 실행을 추적할 수 있습니다.

보고서에 액세스하려면 아래 단계를 수행하십시오.

1. 다음 위치로 이동합니다. **[!UICONTROL Campaigns]** 탭을 클릭하고 **[!UICONTROL Delivery]** 게재 목록을 표시하는 링크입니다.
1. 액세스할 게재 보고서의 이름을 클릭합니다.
1. 을(를) 선택합니다 **[!UICONTROL Summary]** 탭을 클릭하고 **[!UICONTROL Reports]** 를 눌러 게재와 관련된 보고서에 액세스합니다.

   ![](assets/detailed-report-2.png)

   기본적으로 다음 보고서를 사용할 수 있습니다.

   * **[!UICONTROL Delivery throughput]**
   * **[!UICONTROL Sharing to social networks]**
   * **[!UICONTROL Statistics on sharing activities]**
   * **[!UICONTROL Hot clicks]**
   * **[!UICONTROL Tracking statistics]**
   * **[!UICONTROL URLs and click streams]**
   * **[!UICONTROL Tracking indicators]**
   * **[!UICONTROL Non-deliverables and bounces]**
   * **[!UICONTROL User activities]**
   * **[!UICONTROL Delivery summary]**
   * **[!UICONTROL Subscription tracking]**
   * **[!UICONTROL Delivery statistics]**
   * **[!UICONTROL Breakdown of opens]**

## 지표 추적 {#tracking-indicators}

이 보고서는 게재를 받을 때 수신자의 동작을 추적하기 위한 주요 지표를 결합합니다. 게재 및 수신 통계, 열기 및 클릭스루 비율, 생성된 클릭 스트림, 웹 추적 및 소셜 네트워크에 대한 활동 공유를 제공합니다.

>[!NOTE]
>
>텍스트 형식의 전자 메일에 연결된 오류의 여분으로 인해 메시지 열기를 기반으로 계산된 값은 항상 예측됩니다. 다음 **[!UICONTROL Distinct opens/Sum of opens for the population reached]** 지표들은 이 오차 마진을 고려한다. [자세히 알아보기](metrics-calculation.md#tracking-opens-)

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]** : 게재 분석 후 게재할 총 메시지 수입니다.
* **[!UICONTROL Success]** : 정상적으로 처리된 메시지 수.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>관련 백분율은 성공적으로 전달된 메시지 수를 기반으로 계산됩니다.

* **[!UICONTROL Distinct opens for the population reached]** : 메시지를 한 번 이상 연 타겟팅된 수신자 수 예측 링크를 클릭하기 위해 이메일을 열어야 하므로 추적된 URL에 대한 클릭이 고려됩니다.
* **[!UICONTROL Sum of opens for the population reached]** : 타겟팅된 수신자의 총 열기 수 예측
* **[!UICONTROL Clicks on opt-out link]** : 구독 취소 링크에 대한 클릭 수입니다.
* **[!UICONTROL Clicks on the mirror page link]** : 미러 페이지에 대한 링크에 대한 클릭 수입니다. 고려하려면 게재 마법사(추적된 URL)에서 링크는 다음과 같이 정의해야 합니다. <!--Refer to this [page](../../delivery/using/about-delivery-monitoring.md).-->
* **[!UICONTROL Estimation of forwards]** : 타겟팅된 수신자가 발송한 전자 메일 수의 예측입니다. 이 값은 개별 사용자의 수와 이메일을 클릭한 개별 수신자 수를 뺀 값을 계산합니다.

   >[!NOTE]
   >
   >개별 사용자와 타겟팅된 수신자 간의 차이에 대한 자세한 내용은 [대상 개인/수신자](metrics-calculation.md#targeted-persons---recipients).

**[!UICONTROL 3. Open and click-through rate]**

이 값 표는 인터넷 도메인별 게재, 열기, 클릭 수 및 원시 반응성 분류를 보여줍니다. 다음 표시기가 사용됩니다.

* **[!UICONTROL Sent]** : 이 도메인에서 보낸 총 메시지 수입니다.
* **[!UICONTROL Complaints]** : 수신자가 원치 않는다고 보고한 이 도메인에 대한 메시지 수입니다. 이 비율은 이 도메인에서 보낸 총 메시지 수를 기반으로 계산됩니다.
* **[!UICONTROL Opens]** : 메시지를 한 번 이상 연 해당 도메인의 개별 대상 수신자 수입니다. 이 비율은 이 도메인에서 보낸 총 메시지 수를 기반으로 계산됩니다.
* **[!UICONTROL Clicks]** : 동일한 게재에서 최소 한 번 이상 클릭한 개별 대상 수신자 수입니다. 이 비율은 이 도메인에서 보낸 총 메시지 수를 기반으로 계산됩니다
* **[!UICONTROL Raw reactivity]** : 게재를 한 번 이상 클릭한 수신자 수의 백분율로, 게재를 한 번 이상 연 수신자 수와 비교됩니다.

>[!NOTE]
>
>이 보고서에 표시되는 도메인 이름은 큐브 수준에서 사용되는 항목별 목록에서 정의됩니다. 기본 도메인을 변경하거나 추가하려면 **[!UICONTROL Domains]** 항목화된 목록 및 값 및 별칭을 수정합니다. 다음 **[!UICONTROL Others]** 카테고리에는 항목별 목록 값에 속하지 않는 도메인 이름이 포함되어 있습니다.
>
>에서 열거형에 액세스하고 구성하는 방법을 알아봅니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target=&quot;_blank&quot;}.


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>관련 백분율은 성공적으로 전달된 메시지 수를 기반으로 계산됩니다.

* **[!UICONTROL Distinct clicks for the population reached]** : 게재를 한 번 이상 클릭한 개별 사용자 수입니다.
* **[!UICONTROL Cumulated clicks]** : 구독 취소 링크 및 미러 페이지를 제외하고 타겟팅된 수신자의 총 클릭 수입니다.
* **[!UICONTROL Recipient clicks]** : 동일한 게재에서 최소 한 번 이상 클릭한 개별 대상 수신자 수입니다.
* **[!UICONTROL Estimated recipient reactivity]** : 게재에서 한 번 이상 클릭한 수신자 수의 비율을 게재를 한 번 이상 연 예상 수신자 수와 비교하여 보여줍니다. 옵트아웃 및 미러 페이지 링크의 클릭은 고려되지 않습니다.
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]** : Number of web pages visited following message reception.
* **[!UICONTROL Transactions]** : Number of purchases following message reception.
* **[!UICONTROL Total amount]** : Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]** : Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]** : Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]** : Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]** : Average amount of purchases generated per message.

  >[!NOTE]
  >
  >In order for a visited page, transaction, amount or article to be taken into account, a webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).

**[!UICONTROL 6. Sharing activities to email and social networks]**

This section shows the number of messages shared on each social network. For more on this, refer to [Sharing to social networks](../../reporting/using/global-reports.md#sharing-to-social-networks).

## URLs and click streams {#urls-and-click-streams}

This report shows the list of pages visited following a delivery. 

![](assets/s_ncs_user_url_report.png)

You can configure the contents of this report by selecting: the score chart to be displayed, the time filter (since the action launch, over the first 6 hours following launch, etc.) and the data display mode (by label, by URL, by category. Click **[!UICONTROL Refresh]** to confirm your selection.

The following rates are displayed in the upper section of the report:

* **[!UICONTROL Reactivity]** : Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]** : Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]** : Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]** : This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]** : Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]** : Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## 게재 요약 {#delivery-summary}

이 보고서는 게재에 대한 모든 주요 정보를 제공합니다.

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

이 섹션에는 두 개의 지표가 있습니다.

* **[!UICONTROL Initial population]** : 게재가 타겟팅한 총 수신자 수입니다.
* **[!UICONTROL Messages rejected by the rule]** : 유형화 규칙을 적용할 때 분석 중에 무시된 주소 수입니다. 주소가 누락됨, 격리됨, 차단 목록 등 <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

중간 차트는 분석 중에 거부된 메시지 규칙당 분류를 보여줍니다.

**[!UICONTROL Delivery statistics]**

이 섹션에는 다음 표시기가 포함됩니다.

* **[!UICONTROL Messages to be delivered]** : 게재 분석 후 게재할 총 메시지 수입니다.
* **[!UICONTROL Success]** : 성공적으로 처리된 메시지 수입니다. 연관된 비율은 배달할 메시지 수와 비율 입니다.
* **[!UICONTROL Errors]** : 게재 및 자동 리바운드 처리 중에 누적된 총 오류 수입니다. 연관된 비율은 배달할 메시지 수와 비율 입니다.
* **[!UICONTROL New quarantines]** : 실패한 게재 후 격리된 주소 수(사용자 알 수 없음, 잘못된 도메인). 연관된 비율은 배달할 메시지 수와 비율 입니다.

## 핫 클릭 {#hot-clicks}

이 보고서는 각 링크에 대한 클릭 비율( HTML 및/또는 텍스트)을 포함하는 메시지 콘텐츠를 보여줍니다. 개인화 블록은 구독 취소 링크, 미러 페이지 링크 및 오퍼 링크를 총 누적 클릭 수에 고려하지만 보고서에 표시되지 않습니다.

>[!NOTE]
>
>게재에 오퍼(상호 작용)가 포함되어 있으면 보고서 위 부분에 오퍼에 대한 클릭 비율을 표시하는 상자가 표시됩니다.


## 통계 추적 {#tracking-statistics}

이 보고서는 열기, 클릭 및 트랜잭션에 대한 통계를 제공합니다.

게재의 마케팅 영향을 추적할 수 있습니다. 시간 표시줄(1시간, 3시간 또는 24시간 보기 등)을 변경하여 값이 표시되는 방식을 구성할 수 있습니다. **[!UICONTROL Refresh]**&#x200B;을(를) 클릭하여 선택 항목을 확인합니다.

이 보고서는 배달을 최대 효율에 도달하는 데 필요한 시간을 표시하는 값 테이블 및 파레토 차트를 제공합니다. 다음 표시기가 사용됩니다.

* **[!UICONTROL Opens]** : 연 총 메시지 수의 백분율에 도달하는 데 필요한 시간을 예측합니다. 텍스트 형식의 이메일은 고려되지 않습니다. [자세히 알아보기](metrics-calculation.md#tracking-opens-)
* **[!UICONTROL Clicks]** : 기록된 총 클릭 수의 백분율에 도달하는 데 필요한 시간의 예측. 옵트아웃 링크 및 미러 페이지의 클릭은 고려되지 않습니다.
<!--
* **[!UICONTROL Transactions]** : Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## 누적 보고서 {#cumulated-reports}

게재에 대한 누적 보고서를 표시할 수 있습니다. 이렇게 하려면 비교할 게재 를 선택하여 이러한 게재에 대한 보고서 목록을 확인합니다.

목록에서 인접하지 않은 게재를 선택하려면 CTRL 키를 누른 채 선택합니다.

다른 폴더에 저장된 게재를 선택하려면 **[!UICONTROL Display sub-levels]** 아이콘 - 도구 모음에서 액세스 가능. 그러면 동일한 목록에 표시됩니다.

