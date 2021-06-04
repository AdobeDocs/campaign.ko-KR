---
product: Adobe Campaign
title: Campaign을 Adobe Analytics과 함께 사용하기
description: Campaign과 Analytics를 통합하는 방법을 알아봅니다
feature: 개요
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 6a22bdd563bb0be26df12ce8d2b6da266d16f2e3
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 0%

---

# Campaign을 Adobe Analytics과 함께 사용하기

Campaign과 Analytics를 통합하도록 Adobe Analytics을 구성할 수 있습니다.

이 통합을 통해 Adobe Campaign 및 Adobe Analytics은 **Web Analytics 커넥터** 추가 기능을 통해 상호 작용할 수 있습니다. 이 통합은 Adobe Campaign이 Adobe Analytics에 제공하는 이메일 캠페인의 지표와 속성을 보냅니다.

[!DNL :speech_balloon:] 관리 Cloud Services 사용자는  [Adobe](../start/campaign-faq.md#support) 에 문의하여 Campaign을 Adobe Experience Cloud 서비스 및 솔루션과 연결하십시오. 인스턴스에 대해 IMS(Identity Management 서비스 Adobe)을 구현해야 합니다. [자세히 알아보기](../start/connect.md#connect-ims) Web Analytics 커넥터 추가 기능은 전용 패키지를 통해 사용자 환경에 설치해야 합니다.

Adobe Campaign에는 Adobe Analytics 커넥터를 사용하여 인터넷 대상자(Web Analytics)를 측정하는 방법이 있습니다. 웹 분석 도구를 사용하면 Adobe Campaign에서 지표 및 캠페인 속성을 Analytics에 전달할 수 있습니다.

각 도구의 작업 둘레는 다음과 같습니다.

* **Adobe** Analytics는 Adobe Campaign으로 시작한 이메일 캠페인을 스마트합니다

* **Adobe** Campaign은 표시기와 캠페인 속성을 커넥터로 전송하며 이 커넥터는 웹 분석 도구로 전달합니다


>[!CAUTION]
>
>Adobe Analytics 커넥터가 트랜잭션 메시지(메시지 센터)와 호환되지 않습니다.

Campaign-Analytics 연결을 설정하려면 다음 작업을 수행해야 합니다.

1. [Adobe Analytics에서 보고서 세트 만들기](#report-suite-analytics)
1. [전환 변수 및 성공 이벤트 구성](#configure-conversion-success)
1. [Adobe Campaign에서 외부 계정 구성](#external-account-ac)

## Analytics 보고서 세트 {#report-suite-analytics} 만들기

[!DNL Adobe Analytics]에서 **[!UICONTROL Report suite]**&#x200B;을(를) 만들려면 아래 단계를 수행하십시오.

1. [!DNL Adobe Analytics]에서 **[!UICONTROL Admin tab]**&#x200B;을 선택한 다음 **[!UICONTROL All admin]**&#x200B;를 클릭합니다.

   ![](assets/analytics_connnector_1.png)

1. **[!UICONTROL Report suites]**&#x200B;을(를) 클릭합니다.

   ![](assets/analytics_connnector_2.png)

1. **[!UICONTROL Report suite manager]** 페이지에서 **[!UICONTROL Create new]** 를 클릭한 다음 **[!UICONTROL Report suite]** 를 클릭합니다.

   **[!UICONTROL Report suite]** 만들기에 대한 자세한 절차는 이 [섹션](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=en#prerequisites)을 참조하십시오.

   ![](assets/analytics_connnector_3.png)

1. 템플릿을 선택합니다.

1. 다음 정보로 새 보고서 세트를 구성합니다.

   * **[!UICONTROL Report Suite ID]**
   * **[!UICONTROL Site Title]**
   * **[!UICONTROL Time Zone]**
   * **[!UICONTROL Go Live Date]**
   * **[!UICONTROL Estimated Page Views Per Day]**

   ![](assets/analytics_connnector_4.png)

1. 구성된 경우 **[!UICONTROL Create report suite]** 을 클릭합니다.

## 전환 변수 및 성공 이벤트 구성 {#configure-conversion-success}

**[!UICONTROL Report suite]**&#x200B;을 작성한 후 다음과 같이 **[!UICONTROL Conversion variables]** 및 **[!UICONTROL Success events]**&#x200B;를 구성해야 합니다.

1. 이전에 구성한 **[!UICONTROL Report suite]** 을 선택합니다.

1. **[!UICONTROL Edit settings]** 단추에서 **[!UICONTROL Conversion]** > **[!UICONTROL Conversion variables]**&#x200B;를 선택합니다.

   ![](assets/analytics_connnector_5.png)

1. 이메일 캠페인의 영향을 측정하는 데 필요한 식별자(즉, 내부 캠페인 이름(cid) 및 iNmsBroadlog(bid) 테이블 ID를 만들려면 **[!UICONTROL Add new]** 를 클릭합니다.

   **[!UICONTROL Conversion variables]**&#x200B;을 편집하는 방법에 대해 알아보려면 이 [섹션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=en#admin-tools)을 참조하십시오.

   ![](assets/analytics_connnector_6.png)

1. 완료되면 **[!UICONTROL Save]** 을 클릭합니다.

1. 그런 다음 **[!UICONTROL Success events]**&#x200B;을(를) 만들려면 **[!UICONTROL Edit settings]** 단추에서 **[!UICONTROL Conversion]** > **[!UICONTROL Success events]**&#x200B;를 선택합니다.

   ![](assets/analytics_connnector_7.png)

1. **[!UICONTROL Add new]** 을 클릭하여 다음 **[!UICONTROL Success events]**&#x200B;을 구성합니다.

   * **[!UICONTROL Clicked]**
   * **[!UICONTROL Opened]**
   * **[!UICONTROL Person clicks]**
   * **[!UICONTROL Processed]**
   * **[!UICONTROL Scheduled]**
   * **[!UICONTROL Sent]**
   * **[!UICONTROL Total bounces]**
   * **[!UICONTROL Unique Clicks]**
   * **[!UICONTROL Unique Opens]**
   * **[!UICONTROL Unsubscribed]**

   **[!UICONTROL Success events]**&#x200B;을 구성하는 방법에 대해 알아보려면 이 [섹션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=en#admin-tools)을 참조하십시오

   ![](assets/analytics_connnector_8.png)

1. 완료되면 **[!UICONTROL Save]** 을 클릭합니다.

보고서 세트가 구성되면 Adobe Campaign에서 **[!UICONTROL External accounts]**&#x200B;을 구성해야 합니다.

## Campaign 외부 계정 구성 {#external-account-ac}

이제 두 솔루션 간에 동기화를 활성화하려면 Adobe Campaign에서 **[!UICONTROL Web Analytics]** 외부 계정을 구성해야 합니다.

외부 계정을 구성할 때 **[!UICONTROL Report suite]**, **[!UICONTROL Conversion variables]** 또는 **[!UICONTROL Success events]** 중 하나가 표시되지 않으면 사용자와 연결된 **[!UICONTROL Product profile]**&#x200B;에서 새로 만든 이 구성 요소에 대한 권한이 누락되었음을 의미합니다.

자세한 내용은 [Adobe Analytics용 제품 프로필](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=en#product-profile-admins) 페이지를 참조하십시오.

1. Adobe Campaign 트리의 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]** 폴더로 이동하고 **[!UICONTROL New]** 를 클릭합니다.

   ![](assets/analytics_connnector_9.png)

1. 드롭다운 목록을 사용하여 **[!UICONTROL Web Analytics]** 유형과 **[!UICONTROL Integration]** 드롭다운에서 **[!UICONTROL Adobe Analytics]** 유형을 선택합니다.

   ![](assets/analytics_connnector_10.png)

1. **[!UICONTROL Integration]** 드롭다운 옆에 있는 **[!UICONTROL Configure]** 을 클릭합니다.

1. **[!UICONTROL Configure Analytics integration]** 창에서 다음 정보를 제공하는 앞에서 만든 보고서 세트에 외부 계정을 매핑합니다.

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics Company]**
   * **[!UICONTROL Report Suite]**


1. **[!UICONTROL eVars]** 카테고리에서 [!DNL Adobe Analytics]에 구성된 두 **[!UICONTROL Conversion variables]**&#x200B;을 매핑합니다.

   ![](assets/analytics_connnector_11.png)

1. **[!UICONTROL Events]** 카테고리에서 [!DNL Adobe Analytics]에 구성된 10개의 **[!UICONTROL Success events]**&#x200B;을 매핑합니다.

1. 완료되면 **[!UICONTROL Submit]** 을 클릭합니다. Adobe Campaign은 매핑된 Analytics **[!UICONTROL Report Suite]**&#x200B;에 **[!UICONTROL Data source]**, **[!UICONTROL Calculated metrics]**, **[!UICONTROL Remarketing segments]** 및 **[!UICONTROL Classifications]**&#x200B;를 만듭니다.

   [!DNL Adobe Analytics] 과 Adobe Campaign 간의 동기화가 완료되면 창을 닫을 수 있습니다.

1. 설정은 **[!UICONTROL Configure Analytics integration]** 창의 **[!UICONTROL Data Settings]** 탭에서 볼 수 있습니다.

   **[!UICONTROL Sync]** 단추를 사용하면 [!DNL Adobe Campaign]이 [!DNL Adobe Analytics]에서 수행한 이름 변경 사항을 동기화합니다. 구성 요소가 [!DNL Adobe Analytics]에서 삭제되면 구성 요소는 [!DNL Adobe Campaign]에서 취소되거나 **찾을 수 없음** 메시지와 함께 표시됩니다.

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > 이 버전의 Campaign v8에서는 세그먼트를 추가하거나 제거할 수 없습니다.

1. **[!UICONTROL External account]**&#x200B;에서 **[!UICONTROL Enrich the formula...]** 링크를 클릭하여 URL 계산 공식을 변경하여 웹 분석 도구 통합 정보(캠페인 ID)와 활동을 추적해야 하는 사이트의 도메인을 지정합니다.

   ![](assets/analytics_connnector_13.png)

1. 사이트의 도메인 이름을 지정합니다.

   ![](assets/analytics_connnector_14.png)

1. **[!UICONTROL Next]** 을 클릭하고 도메인 이름이 저장되었는지 확인합니다.

   ![](assets/analytics_connnector_15.png)

1. 필요한 경우 계산 공식을 과부로드할 수 있습니다. 이렇게 하려면 상자를 선택하고 창에서 바로 공식을 편집합니다.

   >[!IMPORTANT]
   >
   >이 구성 모드는 전문가 사용자용으로 예약되어 있습니다.이 수식의 오류가 발생하면 이메일 게재가 중지될 수 있습니다.

1. **[!UICONTROL Advanced]** 탭에서는 더 많은 기술 설정을 구성하거나 수정할 수 있습니다.

   * **[!UICONTROL Lifespan]**:기술 워크플로우로 Adobe Campaign에서 웹 이벤트가 복구되는 지연 시간(일)을 지정할 수 있도록 해줍니다. 기본값:180일.
   * **[!UICONTROL Persistence]**:모든 웹 이벤트(예: 구매)가 리마케팅 캠페인에 귀속될 수 있는 기간, 기본값:7일.

>[!NOTE]
>
>여러 대상 측정 도구를 사용하는 경우 외부 계정을 만들 때 **[!UICONTROL Partners]** 드롭다운 목록에서 **[!UICONTROL Other]** 을 선택할 수 있습니다. 게재 속성에서 하나의 외부 계정만 참조할 수 있습니다.따라서 Adobe에서 기대하는 매개 변수와 사용된 다른 모든 측정 도구를 추가하여 추적된 URL의 공식을 조정해야 합니다.

## 웹 분석 프로세스 {#technical-workflows-of-web-analytics-processes} 의 기술 워크플로우

Adobe Campaign과 Adobe Analytics 간의 데이터 교환은 백그라운드 작업으로 실행되는 기술 워크플로우로 처리됩니다.

이 워크플로우는 Campaign Explorer 트리의 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]** 폴더에서 사용할 수 있습니다.

![](assets/webanalytics_workflows.png)

**[!UICONTROL Sending of indicators and campaign attributes]** 워크플로우를 통해 Adobe Campaign을 통해 이메일 캠페인 표시기를 Adobe Analytics 커넥터를 사용하여 Adobe Experience Cloud으로 보낼 수 있습니다. 이 워크플로우는 매일 오전 4시에 트리거되며 데이터를 Analytics에 전송하는 데 24시간이 걸릴 수 있습니다.

이 워크플로우를 다시 시작하지 않아야 합니다. 그렇지 않으면 Analytics 결과를 왜곡할 수 있는 모든 이전 데이터가 다시 전송됩니다.

관련 지표는 다음과 같습니다.

* **[!UICONTROL Messages to deliver]** (@toDeliver)
* **[!UICONTROL Processed]** (@processed)
* **[!UICONTROL Success]** (@success)
* **[!UICONTROL Total count of opens]** (@totalRecipientOpen)
* **[!UICONTROL Recipients who have opened]** (@recipientOpen)
* **[!UICONTROL Total number of recipients who clicked]** (@totalRecipientClick)
* **[!UICONTROL People who clicked]** (@personClick)
* **[!UICONTROL Number of distinct clicks]** (@recipientClick)
* **[!UICONTROL Opt-Out]** (@optOut)
* **[!UICONTROL Errors]** (@error)

>[!NOTE]
>
>전송된 데이터는 지표 데이터에서 음수 값을 초래할 수 있는 마지막 스냅샷을 기반으로 하는 델타는 됩니다.

전송된 속성은 다음과 같습니다.

* **[!UICONTROL Internal name]** (@internalName)
* **[!UICONTROL Label]** (@label)
* **[!UICONTROL Label]** (작업/@label):캠페인 패키지 **** 가 설치된 경우에만
* **[!UICONTROL Nature]** (작업/@nature):캠페인 패키지 **** 가 설치된 경우에만
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (예약/@contactDate)

## 게재 추적 {#tracking-deliveries-in-adobe-campaign}

Adobe Campaign에서 게재를 보낸 후 Adobe Experience Cloud이 사이트에서 활동을 추적할 수 있도록 하려면 게재 속성에서 일치하는 커넥터를 참조해야 합니다. 이렇게 하려면 다음 단계를 적용합니다.

1. 추적할 캠페인 게재를 엽니다.

   ![](assets/webanalytics_delivery_properties_003.png)

1. 게재 속성을 엽니다.
1. **[!UICONTROL Web Analytics]** 탭으로 이동하여 이전에 만든 외부 계정을 선택합니다. Adobe Campaign](#external-account-ac)에서 외부 계정 구성 을 참조하십시오.[

   ![](assets/webanalytics_delivery_properties_002.png)

1. 이제 Adobe Analytics에서 게재를 보내고 보고서에 액세스할 수 있습니다.


**관련 항목**

* [Campaign - Experience Cloud 트리거 통합](ac-triggers.md)
