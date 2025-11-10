---
title: AEP SDK 및 Campaign 통합
description: Adobe Experience Platform mobile SDK을 앱과 통합하는 방법에 대해 알아봅니다
feature: Push
role: Admin, Developer
level: Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 1a75f411-3f71-4114-b738-277820dc6138
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '1679'
ht-degree: 5%

---

# 푸시 알림 채널 구성 {#push-notification-configuration}

Adobe Campaign을 사용하여 푸시 알림을 전송하려면 먼저 이 페이지에 설명된 대로 환경 및 앱을 구성해야 합니다. Adobe Campaign에서 푸시 알림을 전송하는 채널은 모바일 앱 채널입니다.

>[!CAUTION]
>
>Android FCM(Firebase Cloud Messaging) 서비스에 대한 몇 가지 중요한 변경 사항은 2024년에 릴리스될 예정이며 Adobe Campaign 구현에 영향을 미칠 수 있습니다. 이 변경 사항을 지원하려면 Android 푸시 메시지에 대한 구독 서비스 구성을 업데이트해야 할 수 있습니다. 미리 확인하고 조치를 취할 수 있습니다.

Adobe Campaign을 사용하여 푸시 알림 전송을 시작하기 전에 모바일 앱과 Adobe Experience Platform의 태그에 대한 구성 및 통합이 제대로 되어 있는지 확인해야 합니다. Adobe Experience Platform Mobile SDK은 Android 및 iOS 호환 SDK를 통해 모바일에 대한 클라이언트측 통합 API를 제공합니다.

Adobe Experience Platform Mobile SDK를 사용하여 앱을 설정하려면 다음 단계를 따르십시오.

