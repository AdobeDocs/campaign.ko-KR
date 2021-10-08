---
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 4%

---

# Create and send push notifications

Mobile app deliveries let you send notifications to iOS and Android systems.

To send push notifications in Adobe Campaign, you need to:

1. Campaign 환경 구성
1. 모바일 애플리케이션에 대한 모바일 애플리케이션 유형 정보 서비스를 만듭니다.
1. Add the iOS and Android versions of the application to this service.
1. iOS 및 Android 모두에 대한 게재를 만듭니다.

![](../assets/do-not-localize/book.png)  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;}에서 모바일 앱을 시작하는 방법을 알아봅니다

## Adobe SDK와 통합

### Campaign SDK 통합

Campaign SDK를 사용하면 모바일 애플리케이션을 Adobe Campaign 플랫폼에 간편하게 통합할 수 있습니다.

호환 가능한 SDK 버전은 [Campaign 호환성 매트릭스](../start/compatibility-matrix.md#MobileSDK)에 나열되어 있습니다.

![](../assets/do-not-localize/glass.png) 이 섹션에서 Campaign Android 및 iOS SDK를 앱과 통합하는  [방법을 알아봅니다](../config/push-config.md)

### Launch에서 Campaign 확장 구성

Campaign Classic 확장을 활용하여 Adobe Experience Platform Launch SDK를 Campaign과 통합할 수 있습니다.

![](../assets/do-not-localize/book.png) 자세한 내용은  [Adobe Mobile SDK 설명서](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target=&quot;_blank&quot;}에서 알아보십시오

## Campaign에서 앱 설정 구성

Adobe Campaign에서 iOS 및 Android 앱 설정을 정의해야 합니다.

![](../assets/do-not-localize/book.png) iOS에 대한 구성 지침은  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target=&quot;_blank&quot;}에 자세히 설명되어 있습니다

![](../assets/do-not-localize/book.png) Android에 대한 구성 지침은  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;}에 자세히 설명되어 있습니다

## 첫 번째 푸시 알림 만들기

이 섹션에서는 iOS 및 Android 알림 게재와 관련된 요소에 대해 자세히 설명합니다.

>[!CAUTION]
>
>Campaign v8을 사용하면 이제 모바일 등록이 **비동기**&#x200B;입니다. [자세히 알아보기](../dev/staging.md)

새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭으로 이동하여 **[!UICONTROL Deliveries]** 을 클릭하고 기존 게재 목록 위에 있는 **[!UICONTROL Create]** 버튼을 클릭합니다.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 게재를 만드는 방법에 대한 글로벌 정보는  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}를 참조하십시오

### iOS에서 알림 보내기 {#send-notifications-on-ios}

1. **[!UICONTROL Deliver on iOS]** 게재 템플릿을 선택하고 **[!UICONTROL Continue]** 을 클릭합니다.

   ![](assets/push-template-ios.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. Select **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, select the service relevant to your mobile application, then select the iOS version of the application.

   ![](assets/push-ios-subscribers.png)

1. 알림 유형을 선택합니다. **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** 또는 **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. **[!UICONTROL Title]** 필드에서 알림에 표시할 제목의 레이블을 입력합니다.

1. 선택한 알림 유형에 따라 **[!UICONTROL Message]** 및 **[!UICONTROL Value of the badge]** 을 입력합니다.

1. 다음 요소를 정의할 수도 있습니다.

   * **[!UICONTROL Action button]**&#x200B;을(를) 사용하면 경고 알림(**action_loc_key** 페이로드의 필드)에 나타나는 작업 단추에 대한 레이블을 정의할 수 있습니다.

   * 알림을 받을 때 모바일 터미널에서 재생할 사운드를 **[!UICONTROL Play a sound]** 필드에서 선택합니다.

   * **[!UICONTROL Application variables]** 필드에 각 변수의 값을 입력합니다. 예를 들어 사용자가 알림을 활성화하면 표시되는 특정 애플리케이션 화면을 구성할 수 있습니다.

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   ![](assets/push-ios-preview.png)


### Android에서 알림 보내기 {#send-notifications-on-android}

1. Select the **[!UICONTROL Deliver on Android (android)]** delivery template.

   ![](assets/push-template-android.png)

1. 알림의 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]** 를 클릭합니다.

   ![](assets/push-android-select-target.png)

1. **[!UICONTROL Subscribers of an Android mobile application]** 을 선택하고 모바일 애플리케이션과 관련된 서비스(이 경우 Neotrip)를 선택한 다음, 애플리케이션의 Android 버전을 선택합니다.

   ![](assets/push-ios-subscribers.png)

1. 그런 다음 알림에 사용할 콘텐츠를 입력합니다.

   ![](assets/push-android-content.png)

1. 푸시 알림에 이모티콘을 삽입하려면 **[!UICONTROL Insert emoticon]** 아이콘을 클릭합니다.

1. In the **[!UICONTROL Application variables]** field, enter the value of each variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   <!--![](assets/push-android-preview.png)-->

## Test, send and monitor your push notifications

증명을 보내고 최종 게재를 보내려면 이메일 게재와 동일한 프로세스를 사용합니다. Campaign Classic v7 설명서에서 자세히 알아보기:

* 게재 유효성 검사 및 증명 보내기
   ![](../assets/do-not-localize/book.png) [게재{target=&quot;](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)_blank&quot;} 유효성 검사를 위한 주요 단계를 배웁니다.

* 게재 확인 및 보내기
   ![](../assets/do-not-localize/book.png) [게재](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;}를 보내는 주요 단계를 배웁니다.

After sending messages, you can monitor and track your deliveries. Campaign Classic v7 설명서에서 자세히 알아보기:

* 푸시 알림 격리
   ![](../assets/do-not-localize/book.png) [푸시 알림 격리에 대한 자세한 정보](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;}

* 문제 해결
   ![](../assets/do-not-localize/book.png) [푸시 알림](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en) 문제 해결 방법 알아보기{target=&quot;_blank&quot;}
