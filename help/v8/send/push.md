---
solution: Campaign v8
product: Adobe Campaign
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# 푸시 알림 만들기 및 전송

모바일 앱 게재를 사용하면 iOS 및 Android 시스템에 알림을 전송할 수 있습니다.

Adobe Campaign에서 푸시 알림을 전송하려면 다음을 수행해야 합니다.

1. Campaign 환경 구성
1. 모바일 애플리케이션에 대한 모바일 애플리케이션 유형 정보 서비스를 만듭니다.
1. 애플리케이션의 iOS 및 Android 버전을 이 서비스에 추가합니다.
1. iOS 및 Android 모두에 대한 게재를 만듭니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 모바일 앱을 시작하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Adobe SDK와 통합

### Campaign SDK 통합

Campaign SDK를 사용하면 모바일 애플리케이션을 Adobe Campaign 플랫폼에 간편하게 통합할 수 있습니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 Campaign SDK를 앱과 통합하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Launch에서 Campaign 확장 구성

Campaign Classic 확장을 활용하여 Adobe Experience Platform Launch SDK를 Campaign과 통합할 수 있습니다.

[!DNL :arrow_upper_right:] 자세한 내용은  [Adobe Mobile SDK 문서에서 알아보십시오](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Campaign에서 앱 설정 구성

Adobe Campaign에서 iOS 및 Android 앱 설정을 정의해야 합니다.

[!DNL :arrow_upper_right:] iOS에 대한 구성 지침은  [Campaign Classic v7 설명서에 자세히 설명되어 있습니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] Android에 대한 구성 지침은  [Campaign Classic v7 설명서에 자세히 설명되어 있습니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## 첫 번째 푸시 알림 만들기

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 첫 번째 푸시 알림을 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>Campaign v8 모바일 등록을 사용하면 이제 **비동기**&#x200B;가 됩니다. [자세히 알아보기](../dev/staging.md)
