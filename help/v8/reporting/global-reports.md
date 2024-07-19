---
title: Adobe Campaign 글로벌 보고서
description: 글로벌 보고서에 액세스하고 사용하는 방법을 알아봅니다
feature: Reporting, Monitoring
role: User, Data Engineer
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1750'
ht-degree: 6%

---

# 전반적 보고서 {#global-reports}

이러한 보고서는 전체 데이터베이스의 데이터 활동과 관련이 있습니다. 보고서 대시보드를 보려면 **[!UICONTROL Reports]** 탭으로 이동하십시오.

![](assets/reports-tab.png)

보고서를 표시하려면 보고서 이름을 클릭합니다. 기본적으로 다음 보고서를 사용할 수 있습니다.

![](assets/report-global-list.png)

>[!NOTE]
>
>이 섹션에는 게재에 연결된 보고서만 표시됩니다.

* **[!UICONTROL Delivery throughput]** : [게재 처리량](#delivery-throughput)을(를) 참조하세요.
* **[!UICONTROL Browsers]** : [브라우저](#browsers)를 참조하세요.
* **[!UICONTROL Sharing to social networks]** : [소셜 네트워크에 공유](#sharing-to-social-networks)를 참조하세요.
* **[!UICONTROL Statistics on sharing activities]** : [공유 활동에 대한 통계](#statistics-on-sharing-activities)를 참조하세요.
* **[!UICONTROL Operating systems]** : [운영 체제](#operating-systems)를 참조하세요.
* **[!UICONTROL URLs and click streams]** : [URL 및 클릭 스트림](delivery-reports.md#urls-and-click-streams)을 참조하세요.
* **[!UICONTROL Tracking indicators]** : [추적 표시기](delivery-reports.md#tracking-indicators)를 참조하세요.
* **[!UICONTROL Non-deliverables and bounces]** : [게재 불가 및 바운스](#non-deliverables-and-bounces)를 참조하세요.
* **[!UICONTROL User activities]** : [사용자 활동](#user-activities)을 참조하세요.
* **[!UICONTROL Subscription tracking]** : [구독 추적](#subscription-tracking)을 참조하세요.
* **[!UICONTROL Delivery summary]** : [게재 요약](delivery-reports.md#delivery-summary)을 참조하세요.
* **[!UICONTROL Delivery statistics]** : [게재 통계](#delivery-statistics)를 참조하세요.
* **[!UICONTROL Breakdown of opens]** : [열기 분석](#breakdown-of-opens)을 참조하세요.

## 게재 처리량 {#delivery-throughput}

이 보고서에는 주어진 기간 동안 전체 플랫폼의 게재 처리량에 대한 정보가 포함되어 있습니다. 메시지가 게재되는 속도를 측정하기 위한 기준은 시간당 전송된 메시지 수와 메시지 크기(초당 비트 수)입니다. 아래 예에서는 첫 번째 그래프에 성공한 게재 수는 파란색으로, 잘못된 게재 수는 주황색으로 표시됩니다.

![](assets/report-toolbar.png)

시간 표시 막대를 변경하여 표시되는 값을 구성할 수 있습니다(1시간 보기, 3시간 보기, 24시간 보기 등). **[!UICONTROL Refresh]**&#x200B;을(를) 클릭하여 선택 내용을 확인합니다.

>[!NOTE]
>
>[Campaign 컨트롤 패널](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html){target="_blank"}을(를) 사용하여 시간당 전송된 게재 수를 모니터링할 수도 있습니다.
>
>컨트롤 패널은 모든 관리 사용자가 액세스할 수 있습니다. 사용자에게 관리자 권한을 부여하는 단계는 [이 페이지](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=ko#discover-control-panel){target="_blank"}에 자세히 설명되어 있습니다.
>

## 사용자 활동 {#user-activities}

이 보고서는 30분, 시간 또는 일별 열기, 클릭 수 및 거래 분류를 차트의 형식으로 표시합니다.

다음 옵션을 사용할 수 있습니다.

* **[!UICONTROL Opens]** : 열린 총 메시지 수입니다. 텍스트 형식의 이메일은 고려되지 않습니다. [자세히 알아보기](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : 게재의 총 링크 클릭 수입니다. 구독 취소 링크 및 미러 페이지에 대한 클릭은 고려되지 않습니다.
<!--
* **[!UICONTROL Transactions]** : Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## 게재 불가 및 이탈 {#non-deliverables-and-bounces}

이 보고서는 비게재 항목 분류와 인터넷 도메인별 바운스 수 분류를 보여줍니다.

**[!UICONTROL Number of messages processed]**&#x200B;은(는) 게재 서버에서 처리한 총 메시지 수를 나타냅니다. 이 값은 일부 게재가 중지 또는 일시 중지되었을 때(서버에서 처리되기 전에) 게재할 메시지 수보다 적습니다.

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>이 보고서에 표시된 오류는 격리 프로세스를 트리거합니다. 격리 관리에 대한 자세한 내용은 [격리 관리](../send/quarantines.md)를 참조하세요.

이 보고서의 첫 번째 섹션은 게재 불가 분류를 값 테이블 및 차트 형태로 보여줍니다.

각 오류 유형에 대해 다음이 제공됩니다.

* 이 유형의 오류 메시지 수,
* 오류가 있는 총 메시지 수와 비교한 이 유형의 오류가 있는 메시지의 비율입니다.
* 처리된 총 메시지 수와 비교한 이 유형의 오류 메시지 비율입니다.

다음 지표가 사용됩니다.

* **[!UICONTROL User unknown]** : 전자 메일 주소가 잘못되었음을 나타내기 위해 게재 중에 생성된 오류 유형입니다.
* **[!UICONTROL Invalid domain]** : 전자 메일 주소의 도메인이 잘못되었거나 존재하지 않음을 나타내기 위해 게재를 보낼 때 생성되는 오류 유형입니다.
* **[!UICONTROL Inbox full]** : 5회 게재 시도 후 생성된 오류 유형은 받는 사람의 받은 편지함에 메시지가 너무 많음을 나타냅니다.
* **[!UICONTROL Account disabled]** : 주소가 더 이상 존재하지 않음을 나타내기 위해 게재를 보낼 때 생성되는 오류 유형입니다.
* **[!UICONTROL Rejected]** : 보안 규칙(스팸 방지 소프트웨어)을 적용한 다음 IAP(인터넷 액세스 공급자)에서 주소를 거부할 때 생성되는 오류 유형입니다.
* **[!UICONTROL Unreachable]** : 메시지 배포 문자열에서 발생하는 오류 유형: SMTP 릴레이의 문제, 일시적으로 연결할 수 없는 도메인 등
* **[!UICONTROL Not connected]** : 전송 시 받는 사람의 휴대폰이 꺼져 있거나 네트워크 연결이 끊어져 있음을 나타내는 오류 형식입니다.

  >[!NOTE]
  >
  >이 표시기는 [모바일 채널](../send/send.md)의 게재에만 관련됩니다.

  `[+]` 기호를 클릭하여 값 테이블의 각 줄을 열 수 있습니다. 각 오류 유형에 대해 도메인별 오류 메시지 분류를 표시할 수 있습니다.

**[!UICONTROL Breakdown of errors per domain]**

이 보고서의 두 번째 섹션은 값 테이블 및 차트 형태로 인터넷 도메인별 오류 분류를 보여 줍니다.

각 도메인 이름에는 다음이 있습니다.

* 이 도메인에 대한 오류가 있는 메시지 수,
* 이 도메인에 대해 처리된 총 메시지 수와 비교한 이 도메인에 대해 오류가 있는 메시지의 비율입니다.
* 총 오류 메시지 수와 비교한 이 도메인에 대한 오류 메시지의 비율입니다.

[+] 기호를 클릭하여 값 테이블의 각 줄을 열 수 있습니다. 각 도메인 유형에 대해 오류 유형별로 오류 메시지 분류를 표시할 수 있습니다.

![](assets/errors-report-details.png)

>[!NOTE]
>
>이 보고서에 표시되는 도메인 이름은 큐브 수준에서 정의됩니다. 이 값을 변경하려면 **[!UICONTROL Delivery logs (broadlogrcp)]** 큐브를 편집하십시오. 자세한 정보는 [이 섹션](gs-cubes.md)을 참조하세요. **[!UICONTROL Others]** 범주에 특정 클래스에 속하지 않는 도메인 이름이 포함되어 있습니다.

## 브라우저 {#browsers}

이 보고서는 게재 수신자가 관련 기간 동안 사용한 인터넷 브라우저의 분류를 보여줍니다.

>[!NOTE]
>
>이 보고서에 표시된 값은 예상 값입니다. 게재를 클릭한 수신자만 고려됩니다.

**전역 통계**

브라우저 사용에 대한 전역 통계는 값 테이블 및 차트 형태로 표시됩니다.

![](assets/browser-report.png)

다음 지표가 사용됩니다.

* **[!UICONTROL Visitors]** : 대상을 지정하고(인터넷 브라우저당) 한 번 이상 게재를 클릭한 총 수신자 수입니다.
* **[!UICONTROL Pages viewed]** : 모든 게재에 대한 게재(인터넷 브라우저당)의 총 링크 클릭 수입니다.
* **[!UICONTROL Usage rate]** : 이 비율은 총 방문자 수와 관련된 방문자 수(인터넷 브라우저당)의 분류를 나타냅니다.

**브라우저당 통계**

글로벌 통계 값 테이블에서 각 브라우저 이름을 눌러 해당 사용 통계를 볼 수 있습니다.

![](assets/browser-report-info.png)

통계는 곡선, 도표 및 값 표의 형태로 제시된다.

**[!UICONTROL History]** 곡선은 하루 이 브라우저의 출석률을 나타냅니다. 이 비율은 방문자가 가장 높은 방문율을 보인 날에 측정된 방문자 수와 비교한 일일 방문자 수 (이 브라우저의 방문자 수)의 비율입니다.

**[!UICONTROL Breakdown per version]** 차트는 (이 브라우저의) 총 방문자 수와 비교한 버전당 방문자 수를 나타냅니다.

값 테이블에서는 다음 지표를 사용합니다.

* **[!UICONTROL Global rate]** : 이 비율은 (모든 브라우저에서) 총 방문자 수와 비교한 버전당 방문자 수를 나타냅니다.
* **[!UICONTROL Relative rate]** : 이 비율은 (이 브라우저의) 총 방문자 수와 비교한 버전당 방문자 수를 나타냅니다.


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]** : Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]** : Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]** : Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]** : This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]** : Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]** : This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]** : Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]** : Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]** : Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## 운영 체제 {#operating-systems}

이 보고서는 관련 기간 동안 게재 수신자가 사용한 운영 체제의 분류를 보여줍니다.

>[!NOTE]
>
>이 보고서에 표시된 값은 예상 값입니다. 게재를 클릭한 수신자만 고려됩니다.

**전역 통계**

운영 체제의 전역 사용 통계는 값 표 및 차트 형태로 제공됩니다.

![](assets/os-report.png)

다음 지표가 사용됩니다.

* **[!UICONTROL Visitors]** : 게재를 한 번 이상 클릭한 총 대상 받는 사람 수(운영 체제당)의 일일 평균.
* **[!UICONTROL Pages viewed]** : 모든 게재에 대한 게재 링크의 총 클릭 수(운영 체제당)의 일일 평균.
* **[!UICONTROL Rate of use]** : 이 비율은 총 방문자 수와 관련된 방문자(운영 체제당)의 분류를 나타냅니다.

**운영 체제별 통계**

글로벌 통계 값 테이블에서 각 운영 체제의 이름을 눌러 운영 체제별 통계를 확인합니다.

![](assets/os-report-details.png)

통계는 곡선, 도표 및 값 표의 형태로 제시된다.

**[!UICONTROL History]** 곡선은 하루 이 운영 체제의 사용 속도를 나타냅니다. 이 비율은 가장 높은 방문자가 있는 날에 측정된 방문자 수와 관련된 일일 방문자 수(이 운영 체제에서)의 비율입니다.

**[!UICONTROL Breakdown by version]** 차트는 이 운영 체제의 총 방문자 수와 관련된 버전별 방문자 수 분류를 나타냅니다.

값 테이블에서는 다음 지표를 사용합니다.

* **[!UICONTROL Global rate]** : 이 비율은 운영 체제 전체의 총 방문자 수와 관련된 방문자 수(버전당)의 분류를 나타냅니다.
* **[!UICONTROL Relative rate]** : 이 비율은 이 운영 체제에 대한 총 방문자 수와 관련된 방문자 수(버전당)의 분류를 나타냅니다.

## 구독 추적 {#subscription-tracking}

이 보고서를 사용하면 정보 서비스 구독을 모니터링할 수 있습니다. 여기에는 구독 및 구독 취소가 표시됩니다.

![](assets/service-report.png)

홈 페이지의 **[!UICONTROL Profiles and targets > Services and subscriptions]** 노드 또는 탐색기를 클릭하여 구독용으로 표시할 수 있습니다. 원하는 구독을 선택한 다음 **[!UICONTROL Reports]** 탭을 클릭합니다. **[!UICONTROL Subscriptions tracking]** 보고서는 기본적으로 사용할 수 있습니다. 일정 기간 동안의 구독 및 구독 취소 트렌드와 충성도 비율을 확인할 수 있습니다. 드롭다운 목록을 통해 이 데이터의 표현을 구성할 수 있습니다. 선택한 구성의 유효성을 검사하려면 **[!UICONTROL Refresh]**&#x200B;을(를) 클릭하십시오.

자세한 내용은 [이 페이지](../start/subscriptions.md)를 참조하세요.

**[!UICONTROL Number subscribed to date]**&#x200B;은(는) 현재 구독한 총 사용자 수를 나타냅니다.

**[!UICONTROL Overall evolution of subscriptions]**

값 테이블에서는 다음 지표를 사용합니다.

* **[!UICONTROL Subscribers]** : 해당 기간의 총 구독자 수.
* **[!UICONTROL Subscriptions]** : 해당 기간의 구독 수입니다.
* **[!UICONTROL Unsubscriptions]** : 관련 기간의 구독 취소 수입니다.
* **[!UICONTROL Evolution]** : 구독 취소 수에서 구독 수를 뺀 값입니다. 요금은 총 가입자 수를 기준으로 계산됩니다.
* **[!UICONTROL Loyalty]** : 해당 기간 동안 구독자의 충성도 비율입니다.

**[!UICONTROL Subscription evolution curves]**

이 차트는 관련 기간에 대한 구독 및 구독 취소의 진화를 보여 줍니다.

## 게재 통계 {#delivery-statistics}

이 보고서는 인터넷 도메인별, 처리 및 전송된 모든 메시지, 하드 및 소프트 바운스, 열기, 클릭 및 구독 취소에 대한 분류를 보여줍니다.

![](assets/broadcast-report.png)

다음 지표가 사용됩니다.

* **[!UICONTROL Emails processed]** : 게재 서버에서 처리된 총 메시지 수입니다.
* **[!UICONTROL Delivered]** : 처리된 총 메시지 수와 비교하여 성공적으로 처리된 메시지 수의 비율입니다.
* **[!UICONTROL Hard bounces]** : 처리된 총 메시지 수와 비교한 &quot;하드&quot; 바운스 수의 비율입니다.
* **[!UICONTROL Soft bounces]** : 처리된 총 메시지 수와 비교한 &quot;소프트&quot; 바운스 수의 비율입니다.

  >[!NOTE]
  >
  >하드 및 소프트 바운스에 대한 자세한 내용은 [이 페이지](../send/quarantines.md)를 참조하세요.

* **[!UICONTROL Opens]** : 처리된 메시지 수와 비교하여 메시지를 한 번 이상 연 대상 받는 사람 수의 비율입니다.
* **[!UICONTROL Clicks]** : 배달을 한 번 이상 클릭한 사람 수와 성공적으로 처리된 메시지 수의 비율입니다.
* **[!UICONTROL Unsubscription]** : 성공적으로 처리된 메시지 수와 비교한 구독 취소 링크의 클릭 수의 백분율입니다.

## 열람수 분류 {#breakdown-of-opens}

이 보고서는 해당 기간에 대한 운영 체제, 장치 및 브라우저별 열기 분석을 보여 줍니다. 각 범주별로 두 개의 차트가 사용됩니다. 첫 번째 차트에는 컴퓨터 및 모바일 디바이스에서의 열람과 관련된 통계가 표시됩니다. 두 번째 차트에는 모바일 디바이스에서의 열람과 관련된 통계만 표시됩니다.

열기 횟수는 열린 총 메시지 수에 해당합니다. 텍스트 형식 이메일은 카운트되지 않습니다. 열림 추적에 대한 자세한 내용은 [이 섹션](metrics-calculation.md#tracking-opens-)을 참조하세요.

![](assets/user-agent-report.png)

>[!NOTE]
>
>브라우저 및 운영 체제 이름은 메시지가 열린 브라우저의 사용자 에이전트에서 보낸 정보의 일부를 구성합니다. Adobe Campaign은 장치 정보를 사용하여 장치 유형을 추론합니다.
