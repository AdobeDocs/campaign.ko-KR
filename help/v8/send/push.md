---
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 5%

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
>의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 이제 모바일 등록 **비동기**. [자세히 알아보기](../architecture/staging.md)

새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭, **[!UICONTROL Deliveries]** 을 클릭하고 **[!UICONTROL Create]** 기존 게재 목록 위의 단추.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 게재를 만드는 방법에 대한 글로벌 정보는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### iOS에서 알림 보내기 {#send-notifications-on-ios}

>[!NOTE]
>
>이 기능은 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 [이 섹션](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. 을(를) 선택합니다 **[!UICONTROL Deliver on iOS]** 게재 템플릿.

   ![](assets/push_ios_1.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. 선택 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**&#x200B;모바일 애플리케이션과 관련된 서비스를 선택한 다음, 애플리케이션의 iOS 버전을 선택합니다.

   ![](assets/push_ios_3.png)

1. 선택 **[!UICONTROL Notification type]** 사이 **[!UICONTROL General notification (Alert, Sound, Badge)]** 또는 **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >다음 **자동 푸시** 모드에서는 모바일 애플리케이션에 &quot;자동&quot; 알림을 보낼 수 있습니다. 사용자가 알림의 도착을 인식하지 못합니다. 애플리케이션에 직접 전송됩니다.

1. 에서 **[!UICONTROL Title]** 필드에서 알림 센터에서 사용할 알림 목록에 표시할 제목의 레이블을 입력합니다.

   이 필드에서는 **제목** iOS 알림 페이로드의 매개 변수입니다.

1. 을(를) 추가할 수 있습니다 **[!UICONTROL Subtitle]**, 값 **부제** iOS 알림 페이로드의 매개 변수입니다.

1. 메시지의 내용을 **[!UICONTROL Message content]** 섹션에 나열된 상태로 남아 있습니다.

1. 에서 **[!UICONTROL Sound and Badge]** 탭에서 다음 옵션을 편집할 수 있습니다.

   * **[!UICONTROL Clean Badge]**: 배지 값을 새로 고치려면 이 옵션을 활성화합니다.

   * **[!UICONTROL Value]**: 애플리케이션 아이콘에 직접 표시하는 데 사용할 숫자를 설정하여 읽지 않은 새로운 정보의 수를 설정합니다.

   * **[!UICONTROL Critical alert mode]**: 사용자의 전화기가 포커스 모드에 설정되어 있거나 iPhone이 음소거된 경우에도 알림에 사운드를 추가하려면 이 옵션을 활성화합니다.

   * **[!UICONTROL Name]**: 알림을 받을 때 모바일 단말에서 재생할 사운드를 선택합니다.

   * **[!UICONTROL Volume]**: 음량: 0에서 100까지

      >[!NOTE]
      > 
      >사운드는 응용 프로그램에 포함되고 서비스를 만들 때 정의해야 합니다.
      >
      >iOS에 대한 구성 지침은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en).
   ![](assets/push_ios_5.png)

1. 에서 **[!UICONTROL Application variables]** 탭, **[!UICONTROL Application variables]** 이 자동으로 추가됩니다. 알림 동작을 정의할 수 있도록 해줍니다. 예를 들어, 사용자가 알림을 활성화하면 표시되는 특정 애플리케이션 화면을 구성할 수 있습니다.

   이 작업에 대한 자세한 정보는 [이 섹션](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en)을 참조하십시오.

1. 에서 **[!UICONTROL Advanced]** 탭에서 다음 일반 옵션을 편집할 수 있습니다.

   * **[!UICONTROL Mutable content]**: 모바일 애플리케이션에서 미디어 컨텐츠를 다운로드할 수 있도록 하려면 이 옵션을 활성화합니다.

   * **[!UICONTROL Thread-id]**: 관련 알림을 함께 그룹화하는 데 사용되는 식별자입니다.

   * **[!UICONTROL Category]**: 작업 버튼을 표시할 카테고리 ID의 이름입니다. 이러한 알림은 사용자가 애플리케이션을 열거나 탐색하지 않고도 알림에 응답하여 다른 작업을 보다 빠르게 수행할 수 있도록 합니다.

   ![](assets/push_ios_6.png)

1. 시간 구분 알림의 경우 다음 옵션을 지정할 수 있습니다.

   * **[!UICONTROL Target content ID]**: 알림을 열 때 전송할 응용 프로그램 창을 타겟팅하는 데 사용되는 식별자입니다.

   * **[!UICONTROL Launch image]**: 표시할 launch 이미지 파일의 이름입니다. 사용자가 애플리케이션을 실행하도록 선택하면 애플리케이션의 시작 화면 대신 선택한 이미지가 표시됩니다.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: 기본적으로 시스템은 알림을 즉시 표시하고 화면을 켜고 사운드를 재생할 수 있습니다. 알림은 포커스 모드를 벗어나지 않습니다.

      * **[!UICONTROL Passive]**: 이 시스템은 화면을 켜거나 사운드를 재생하지 않고 알림 목록에 알림을 추가합니다. 알림은 포커스 모드를 벗어나지 않습니다.

      * **[!UICONTROL Time sensitive]** 즉시 알림을 표시하고 화면을 켜고 사운드를 재생하며 포커스 모드를 시작할 수 있습니다. 이 수준에는 Apple의 특별한 권한이 필요하지 않습니다.

      * **[!UICONTROL Critical]** 알림 메시지를 즉시 표시하고 화면을 켜고 음소거 스위치나 포커스 모드를 우회합니다. 이 수준에는 Apple의 특수 권한이 필요합니다.
   * **[!UICONTROL Relevance score]**: 관련성 점수를 0에서 100으로 설정합니다. 시스템은 이를 사용하여 알림 요약의 알림을 정렬합니다.

   ![](assets/push_ios_7.png)

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   ![](assets/push-ios-preview.png)

### Android에서 알림 보내기 {#send-notifications-on-android}

1. 을(를) 선택합니다 **[!UICONTROL Deliver on Android (android)]** 게재 템플릿.

   ![](assets/push-template-android.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 선택 **[!UICONTROL Subscribers of an Android mobile application]**&#x200B;모바일 애플리케이션(이 경우 네오트립)과 관련된 서비스를 선택한 다음 애플리케이션의 Android 버전을 선택합니다.

   ![](assets/push-android-subscribers.png)

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
