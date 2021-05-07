---
solution: Campaign
product: Adobe Campaign
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작하기
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# 푸시 알림 만들기 및 보내기

모바일 앱 게재를 사용하면 iOS 및 Android 시스템에 알림을 보낼 수 있습니다.

Adobe Campaign에서 푸시 알림을 전송하려면 다음을 수행해야 합니다.

1. 캠페인 환경 구성
1. 모바일 응용 프로그램용 모바일 응용 프로그램 유형 정보 서비스를 만듭니다.
1. 이 서비스에 애플리케이션의 iOS 및 Android 버전을 추가합니다.
1. iOS 및 Android 모두에 대한 배달을 만듭니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)에서 모바일 앱을 시작하는 방법에 대해 학습합니다.

## Adobe SDK와 통합

### 캠페인 SDK 통합

Campaign SDK는 모바일 애플리케이션을 Adobe Campaign 플랫폼으로 쉽게 통합합니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)에서 Campaign SDK를 앱과 통합하는 방법을 알아봅니다.

### 론치에서 캠페인 확장 구성

Campaign Classic 확장을 활용하여 Adobe Experience Platform Launch SDK를 Campaign과 통합할 수 있습니다.

:arrow_upper_right:[Adobe Mobile SDK 설명서](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)에서 자세한 내용

## Campaign에서 앱 설정 구성

Adobe Campaign에서 iOS 및 Android 앱 설정을 정의해야 합니다.

:arrow_upper_right:iOS에 대한 구성 지침은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)에 자세히 설명되어 있습니다.

:arrow_upper_right:Android에 대한 구성 지침은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)에 자세히 설명되어 있습니다.

## 첫 번째 푸시 알림 만들기

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)에서 첫 번째 푸시 알림을 만드는 방법에 대해 알아봅니다.
