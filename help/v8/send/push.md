---
title: Adobe Campaign을 사용하여 푸시 알림 보내기
description: Campaign에서 푸시 알림 시작
feature: Push
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 7%

---

# 푸시 알림 구성 및 전송{#push-notifications-create}

모바일 앱 게재를 사용하면 iOS 및 Android 디바이스에 알림을 전송할 수 있습니다.

Adobe Campaign을 사용하여 푸시 알림 전송을 시작하기 전에 모바일 앱과 Adobe Experience Platform의 태그에 대한 구성 및 통합이 제대로 되어 있는지 확인해야 합니다. [푸시 구성에 대해 자세히 알아보세요.](push-settings.md).

>[!CAUTION]
>
>Android FCM(Firebase Cloud Messaging) 서비스에 대한 몇 가지 중요한 변경 사항이 2024년에 출시될 예정이며, 이는 Adobe Campaign 구현에 영향을 줄 수 있습니다. 이 변경 사항을 지원하려면 Android 푸시 메시지에 대한 구독 서비스 구성을 업데이트해야 할 수 있습니다. 미리 확인하고 조치를 취할 수 있습니다.

## 첫 번째 푸시 알림 만들기 {#push-create}

이 섹션에서는 iOS 및 Android 알림 전달과 관련된 요소에 대해 자세히 설명합니다.

>[!IMPORTANT]
>
>[엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md)의 컨텍스트에서 모바일 등록은 이제 **비동기**&#x200B;입니다. [자세히 알아보기](../architecture/staging.md)


새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭으로 이동하여 **[!UICONTROL Deliveries]**&#x200B;을(를) 클릭하고 기존 게재 목록 위에 있는 **[!UICONTROL Create]** 단추를 클릭합니다.

![](assets/delivery_step_1.png)


기본적으로 Adobe Campaign에는 두 개의 게재 템플릿이 제공됩니다(iOS용 템플릿, Android용 템플릿). 이를 복제하여 자신만의 설정을 정의할 수 있습니다. 이러한 템플릿을 기반으로 푸시 게재를 구성하는 단계는 아래에 자세히 설명되어 있습니다.

>[!BEGINTABS]

>[!TAB iOS]

iOS 디바이스에서 알림을 보내려면 다음 단계를 따르십시오.

1. **[!UICONTROL Deliver on iOS]** 게재 템플릿을 선택하십시오.

   ![](assets/push_ios_1.png)

1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.

   ![](assets/push_ios_2.png)

1. **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**&#x200B;을(를) 선택하고 모바일 응용 프로그램과 관련된 서비스를 선택한 다음 응용 프로그램의 iOS 버전을 선택합니다.

   ![](assets/push_ios_3.png)

1. **[!UICONTROL Notification type]**&#x200B;과(와) **[!UICONTROL General notification (Alert, Sound, Badge)]** 중 **[!UICONTROL Silent notification]**&#x200B;을(를) 선택하세요.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >**자동 푸시** 모드를 사용하면 &quot;자동&quot; 알림을 모바일 애플리케이션으로 보낼 수 있습니다. 사용자는 알림이 도착했음을 알지 못합니다. 애플리케이션으로 직접 전송됩니다.

1. 알림 센터에서 사용할 수 있는 알림 목록에 표시할 제목의 레이블을 **[!UICONTROL Title]** 필드에 입력합니다.

   이 필드에서는 iOS 알림 페이로드의 **title** 매개 변수의 값을 정의할 수 있습니다.

1. iOS 알림 페이로드의 **[!UICONTROL Subtitle]**&#x200B;자막&#x200B;**매개 변수의** 값을 추가할 수 있습니다.

1. 마법사의 **[!UICONTROL Message content]** 섹션에 메시지 내용을 입력합니다.

1. **[!UICONTROL Sound and Badge]** 탭에서 다음 옵션을 편집할 수 있습니다.

   * **[!UICONTROL Clean Badge]**: 배지 값을 새로 고치려면 이 옵션을 활성화하십시오.

   * **[!UICONTROL Value]**: 읽지 않은 새 정보의 수를 응용 프로그램 아이콘에 직접 표시하는 데 사용할 숫자를 설정하십시오.

   * **[!UICONTROL Critical alert mode]**: 사용자의 휴대폰이 포커스 모드로 설정되어 있거나 iPhone이 음소거되어 있는 경우에도 알림에 사운드를 추가하려면 이 옵션을 사용합니다.

   * **[!UICONTROL Name]**: 알림을 받을 때 모바일 터미널에서 재생할 소리를 선택하십시오.

   * **[!UICONTROL Volume]**: 사운드의 음량이 0에서 100까지입니다.

     >[!NOTE]
     > 
     >사운드는 애플리케이션에 포함되어야 하며 서비스를 만들 때 정의되어야 합니다.
     >

   ![](assets/push_ios_5.png)

1. **[!UICONTROL Application variables]** 탭에서 **[!UICONTROL Application variables]**&#x200B;이(가) 자동으로 추가됩니다. 알림 동작을 정의할 수 있습니다. 예를 들어, 사용자가 알림을 활성화할 때 특정 애플리케이션 화면이 표시되도록 구성할 수 있습니다.