1. [필수 구성 요소](#before-starting)를 확인하십시오.
1. Adobe Experience Platform 데이터 수집에서 [모바일 태그 속성](#launch-property)을 설정합니다.
1. 이 페이지에서 [자세히](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}대로 Adobe Experience Platform Mobile SDK을 가져옵니다.
1. (선택 사항) 로깅 및 라이프사이클 지표를 사용하도록 설정합니다(자세한 정보: 이 [페이지](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}).
1. (선택 사항) 구현의 유효성을 검사하려면 [Adobe Experience Platform Assurance을 앱에 추가](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"}하십시오. 이 페이지[에서 Adobe Experience Platform Assurance 확장 ](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}을(를) 구현하는 방법을 알아보세요.
1. 이 페이지의 [자세히](#push-service)로 Adobe Campaign에서 iOS 및 Android Mobile Services를 구성합니다.
1. 모바일 속성에 [Adobe Campaign 확장](#configure-extension)을 설치하고 구성합니다.
1. 앱에서 Adobe Experience Platform Mobile SDK를 설정하려면 [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"}를 따르십시오.

## 필수 구성 요소 {#before-starting}

### 권한 설정 {#setup-permissions}

모바일 애플리케이션을 만들기 전에 먼저 Adobe Experience Platform의 태그에 대한 올바른 사용자 권한이 있는지 확인하거나 사용자에게 할당해야 합니다. Adobe Experience Platform의 태그에 대한 사용자 권한은 Adobe Admin Console을 통해 사용자에게 할당됩니다. 자세한 내용은 [태그 설명서](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}를 참조하세요.

>[!CAUTION]
>
>푸시 구성은 전문가 사용자가 수행해야 합니다. 구현 모델 및 이 구현에 관련된 담당자에 따라 단일 제품 프로필에 전체 권한 집합을 할당하거나 앱 개발자와 **Adobe Campaign** 관리자 간에 권한을 공유해야 할 수 있습니다.

**속성** 및 **회사** 권한을 할당하려면 아래 단계를 따르십시오.

1. **[!DNL Admin Console]**&#x200B;에 액세스합니다.
1. **[!UICONTROL Products]** 탭에서 **[!UICONTROL Adobe Experience Platform Data Collection]** 카드를 선택합니다.
1. 기존 **[!UICONTROL Product Profile]**&#x200B;을(를) 선택하거나 **[!UICONTROL New profile]** 단추를 사용하여 새 을(를) 만듭니다. **[!UICONTROL New profile]** Admin Console 설명서[에서 새 ](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}을(를) 만드는 방법을 알아보세요.
1. **[!UICONTROL Permissions]** 탭에서, **[!UICONTROL Property Rights]**&#x200B;를 선택합니다.
1. **[!UICONTROL Add all]**&#x200B;을(를) 클릭합니다. 이렇게 하면 제품 프로필에 다음 권한이 추가됩니다.
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Adobe Campaign 확장을 설치 및 게시하고 **Adobe Experience Platform Mobile SDK**&#x200B;에 앱 속성을 게시하려면 이러한 권한이 필요합니다.

1. 그런 다음 왼쪽 메뉴에서 **[!UICONTROL Company rights]**&#x200B;을(를) 선택합니다.
1. 다음 권한을 추가합니다.

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   모바일 앱 개발자가 **Adobe Experience Platform 데이터 수집**&#x200B;에서 푸시 자격 증명을 설정하려면 이러한 권한이 필요합니다.

1. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

이 **[!UICONTROL Product profile]**&#x200B;을(를) 사용자에게 할당하려면 아래 단계를 따르십시오.

1. **[!DNL Admin Console]**&#x200B;에 액세스합니다.
1. **[!UICONTROL Products]** 탭에서 **[!UICONTROL Adobe Experience Platform Data Collection]** 카드를 선택합니다.
1. 이전에 구성한 **[!UICONTROL Product profile]**&#x200B;를 선택합니다.
1. **[!UICONTROL Users]** 탭에서 **[!UICONTROL Add user]**&#x200B;을 클릭합니다.
1. 사용자의 이름 또는 이메일 주소를 입력하고 사용자를 선택합니다. **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   >[!NOTE]
   >
   >사용자가 이전에 Admin Console에서 만들어진 것이 아니라면 [사용자 추가 설명서](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}를 참조하세요.

### 앱 구성 {#configure-app}

기술 설정에는 앱 개발자와 비즈니스 관리자 간의 긴밀한 협업이 포함됩니다. [!DNL Adobe Campaign]을(를) 사용하여 푸시 알림 전송을 시작하기 전에 [!DNL Adobe Experience Platform Data Collection]에서 설정을 정의하고 모바일 앱을 Adobe Experience Platform Mobile SDK와 통합해야 합니다.

아래 링크에 자세히 설명된 구현 단계를 따르십시오.

* **Apple iOS**&#x200B;의 경우: [Apple 설명서](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}에서 APNs에 앱을 등록하는 방법에 대해 알아보세요.
* **Google Android**&#x200B;의 경우: [Google 설명서](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}에서 Android에서 Firebase Cloud Messaging 클라이언트 앱을 설정하는 방법을 알아보세요.

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Adobe Experience Platform 데이터 수집에서 모바일 태그 속성 설정 {#launch-property}

모바일 속성을 설정하면 모바일 앱 개발자 또는 마케터가 모바일 SDK를 구성할 수 있습니다. 일반적으로 관리하려는 각 모바일 애플리케이션에 대해 모바일 속성을 만듭니다. [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}에서 모바일 속성을 만들고 구성하는 방법에 대해 알아봅니다.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

[!DNL Adobe Experience Platform Data Collection]Adobe Experience Platform 설명서[에서 ](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"} 태그에 대해 자세히 알아보세요.

만든 후에는 새 태그 속성을 열고 라이브러리를 만듭니다. 방법은 다음과 같습니다.

1. 왼쪽 탐색에서 **게시 흐름**(으)로 이동한 다음 **라이브러리 추가**&#x200B;를 선택합니다.
1. 라이브러리 이름을 입력하고 환경을 선택합니다.
1. **변경된 모든 리소스 추가** 및 **개발에 저장 및 빌드**&#x200B;를 선택합니다.
1. 마지막으로 **작업 라이브러리 선택** 단추에서 이 라이브러리를 작업 라이브러리로 설정하십시오.

## Campaign에서 모바일 서비스 구성 {#push-service}

[!DNL Adobe Experience Platform Data Collection]에서 모바일 앱을 설정한 후에는 **[!DNL Adobe Campaign]**&#x200B;에서 푸시 알림을 보낼 수 있도록 두 개의 서비스(iOS 디바이스용 서비스, Android 디바이스용 서비스)를 만들어야 합니다.

푸시 알림은 전용 서비스를 통해 앱 사용자에게 전송됩니다. 사용자가 앱을 설치할 때 이 서비스에 가입합니다. Adobe Campaign은 이 서비스를 사용하여 앱 가입자만 타깃팅합니다. 이 서비스에서는 iOS 및 Android 앱을 추가하여 iOS 및 Android 디바이스에서 전송해야 합니다.

푸시 알림을 전송하는 서비스를 만들려면 아래 단계를 수행하십시오.

1. **[!UICONTROL Profiles and Targets > Services and Subscriptions]** 탭으로 이동하여 **[!UICONTROL Create]**&#x200B;을(를) 클릭합니다.

   ![](assets/new-service-push.png){width="800" align="left"}

1. **[!UICONTROL Label]** 및 **[!UICONTROL Internal name]**&#x200B;을(를) 입력하고 **[!UICONTROL Mobile application]** 유형을 선택하십시오.

   >[!NOTE]
   >
   >기본 **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** 대상 매핑이 받는 사람 테이블에 연결되어 있습니다. 다른 대상 매핑을 사용하려면 새 대상 매핑을 만들고 서비스의 **[!UICONTROL Target mapping]** 필드에 입력해야 합니다. [이 페이지](../audiences/target-mappings.md)에서 대상 매핑에 대해 자세히 알아보세요.

1. 오른쪽의 **[!UICONTROL Add]** 아이콘을 사용하여 이 서비스를 사용하는 모바일 응용 프로그램을 정의합니다.

>[!BEGINTABS]

>[!TAB iOS]

iOS 디바이스용 앱을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Create an iOS application]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다 .

   ![](assets/new-ios-app.png){width="600" align="left"}

1. **[!UICONTROL Label]** 필드에 앱 이름을 입력합니다.
1. (선택 사항) 일부 **[!UICONTROL Application variables]**&#x200B;을(를) 사용하여 푸시 메시지 콘텐츠를 보강할 수 있습니다. 이는 완전히 맞춤화가 가능하며 모바일 디바이스로 전송되는 메시지 페이로드의 일부입니다.

   아래 예에서는 **mediaURl** 및 **mediaExt** 변수가 추가되어 리치 푸시 알림을 만든 다음 응용 프로그램에 알림 내에 표시할 이미지를 제공합니다.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. **[!UICONTROL Subscription parameters]** 탭으로 이동하여 **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** 스키마의 확장으로 매핑을 정의합니다.

1. **[!UICONTROL Sounds]** 탭으로 이동하여 재생할 소리를 정의합니다. **[!UICONTROL Add]**&#x200B;을(를) 클릭하고 응용 프로그램에 포함된 파일 이름 또는 시스템 사운드 이름을 포함해야 하는 **[!UICONTROL Internal name]** 필드를 채웁니다.

1. 개발 응용 프로그램 구성을 시작하려면 **[!UICONTROL Next]**&#x200B;을(를) 클릭하십시오.

1. 통합 키는 각 애플리케이션에 따라 다릅니다. 모바일 애플리케이션을 Adobe Campaign에 연결합니다.

   Adobe Campaign 및 SDK을 통한 응용 프로그램 코드에서 동일한 **[!UICONTROL Integration key]**&#x200B;이(가) 정의되었는지 확인하십시오.

   자세한 내용은 [개발자 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}를 참조하세요


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]**&#x200B;은(는) 문자열 값으로 완전히 사용자 지정할 수 있지만 SDK에 지정된 값과 정확히 동일해야 합니다.
   >
   > 애플리케이션의 개발 버전(샌드박스)과 프로덕션 버전에는 동일한 인증서를 사용할 수 없습니다.

1. 서비스의 모바일 애플리케이션을 개인화하려면 **[!UICONTROL Application icon]** 필드에서 아이콘을 선택하십시오.

1. **[!UICONTROL Authentication mode]**&#x200B;을(를) 선택합니다. 두 가지 모드를 사용할 수 있습니다.

   * (권장) **[!UICONTROL Token-based authentication]**: APNs 연결 설정 **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** 및 **[!UICONTROL Bundle Id]**&#x200B;을(를) 입력한 다음 **[!UICONTROL Enter the private key...]**&#x200B;을(를) 클릭하여 p8 인증서를 선택합니다. **[!UICONTROL Token-based authentication]**&#x200B;에 대한 자세한 내용은 [Apple 설명서](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}를 참조하세요.

   * **[!UICONTROL Certificate-based authentication]**: **[!UICONTROL Enter the certificate...]**&#x200B;을(를) 클릭한 다음 p12 키를 선택하고 모바일 애플리케이션 개발자가 제공한 암호를 입력하십시오. 이 인증서는 만료 날짜가 포함되어 있으며 매년 갱신해야 합니다. 사용자의 서비스가 중단되지 않도록 하려면 인증서가 만료되기 전에 인증서를 업데이트하십시오. 인증서는 1년 동안 유효하며 APNs와 계속 통신하려면 인증서를 업데이트해야 합니다.

1. **[!UICONTROL Test the connection]** 단추를 사용하여 구성의 유효성을 검사하십시오.

1. **[!UICONTROL Next]**&#x200B;을(를) 클릭하여 프로덕션 응용 프로그램 구성을 시작하고 위에 설명된 것과 동일한 단계를 수행합니다.

1. **[!UICONTROL Finish]**&#x200B;을(를) 클릭합니다.

이제 iOS 애플리케이션을 Campaign에서 사용할 준비가 되었습니다.

>[!TAB Android]

Android 디바이스용 앱을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Create an Android application]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다 .

   ![](assets/new-android-app.png){width="600" align="left"}

1. **[!UICONTROL Label]** 필드에 앱 이름을 입력합니다.
1. 통합 키는 각 애플리케이션에 따라 다릅니다. 모바일 애플리케이션을 Adobe Campaign에 연결합니다.

   Adobe Campaign 및 SDK을 통한 응용 프로그램 코드에서 동일한 **[!UICONTROL Integration key]**&#x200B;이(가) 정의되었는지 확인하십시오.

   자세한 내용은 [개발자 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}를 참조하세요


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]**&#x200B;은(는) 문자열 값으로 완전히 사용자 지정할 수 있지만 SDK에 지정된 값과 정확히 동일해야 합니다.
   >

1. 서비스의 모바일 애플리케이션을 개인화하려면 **[!UICONTROL Application icon]** 필드에서 아이콘을 선택하십시오.
1. **드롭다운 목록에서** HTTP v1 **[!UICONTROL API version]**&#x200B;을(를) 선택합니다.
1. JSON 키 파일을 로드하려면 **[!UICONTROL Load project json file to extract project details...]** 링크를 클릭하십시오. JSON 파일을 추출하는 방법에 대한 자세한 내용은 [Google Firebase 설명서](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}를 참조하세요.

   다음 세부 정보를 수동으로 입력할 수도 있습니다.
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. **[!UICONTROL Test the connection]** 단추를 사용하여 구성의 유효성을 검사하십시오.

   >[!CAUTION]
   >
   >**[!UICONTROL Test connection]** 단추는 MID(중간 소싱) 서버에서 FCM 서버에 액세스할 수 있는지 확인하지 않습니다.

1. (선택 사항) 필요한 경우 일부 **[!UICONTROL Application variables]**(으)로 푸시 메시지 콘텐츠를 보강할 수 있습니다. 이는 완전히 맞춤화가 가능하며 모바일 디바이스로 전송되는 메시지 페이로드의 일부입니다.

1. **[!UICONTROL Finish]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다. 이제 Android 애플리케이션을 Campaign에서 사용할 준비가 되었습니다.

다음은 푸시 알림을 추가로 개인화할 FCM 페이로드 이름입니다.

| 메시지 유형 | 구성 가능한 메시지 요소(FCM 페이로드 이름) | 구성 가능한 옵션(FCM 페이로드 이름) |
|:-:|:-:|:-:|
| 데이터 메시지 | N/A | validate_only |
| 알림 메시지 | 제목, 본문, android_channel_id, 아이콘, 사운드, 태그, 색상, click_action, 이미지, 티커, 고정, 가시성, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]

## 모바일 속성에서 Adobe Campaign 확장 구성 {#configure-extension}

Adobe Experience Platform Mobile SDK용 **Adobe Campaign Classic 확장**&#x200B;은(는) 모바일 앱에 대한 푸시 알림을 실행하고 사용자 푸시 토큰을 수집하고 Adobe Experience Platform 서비스와의 상호 작용 측정을 관리하는 데 도움이 됩니다.

Campaign Classic v7 및 Campaign v8 모두에 적용되는 이 확장은 환경에 사전 설치되어 있으므로 구성해야 합니다. 모바일 태그 속성에 대한 확장을 구성하려면 다음 단계를 수행합니다.

1. 이전에 만든 태그 속성을 엽니다.
1. 왼쪽 탐색에서 **확장**(으)로 이동한 다음 **카탈로그** 탭을 엽니다. 검색 필드를 사용하여 **Adobe Campaign Classic** 확장을 찾습니다.
1. Campaign Classic 카드에서 **설치** 단추를 클릭합니다.
1. [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}에 설명된 대로 설정을 입력합니다.

이제 [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}에 자세히 설명된 대로 앱에 캠페인을 추가할 수 있습니다.
