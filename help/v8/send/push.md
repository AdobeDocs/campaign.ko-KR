---
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: a18141274b4934d45ecc82ce5d872c86e141a96f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---

# 푸시 알림 만들기 및 전송

모바일 앱 게재를 사용하면 iOS 및 Android 시스템에 알림을 전송할 수 있습니다.

Adobe Campaign에서 푸시 알림을 전송하려면 다음을 수행해야 합니다.

1. Campaign 환경 구성
1. 모바일 애플리케이션에 대한 모바일 애플리케이션 유형 정보 서비스를 만듭니다.
1. 애플리케이션의 iOS 및 Android 버전을 이 서비스에 추가합니다.
1. iOS 및 Android 모두에 대한 게재를 만듭니다.

![](../assets/do-not-localize/book.png) 에서 모바일 앱을 시작하는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;}

## Campaign SDK 통합

Campaign SDK를 사용하면 모바일 애플리케이션을 Adobe Campaign 플랫폼에 간편하게 통합할 수 있습니다.

호환 가능한 SDK 버전은 [Campaign 호환성 매트릭스](../start/compatibility-matrix.md#MobileSDK).

![](../assets/do-not-localize/glass.png) 에서 Campaign Android 및 iOS SDK를 앱과 통합하는 방법을 알아봅니다. [이 섹션](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

-->

## Campaign에서 앱 설정 구성

Adobe Campaign에서 iOS 및 Android 앱 설정을 정의해야 합니다.

![](../assets/do-not-localize/book.png) iOS에 대한 구성 지침은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) Android에 대한 구성 지침은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;}

## 첫 번째 푸시 알림 만들기

이 섹션에서는 iOS 및 Android 알림 게재와 관련된 요소에 대해 자세히 설명합니다.

>[!CAUTION]
>
>Campaign v8을 사용하면 이제 모바일 등록이 이루어집니다 **비동기**. [자세히 알아보기](../dev/staging.md)

새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭, **[!UICONTROL Deliveries]** 을 클릭하고 **[!UICONTROL Create]** 기존 게재 목록 위의 단추.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 게재를 만드는 방법에 대한 글로벌 정보는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### iOS에서 알림 보내기 {#send-notifications-on-ios}

1. 을(를) 선택합니다 **[!UICONTROL Deliver on iOS]** 게재 템플릿 을(를) 클릭하고 **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. 선택 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**&#x200B;모바일 애플리케이션과 관련된 서비스를 선택한 다음, 애플리케이션의 iOS 버전을 선택합니다.

   ![](assets/push-ios-subscribers.png)

1. 알림 유형을 선택합니다. **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** 또는 **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. 에서 **[!UICONTROL Title]** 필드에서 알림에 표시할 제목의 레이블을 입력합니다.

1. 을(를) 입력합니다. **[!UICONTROL Message]** 그리고 **[!UICONTROL Value of the badge]** 선택한 알림 유형에 따라 다릅니다.

1. 다음 요소를 정의할 수도 있습니다.

   * 다음 **[!UICONTROL Action button]** 경고 알림에 나타나는 작업 단추에 대한 레이블을 정의할 수 있습니다(**action_loc_key** 페이로드 필드).

   * 에서 **[!UICONTROL Play a sound]** 필드에서는 알림을 받을 때 모바일 단말이 재생할 사운드를 선택합니다.

   * 에서 **[!UICONTROL Application variables]** 필드에서 각 변수의 값을 입력합니다. 예를 들어 사용자가 알림을 활성화하면 표시되는 특정 애플리케이션 화면을 구성할 수 있습니다.

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   ![](assets/push-ios-preview.png)


### Android에서 알림 보내기 {#send-notifications-on-android}

1. 을(를) 선택합니다 **[!UICONTROL Deliver on Android (android)]** 게재 템플릿.

   ![](assets/push-template-android.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 선택 **[!UICONTROL Subscribers of an Android mobile application]**&#x200B;모바일 애플리케이션(이 경우 네오트립)과 관련된 서비스를 선택한 다음 애플리케이션의 Android 버전을 선택합니다.

   ![](assets/push-ios-subscribers.png)

1. 그런 다음 알림에 사용할 콘텐츠를 입력합니다.

   ![](assets/push-android-content.png)

1. 을(를) 클릭합니다. **[!UICONTROL Insert emoticon]** 푸시 알림에 이모티콘을 삽입하는 아이콘.

1. 에서 **[!UICONTROL Application variables]** 필드에서 각 변수의 값을 입력합니다. 예를 들어 사용자가 알림을 활성화하면 표시되는 특정 애플리케이션 화면을 구성할 수 있습니다.

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   <!--![](assets/push-android-preview.png)-->

## 푸시 알림 테스트, 전송 및 모니터링

증명을 보내고 최종 게재를 보내려면 이메일 게재와 동일한 프로세스를 사용합니다. Campaign Classic v7 설명서에서 자세히 알아보기:

* 게재 유효성 검사 및 증명 보내기
   ![](../assets/do-not-localize/book.png) [게재의 유효성을 검사하는 주요 단계를 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}

* 게재 확인 및 보내기
   ![](../assets/do-not-localize/book.png) [게재를 보내는 주요 단계를 배웁니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;}

메시지를 보낸 후 게재를 모니터링하고 추적할 수 있습니다. Campaign Classic v7 설명서에서 자세히 알아보기:

* 푸시 알림 격리
   ![](../assets/do-not-localize/book.png) [푸시 알림 격리에 대한 자세한 정보](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;}

* 문제 해결
   ![](../assets/do-not-localize/book.png) [푸시 알림 문제 해결 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target=&quot;_blank&quot;}