1. **[!UICONTROL Advanced]** 탭에서 다음 일반 옵션을 편집할 수 있습니다.

   * **[!UICONTROL Mutable content]**: 모바일 애플리케이션에서 미디어 콘텐츠를 다운로드하도록 하려면 이 옵션을 활성화하십시오.

   * **[!UICONTROL Thread-id]**: 관련 알림을 함께 그룹화하는 데 사용되는 식별자입니다.

   * **[!UICONTROL Category]**: 작업 단추를 표시할 범주 ID의 이름입니다. 이러한 알림은 사용자가 애플리케이션을 열거나 탐색하지 않고도 알림에 응답하여 다른 작업을 보다 빠르게 수행할 수 있도록 합니다.

   ![](assets/push_ios_6.png)

1. 시간 구분 알림의 경우 다음 옵션을 지정할 수 있습니다.

   * **[!UICONTROL Target content ID]**: 알림을 열 때 앞으로 가져올 응용 프로그램 창을 대상으로 하는 데 사용되는 식별자입니다.

   * **[!UICONTROL Launch image]**: 표시할 시작 이미지 파일의 이름입니다. 사용자가 응용 프로그램을 시작하도록 선택하면 응용 프로그램의 시작 화면 대신 선택한 이미지가 표시됩니다.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: 기본적으로 설정되어 있으면 시스템에서 알림을 즉시 표시하고 화면을 켜며 소리를 재생할 수 있습니다. 알림은 포커스 모드를 통과하지 않습니다.

      * **[!UICONTROL Passive]**: 시스템에서 화면에 불을 켜거나 소리를 재생하지 않고 알림 목록에 알림을 추가합니다. 알림은 포커스 모드를 통과하지 않습니다.

      * **[!UICONTROL Time sensitive]** 시스템에서 알림을 즉시 표시하고 화면을 켜며 소리를 재생하고 포커스 모드를 돌파할 수 있습니다. 이 수준에서는 Apple의 특별한 권한이 필요하지 않습니다.

      * **[!UICONTROL Critical]** 시스템에서 알림을 즉시 표시하고 화면을 켜며 음소거 스위치나 포커스 모드를 사용하지 않습니다. 이 수준에는 Apple의 특별한 권한이 필요합니다.

   * **[!UICONTROL Relevance score]**: 관련성 점수를 0에서 100으로 설정합니다. 시스템은 이 옵션을 사용하여 알림 요약의 알림을 정렬합니다.

   ![](assets/push_ios_7.png)

1. 알림이 구성되면 알림을 미리 보려면 **[!UICONTROL Preview]** 탭을 클릭하십시오.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Android 디바이스에서 알림을 보내려면 다음 단계를 따르십시오.

1. **[!UICONTROL Deliver on Android (android)]** 게재 템플릿을 선택하십시오.

   ![](assets/push-template-android.png)

   >[!NOTE]
   > 
   >최신 FCM API(HTTP v1)를 사용하면 Android 푸시 알림용 **게재 템플릿**&#x200B;을 업데이트하여 일괄 처리 메시지 수를 늘려야 합니다. 이렇게 하려면 Android 게재 템플릿의 속성을 찾은 다음 **게재** 탭에서 [메시지 일괄 처리 수량](../../v8/send/configure-and-send.md#delivery-batch-quantity)을 **256**(으)로 설정합니다. 이 변경 사항을 Android 게재에 사용되는 모든 게재 템플릿과 기존의 모든 Android 게재에 적용합니다.


1. 알림 대상을 정의하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.

   ![](assets/push-android-select-target.png)

1. **[!UICONTROL Subscribers of an Android mobile application]**&#x200B;을(를) 선택하고 모바일 응용 프로그램과 관련된 서비스(이 경우 Neotrips)를 선택한 다음 응용 프로그램의 Android 버전을 선택합니다.

   ![](assets/push-android-subscribers.png)

1. 그런 다음 알림 콘텐츠를 입력합니다.

   ![](assets/push-android-content.png)

1. 푸시 알림에 이모티콘을 삽입하려면 **[!UICONTROL Insert emoticon]** 아이콘을 클릭하세요.

1. **[!UICONTROL Application variables]** 필드에 각 변수의 값을 입력합니다. 예를 들어, 사용자가 알림을 활성화할 때 특정 애플리케이션 화면이 표시되도록 구성할 수 있습니다.

1. 알림이 구성되면 알림을 미리 보려면 **[!UICONTROL Preview]** 탭을 클릭하십시오.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## 푸시 알림 테스트, 전송 및 모니터링 {#push-test}

증명을 보내고 최종 게재를 보내려면 다른 게재와 동일한 프로세스를 사용합니다.

[이 페이지](preview-and-proof.md)에서 게재의 유효성을 검사하는 방법을 알아보세요.

[이 페이지](send.md)에서 게재를 확인하고 보내는 방법을 알아보세요.

메시지를 보낸 후 게재를 모니터링하고 추적할 수 있습니다. [이 페이지](delivery-failures.md#push-error-types)에서 푸시 알림 게재 실패 이유에 대해 자세히 알아보세요.

