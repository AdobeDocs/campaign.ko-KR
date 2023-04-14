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

모바일 앱 게재를 사용하면 iOS 및 Android 장치에 알림을 보낼 수 있습니다.

Adobe Campaign에서 푸시 알림을 전송하려면 다음을 수행해야 합니다.

1. SDK를 앱과 통합합니다. [자세히 알아보기](#push-sdk)
1. 모바일 애플리케이션에 대한 모바일 애플리케이션 유형 정보 서비스를 만들고 해당 서비스에 애플리케이션의 iOS 및 Android 버전을 추가합니다. [자세히 알아보기](#push-config)
1. iOS 및 Android 모두에 대한 게재를 만듭니다. [자세히 알아보기](#push-create)

## SDK 통합 {#push-sdk}

Adobe Campaign으로 푸시 알림을 전송하려면 Adobe Experience Platform Mobile SDK의 데이터 수집 UI에서 Adobe Campaign 확장을 구성해야 합니다.

Adobe Experience Platform Mobile SDK는 모바일 앱에서 Adobe의 Experience Cloud 솔루션 및 서비스를 제공하는 데 도움이 됩니다. SDK 구성은 유연한 구성 및 확장 가능한 규칙 기반 통합을 위해 데이터 수집 UI를 통해 관리됩니다.

[Adobe Developer 설명서에서 자세히 알아보기](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.


## Campaign에서 앱 설정 구성{#push-config}

푸시 알림을 전송하기 전에 Adobe Campaign에서 iOS 및 Android 앱 설정을 정의해야 합니다.

푸시 알림은 전용 서비스를 통해 앱 사용자에게 전송됩니다. 사용자가 앱을 설치하면 이 서비스에 가입합니다. Adobe Campaign은 이 서비스를 사용하여 앱의 구독자만 타겟팅합니다. 이 서비스에서는 iOS 및 Android 장치에서 전송하기 위해 iOS 및 Android 앱을 추가해야 합니다.

푸시 알림을 전송하는 서비스를 만들려면 아래 단계를 수행하십시오.

1. 찾아보기 **[!UICONTROL Profiles and Targets > Services and Subscriptions]** 탭을 클릭한 다음 **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. 을(를) 입력합니다. **[!UICONTROL Label]** 그리고 **[!UICONTROL Internal name]**, 을(를) 선택하고 을(를) 선택합니다. **[!UICONTROL Mobile application]** 유형.

   >[!NOTE]
   >
   >기본값 **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** 대상 매핑은 수신자 테이블에 연결됩니다. 다른 대상 매핑을 사용하려면 새 대상 매핑을 생성하고 여기에 입력해야 합니다 **[!UICONTROL Target mapping]** 서비스의 필드입니다. 에서 타겟 매핑에 대해 자세히 알아보십시오 [이 페이지](../audiences/target-mappings.md).

1. 그런 다음 **[!UICONTROL Add]** 아이콘을 클릭합니다.

>[!BEGINTABS]

>[!TAB iOS]

iOS 장치용 앱을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Create an iOS application]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다 .

   ![](assets/new-ios-app.png){width="600" align="left"}

1. 에 앱 이름을 입력합니다 **[!UICONTROL Label]** 필드.
1. (선택 사항) 일부 항목을 사용하여 푸시 메시지 콘텐츠를 보강할 수 있습니다 **[!UICONTROL Application variables]**. 사용자 지정할 수 있으며 모바일 장치로 전송되는 메시지 페이로드의 일부입니다.

   아래 예제에서 **mediaURL** 및 **mediaExt** 리치 푸시 알림을 만들기 위해 변수가 추가되고 알림 내에 표시할 이미지를 애플리케이션에 제공합니다.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. 다음 위치로 이동합니다. **[!UICONTROL Subscription parameters]** 탭을 사용하여 확장 기능을 사용하는 매핑을 정의할 수 있습니다 **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** 스키마.

1. 다음 위치로 이동합니다. **[!UICONTROL Sounds]** 탭하여 재생할 사운드를 정의합니다. 클릭 **[!UICONTROL Add]** 및 채우기 **[!UICONTROL Internal name]** 응용 프로그램에 포함된 파일의 이름 또는 시스템 사운드의 이름을 포함해야 하는 필드입니다.

1. 클릭 **[!UICONTROL Next]** 개발 애플리케이션 구성을 시작하려면 다음을 수행하십시오.

1. 통합 키는 각 애플리케이션에만 적용됩니다. 모바일 애플리케이션을 Adobe Campaign에 연결합니다.

   동일한 **[!UICONTROL Integration key]** 는 Adobe Campaign에 정의되며, SDK를 통해 애플리케이션 코드에 정의됩니다.

   추가 정보 [개발자 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 다음 **[!UICONTROL Integration key]** 는 문자열 값으로 완전히 사용자 지정할 수 있지만 SDK에 지정된 값과 동일해야 합니다.
   >
   > 개발 버전(샌드박스) 및 응용 프로그램의 프로덕션 버전에 동일한 인증서를 사용할 수 없습니다.

1. 에서 아이콘을 선택합니다 **[!UICONTROL Application icon]** 필드에서 모바일 애플리케이션을 개인화할 수 있습니다.

1. **[!UICONTROL Authentication mode]**&#x200B;을(를) 선택합니다. 다음 두 가지 모드를 사용할 수 있습니다.

   * (권장) **[!UICONTROL Token-based authentication]**: APNs 연결 설정 입력 **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** 및 **[!UICONTROL Bundle Id]** 그런 다음 를 클릭하여 p8 인증서를 선택합니다. **[!UICONTROL Enter the private key...]**. 자세한 내용 **[!UICONTROL Token-based authentication]**&#x200B;를 참조하려면 [Apple 설명서](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: 클릭 **[!UICONTROL Enter the certificate...]**  그런 다음 p12 키를 선택하고 모바일 애플리케이션 개발자가 제공한 암호를 입력합니다.
   인증 모드를 나중에 **[!UICONTROL Certificate]** 모바일 애플리케이션의 탭입니다.

1. 를 사용하십시오 **[!UICONTROL Test the connection]** 단추를 클릭하여 구성을 확인합니다.

1. 클릭 **[!UICONTROL Next]** 프로덕션 애플리케이션 구성을 시작하고 위의 설명과 동일한 단계를 수행하십시오.

1. **[!UICONTROL Finish]**&#x200B;를 클릭합니다.

이제 iOS 애플리케이션을 Campaign에서 사용할 준비가 되었습니다.

>[!TAB Android]

Android 장치용 앱을 만들려면 다음 단계를 수행하십시오.

1. **[!UICONTROL Create an Android application]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다 .

   ![](assets/new-android-app.png){width="600" align="left"}

1. 에 앱 이름을 입력합니다 **[!UICONTROL Label]** 필드.
1. 통합 키는 각 애플리케이션에만 적용됩니다. 모바일 애플리케이션을 Adobe Campaign에 연결합니다.

   동일한 **[!UICONTROL Integration key]** 는 Adobe Campaign에 정의되며, SDK를 통해 애플리케이션 코드에 정의됩니다.

   추가 정보 [개발자 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 다음 **[!UICONTROL Integration key]** 는 문자열 값으로 완전히 사용자 지정할 수 있지만 SDK에 지정된 값과 동일해야 합니다.

1. 에서 아이콘을 선택합니다 **[!UICONTROL Application icon]** 필드에서 모바일 애플리케이션을 개인화할 수 있습니다.
1. 선택 **HTTP v1** in  **[!UICONTROL API version]** 드롭다운 목록.
1. 클릭 **[!UICONTROL Load project json file to extract project details...]** 링크를 클릭하여 JSON 키 파일을 로드합니다. JSON 파일을 추출하는 방법에 대한 자세한 내용은 [Google Firebase 설명서](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   다음 세부 정보를 수동으로 입력할 수도 있습니다.
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. 를 사용하십시오 **[!UICONTROL Test the connection]** 단추를 클릭하여 구성을 확인합니다.

   >[!CAUTION]
   >
   >다음 **[!UICONTROL Test connection]** 버튼은 MID 서버가 FCM 서버에 액세스할 수 있는지 확인하지 않습니다.

1. (선택 사항) 일부 항목을 사용하여 푸시 메시지 콘텐츠를 보강할 수 있습니다 **[!UICONTROL Application variables]** 필요한 경우 사용자 지정할 수 있으며 모바일 장치로 전송되는 메시지 페이로드의 일부입니다.

1. **[!UICONTROL Finish]**&#x200B;을(를) 클릭한 뒤 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다. 이제 Android 애플리케이션을 Campaign에서 사용할 준비가 되었습니다.

푸시 알림을 추가로 개인화하기 위한 FCM 페이로드 이름은 다음과 같습니다.

| 메시지 유형 | 구성 가능한 메시지 요소(FCM 페이로드 이름) | 구성 가능한 옵션(FCM 페이로드 이름) |
|:-:|:-:|:-:|
| 데이터 메시지 | N/A | valid_only |
| 알림 메시지 | 제목, body, android_channel_id, 아이콘, 사운드, 태그, 색상, click_action, 이미지, 티커, 가시성, notification_priority, notification_count <br> | valid_only |


>[!ENDTABS]


## 첫 번째 푸시 알림 만들기{#push-create}

이 섹션에서는 iOS 및 Android 알림 게재와 관련된 요소에 대해 자세히 설명합니다.

>[!CAUTION]
>
>의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 이제 모바일 등록 **비동기**. [자세히 알아보기](../architecture/staging.md)

새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭, **[!UICONTROL Deliveries]** 을 클릭하고 **[!UICONTROL Create]** 기존 게재 목록 위의 단추.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

iOS 장치에서 알림을 전송하려면 다음 단계를 수행합니다.

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
   ![](assets/push_ios_5.png)

1. 에서 **[!UICONTROL Application variables]** 탭, **[!UICONTROL Application variables]** 이 자동으로 추가됩니다. 알림 동작을 정의할 수 있도록 해줍니다. 예를 들어, 사용자가 알림을 활성화하면 표시되는 특정 애플리케이션 화면을 구성할 수 있습니다.

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


>[!TAB Android]

Android 장치에서 알림을 전송하려면 다음 단계를 수행합니다.

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

>[!ENDTABS]


## 푸시 알림 테스트, 전송 및 모니터링

증명을 보내고 최종 게재를 보내려면 다른 게재와 동일한 프로세스를 사용하십시오.

에서 게재의 유효성을 검사하는 방법을 알아봅니다 [이 페이지](preview-and-proof.md).

게재를 확인하고 보내는 방법을 알아봅니다 [이 페이지](send.md)

메시지를 보낸 후 게재를 모니터링하고 추적할 수 있습니다. 푸시 알림 게재 실패 이유에 대해 자세히 알아보기 [이 페이지](delivery-failures.md#push-error-types).

