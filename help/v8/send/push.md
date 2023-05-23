---
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: e7c255d30e38c4e17779ef820e8984668ac5d48b
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# 푸시 알림 만들기 및 전송{#push-notifications-create}

모바일 앱 게재를 사용하면 iOS 및 Android 디바이스에 알림을 전송할 수 있습니다.

Adobe Campaign에서 푸시 알림을 전송하려면 다음을 수행해야 합니다.

1. SDK를 앱과 통합합니다. [자세히 알아보기](#push-sdk)
1. 모바일 애플리케이션에 대한 모바일 애플리케이션 유형 정보 서비스를 만들고 해당 서비스에 애플리케이션의 iOS 및 Android 버전을 추가합니다. [자세히 알아보기](#push-config)
1. iOS 및 Android 모두에 대한 게재를 만듭니다. [자세히 알아보기](#push-create)

## SDK 통합 {#push-sdk}

Adobe Campaign에서 푸시 알림을 전송하려면 Adobe Experience Platform Mobile SDK의 데이터 수집 UI에서 Adobe Campaign 확장 기능을 구성해야 합니다.

Adobe Experience Platform Mobile SDK는 모바일 앱에서 Adobe의 Experience Cloud 솔루션 및 서비스를 강화하는 데 도움이 됩니다. SDK 구성은 유연한 구성 및 확장 가능한 규칙 기반 통합을 위해 데이터 수집 UI를 통해 관리됩니다.

[Adobe Developer 설명서에서 자세히 알아보기](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.


## Campaign에서 앱 설정 구성{#push-config}

푸시 알림을 전송하기 전에 Adobe Campaign에서 iOS 및 Android 앱 설정을 정의해야 합니다.

푸시 알림은 전용 서비스를 통해 앱 사용자에게 전송됩니다. 사용자가 앱을 설치할 때 이 서비스에 가입합니다. Adobe Campaign은 이 서비스를 사용하여 앱 가입자만 타깃팅합니다. 이 서비스에서는 iOS 및 Android 장치에서 전송할 iOS 및 Android 앱을 추가해야 합니다.

푸시 알림을 전송할 서비스를 만들려면 아래 단계를 수행하십시오.

1. 다음으로 이동 **[!UICONTROL Profiles and Targets > Services and Subscriptions]** 탭을 클릭하고 다음을 클릭합니다. **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. 입력 **[!UICONTROL Label]** 및 **[!UICONTROL Internal name]**&#x200B;을(를) 클릭하고 **[!UICONTROL Mobile application]** 유형.

   >[!NOTE]
   >
   >기본값 **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** 대상 매핑이 수신자 테이블에 연결됩니다. 다른 대상 매핑을 사용하려면 새 대상 매핑을 생성하고 **[!UICONTROL Target mapping]** 서비스 필드. 다음에서 대상 매핑에 대해 자세히 알아보기: [이 페이지](../audiences/target-mappings.md).

1. 그런 다음 **[!UICONTROL Add]** 아이콘을 클릭하면 이 서비스를 사용하는 모바일 애플리케이션을 정의할 수 있습니다.

>[!BEGINTABS]

>[!TAB iOS]

iOS 디바이스용 앱을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Create an iOS application]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다 .

   ![](assets/new-ios-app.png){width="600" align="left"}

1. 앱의 이름을 **[!UICONTROL Label]** 필드.
1. (선택 사항) 몇 가지 방법으로 푸시 메시지 콘텐츠를 보강할 수 있습니다 **[!UICONTROL Application variables]**. 이는 완전히 맞춤화가 가능하며 모바일 디바이스로 전송되는 메시지 페이로드의 일부입니다.

   아래의 예에서는 **mediaURl** 및 **mediaExt** 변수가 추가되어 리치 푸시 알림을 만든 다음 애플리케이션에 알림 내에 표시할 이미지를 제공합니다.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. 다음으로 이동 **[!UICONTROL Subscription parameters]** 탭을 사용하여 의 확장으로 매핑을 정의합니다. **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** 스키마.

1. 다음으로 이동 **[!UICONTROL Sounds]** 재생할 사운드를 정의하는 탭입니다. 클릭 **[!UICONTROL Add]** 및 채우기 **[!UICONTROL Internal name]** 응용 프로그램에 포함된 파일의 이름이나 시스템 사운드의 이름을 포함해야 하는 필드입니다.

1. 클릭 **[!UICONTROL Next]** 개발 응용 프로그램 구성을 시작합니다.

1. 통합 키는 각 애플리케이션에 따라 다릅니다. 모바일 애플리케이션을 Adobe Campaign에 연결합니다.

   동일한 **[!UICONTROL Integration key]** 는 Adobe Campaign 및 SDK를 통한 애플리케이션 코드에 정의되어 있습니다.

   다음에서 자세히 알아보기 [개발자 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 다음 **[!UICONTROL Integration key]** 는 문자열 값으로 완전히 사용자 지정할 수 있지만 SDK에 지정된 것과 정확히 동일해야 합니다.
   >
   > 애플리케이션의 개발 버전(샌드박스)과 프로덕션 버전에는 동일한 인증서를 사용할 수 없습니다.

1. 다음에서 아이콘을 선택합니다. **[!UICONTROL Application icon]** 서비스에서 모바일 애플리케이션을 개인화하는 필드입니다.

1. **[!UICONTROL Authentication mode]**&#x200B;을(를) 선택합니다. 두 가지 모드를 사용할 수 있습니다.

   * (권장) **[!UICONTROL Token-based authentication]**: APNs 연결 설정을 입력합니다 **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** 및 **[!UICONTROL Bundle Id]** 그런 다음 를 클릭하여 p8 인증서를 선택합니다. **[!UICONTROL Enter the private key...]**. 에 대한 자세한 내용 **[!UICONTROL Token-based authentication]**, 참조 [Apple 설명서](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: 클릭 **[!UICONTROL Enter the certificate...]**  그런 다음 p12 키를 선택하고 모바일 애플리케이션 개발자가 제공한 암호를 입력합니다.
   인증 모드는 나중에 **[!UICONTROL Certificate]** 모바일 애플리케이션의 탭입니다.

1. 사용 **[!UICONTROL Test the connection]** 단추를 클릭하여 구성을 확인합니다.

1. 클릭 **[!UICONTROL Next]** 프로덕션 애플리케이션 구성을 시작하고 위에 설명된 것과 동일한 단계를 수행합니다.

1. **[!UICONTROL Finish]**&#x200B;를 클릭합니다.

이제 iOS 애플리케이션을 Campaign에서 사용할 준비가 되었습니다.

>[!TAB Android]

Android 디바이스용 앱을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Create an Android application]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다 .

   ![](assets/new-android-app.png){width="600" align="left"}

1. 앱의 이름을 **[!UICONTROL Label]** 필드.
1. 통합 키는 각 애플리케이션에 따라 다릅니다. 모바일 애플리케이션을 Adobe Campaign에 연결합니다.

   동일한 **[!UICONTROL Integration key]** 는 Adobe Campaign 및 SDK를 통한 애플리케이션 코드에 정의되어 있습니다.

   다음에서 자세히 알아보기 [개발자 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 다음 **[!UICONTROL Integration key]** 는 문자열 값으로 완전히 사용자 지정할 수 있지만 SDK에 지정된 것과 정확히 동일해야 합니다.

1. 다음에서 아이콘을 선택합니다. **[!UICONTROL Application icon]** 서비스에서 모바일 애플리케이션을 개인화하는 필드입니다.
1. 선택 **HTTP v1** 위치:  **[!UICONTROL API version]** 드롭다운 목록입니다.
1. 클릭 **[!UICONTROL Load project json file to extract project details...]** json 키 파일을 로드하는 링크. JSON 파일을 추출하는 방법에 대한 자세한 내용은 다음을 참조하십시오. [Google Firebase 설명서](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   다음 세부 정보를 수동으로 입력할 수도 있습니다.
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. 사용 **[!UICONTROL Test the connection]** 단추를 클릭하여 구성을 확인합니다.

   >[!CAUTION]
   >
   >다음 **[!UICONTROL Test connection]** MID 서버가 FCM 서버에 액세스할 수 있는지 여부를 확인하지 않습니다.

1. (선택 사항) 몇 가지 방법으로 푸시 메시지 콘텐츠를 보강할 수 있습니다 **[!UICONTROL Application variables]** 필요한 경우. 이는 완전히 맞춤화가 가능하며 모바일 디바이스로 전송되는 메시지 페이로드의 일부입니다.

1. **[!UICONTROL Finish]**&#x200B;을(를) 클릭한 뒤 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다. 이제 Android 애플리케이션을 Campaign에서 사용할 준비가 되었습니다.

다음은 푸시 알림을 추가로 개인화할 FCM 페이로드 이름입니다.

| 메시지 유형 | 구성 가능한 메시지 요소(FCM 페이로드 이름) | 구성 가능한 옵션(FCM 페이로드 이름) |
|:-:|:-:|:-:|
| 데이터 메시지 | N/A | validate_only |
| 알림 메시지 | 제목, 본문, android_channel_id, 아이콘, 사운드, 태그, 색상, click_action, 이미지, 티커, 고정, 가시성, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## 첫 번째 푸시 알림 만들기{#push-create}

이 섹션에서는 iOS 및 Android 알림 전달과 관련된 요소에 대해 자세히 설명합니다.

>[!CAUTION]
>
>의 맥락에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 이제 모바일 등록은 **비동기**. [자세히 알아보기](../architecture/staging.md)

새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭을 클릭하고 **[!UICONTROL Deliveries]** 을(를) 클릭하고 **[!UICONTROL Create]** 기존 게재 목록 위에 있는 단추입니다.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

iOS 디바이스에서 알림을 보내려면 다음 단계를 따르십시오.

1. 다음 항목 선택 **[!UICONTROL Deliver on iOS]** 게재 템플릿.

   ![](assets/push_ios_1.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. 선택 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**&#x200B;에서 모바일 애플리케이션과 관련된 서비스를 선택한 다음, 애플리케이션의 iOS 버전을 선택합니다.

   ![](assets/push_ios_3.png)

1. 다음 항목 선택 **[!UICONTROL Notification type]** 사이 **[!UICONTROL General notification (Alert, Sound, Badge)]** 또는 **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >다음 **자동 푸시** 모드에서는 &quot;자동&quot; 알림을 모바일 애플리케이션으로 전송할 수 있습니다. 사용자는 알림이 도착한 것을 알 수 없습니다. 애플리케이션에 바로 전송됩니다.

1. 다음에서 **[!UICONTROL Title]** 필드에 알림 센터에서 사용할 수 있는 알림 목록에 표시할 제목의 레이블을 입력합니다.

   이 필드에서는 의 값을 정의할 수 있습니다. **제목** iOS 알림 페이로드의 매개 변수.

1. 다음을 추가할 수 있습니다. **[!UICONTROL Subtitle]**, 값 **부제** iOS 알림 페이로드의 매개 변수.

1. 에 메시지 내용 입력 **[!UICONTROL Message content]** 섹션에 있는 마지막 항목이 될 필요가 없습니다.

1. 다음에서 **[!UICONTROL Sound and Badge]** 탭에서 다음 옵션을 편집할 수 있습니다.

   * **[!UICONTROL Clean Badge]**: 배지 값을 새로 고치려면 이 옵션을 활성화합니다.

   * **[!UICONTROL Value]**: 애플리케이션 아이콘에 읽지 않은 새로운 정보의 수를 직접 표시하는 데 사용할 숫자를 설정합니다.

   * **[!UICONTROL Critical alert mode]**: 사용자의 휴대폰이 포커스 모드로 설정되어 있거나 iPhone이 음소거된 경우에도 알림에 사운드를 추가하려면 이 옵션을 활성화합니다.

   * **[!UICONTROL Name]**: 알림을 수신할 때 모바일 디바이스에서 재생할 사운드를 선택합니다.

   * **[!UICONTROL Volume]**: 0에서 100 사이의 사운드 볼륨입니다.

      >[!NOTE]
      > 
      >사운드는 애플리케이션에 포함되어야 하며 서비스를 만들 때 정의되어야 합니다.
   ![](assets/push_ios_5.png)

1. 다음에서 **[!UICONTROL Application variables]** 탭, **[!UICONTROL Application variables]** 자동으로 추가됩니다. 알림 동작을 정의할 수 있습니다. 예를 들어, 사용자가 알림을 활성화할 때 특정 애플리케이션 화면이 표시되도록 구성할 수 있습니다.

1. 다음에서 **[!UICONTROL Advanced]** 탭에서 다음 일반 옵션을 편집할 수 있습니다.

   * **[!UICONTROL Mutable content]**: 모바일 애플리케이션에서 미디어 콘텐츠를 다운로드하도록 하려면 이 옵션을 활성화합니다.

   * **[!UICONTROL Thread-id]**: 관련 알림을 함께 그룹화하는 데 사용되는 식별자.

   * **[!UICONTROL Category]**: 작업 버튼을 표시할 범주 ID의 이름입니다. 이러한 알림은 사용자가 애플리케이션을 열거나 탐색하지 않고도 알림에 응답하여 다른 작업을 보다 빠르게 수행할 수 있도록 합니다.

   ![](assets/push_ios_6.png)

1. 시간 구분 알림의 경우 다음 옵션을 지정할 수 있습니다.

   * **[!UICONTROL Target content ID]**: 알림을 열 때 앞으로 가져올 애플리케이션 창을 타겟팅하는 데 사용되는 식별자입니다.

   * **[!UICONTROL Launch image]**: 표시할 론치 이미지 파일의 이름입니다. 사용자가 응용 프로그램을 시작하도록 선택하면 응용 프로그램의 시작 화면 대신 선택한 이미지가 표시됩니다.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: 기본적으로 설정되어 있으므로 시스템에서 알림을 즉시 표시하고 화면을 켜며 사운드를 재생할 수 있습니다. 알림은 포커스 모드를 통과하지 않습니다.

      * **[!UICONTROL Passive]**: 화면에 불이 들어오거나 소리가 재생되지 않고 알림 목록에 알림이 추가됩니다. 알림은 포커스 모드를 통과하지 않습니다.

      * **[!UICONTROL Time sensitive]** 이 시스템은 알림을 즉시 표시하고 화면을 켜며 사운드를 재생하고 포커스 모드를 돌파할 수 있습니다. 이 수준에서는 Apple의 특별한 권한이 필요하지 않습니다.

      * **[!UICONTROL Critical]** 이 시스템은 알림을 즉시 표시하고 화면을 켜며 음소거 스위치나 포커스 모드를 우회합니다. 이 수준에는 Apple의 특별한 권한이 필요합니다.
   * **[!UICONTROL Relevance score]**: 관련성 점수를 0에서 100으로 설정합니다. 시스템은 이 옵션을 사용하여 알림 요약의 알림을 정렬합니다.

   ![](assets/push_ios_7.png)

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Android 장치에서 알림을 보내려면 다음 단계를 따르십시오.

1. 다음 항목 선택 **[!UICONTROL Deliver on Android (android)]** 게재 템플릿.

   ![](assets/push-template-android.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 선택 **[!UICONTROL Subscribers of an Android mobile application]**&#x200B;에서 모바일 애플리케이션과 관련된 서비스(이 경우 Neotrips)를 선택한 다음, 애플리케이션의 Android 버전을 선택합니다.

   ![](assets/push-android-subscribers.png)

1. 그런 다음 알림 콘텐츠를 입력합니다.

   ![](assets/push-android-content.png)

1. 다음을 클릭합니다. **[!UICONTROL Insert emoticon]** 아이콘: 푸시 알림에 이모티콘을 삽입합니다.

1. 다음에서 **[!UICONTROL Application variables]** 필드에 각 변수의 값을 입력합니다. 예를 들어, 사용자가 알림을 활성화할 때 특정 애플리케이션 화면이 표시되도록 구성할 수 있습니다.

1. 알림이 구성되면 **[!UICONTROL Preview]** 탭을 클릭하여 알림을 미리 봅니다.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## 푸시 알림 테스트, 전송 및 모니터링

증명을 보내고 최종 게재를 보내려면 다른 게재와 동일한 프로세스를 사용합니다.

에서 게재의 유효성을 검사하는 방법 알아보기 [이 페이지](preview-and-proof.md).

에서 게재를 확인하고 보내는 방법 알아보기 [이 페이지](send.md)

메시지를 보낸 후 게재를 모니터링하고 추적할 수 있습니다. 에서 푸시 알림 게재 실패 이유에 대해 자세히 알아보기 [이 페이지](delivery-failures.md#push-error-types).

