---
title: AEP SDK 및 Campaign 통합
description: Adobe Experience Platform Mobile SDK를 앱과 통합하는 방법을 알아봅니다
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e3ea361cc486096fe6c19ac469e8a71b636371ac
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---


# AEP SDK + 캠페인: 푸시 알림 채널 구성 {#push-notification-configuration}

Adobe Campaign으로 푸시 알림을 전송하기 전에 모바일 앱 및 Adobe Experience Platform의 태그에 구성 및 통합이 제대로 수행되었는지 확인해야 합니다... .... ....


## 시작하기 전 {#before-starting}

### 권한 설정 {#setup-permissions}

모바일 애플리케이션을 만들기 전에 먼저 Adobe Experience Platform에서 태그에 대한 올바른 사용자 권한이 있는지 또는 지정했는지 확인해야 합니다. Adobe Experience Platform의 태그에 대한 사용자 권한은 Adobe Admin Console을 통해 사용자에게 할당됩니다. 추가 정보 [태그 설명서](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>푸시 구성은 전문가 사용자가 수행해야 합니다. 구현 모델 및 이 구현에 관련된 개인에 따라 전체 권한 세트를 단일 제품 프로필에 할당하거나 앱 개발자와 앱 개발자 간에 권한을 공유해야 할 수 있습니다 **Adobe Campaign** 관리자

할당하려면 **속성** 및 **회사** 권한을 갖고 아래 절차를 따르십시오.

1. 액세스 권한 **[!DNL Admin Console]**.
1. 에서 **[!UICONTROL Products]** 탭에서 을 선택합니다 **[!UICONTROL Adobe Experience Platform Data Collection]** 카드.
1. 기존 항목 선택 **[!UICONTROL Product Profile]** 또는 **[!UICONTROL New profile]** 버튼을 클릭합니다. 새로 만드는 방법 알아보기 **[!UICONTROL New profile]** 에서 [Admin Console 설명서](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. **[!UICONTROL Permissions]** 탭에서, **[!UICONTROL Property Rights]**&#x200B;를 선택합니다.
1. **[!UICONTROL Add all]**&#x200B;을(를) 클릭합니다. 이렇게 하면 제품 프로필에 다음 권한이 추가됩니다.
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Adobe Campaign 확장을 설치 및 게시하고 앱 속성을 게시하려면 다음 권한이 필요합니다. **Adobe Experience Platform Mobile SDK**.

1. 그런 다음 **[!UICONTROL Company rights]** 왼쪽 메뉴에 있습니다.
1. 다음 권한을 추가합니다.

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   이러한 권한은 모바일 앱 개발자가 푸시 자격 증명을 설정하려면에서 설정하는 데 필요합니다 **Adobe Experience Platform 데이터 수집**.

1. **[!UICONTROL Save]**&#x200B;를 클릭합니다.

이를 할당하려면 **[!UICONTROL Product profile]** 사용자에게 알려면 아래 단계를 수행하십시오.

1. 액세스 권한 **[!DNL Admin Console]**.
1. 에서 **[!UICONTROL Products]** 탭에서 을 선택합니다 **[!UICONTROL Adobe Experience Platform Data Collection]** 카드.
1. 이전에 구성한 **[!UICONTROL Product profile]**&#x200B;를 선택합니다.
1. **[!UICONTROL Users]** 탭에서 **[!UICONTROL Add user]**&#x200B;을 클릭합니다.
1. 사용자 이름이나 이메일 주소를 입력하고 사용자를 선택합니다. 그런 다음 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >이전에 Admin Console에서 사용자를 만들지 않은 경우 [사용자 추가 설명서](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### 앱 구성 {#configure-app}

기술 설정에는 앱 개발자와 비즈니스 관리자 간의 긴밀한 공동 작업이 포함됩니다. 푸시 알림 전송을 시작하기 전에 [!DNL Adobe Campaign]를 지정하는 경우에서 설정을 정의해야 합니다 [!DNL Adobe Experience Platform Data Collection] Adobe Experience Platform Mobile SDK와 모바일 앱을 통합합니다.

아래 링크에 자세히 설명된 구현 단계를 따르십시오.

* 대상 **Apple iOS**: 의 APNs에 앱을 등록하는 방법을 알아봅니다. [Apple 설명서](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* 대상 **Google Android**: Android에서 Firebase Cloud Messaging 클라이언트 앱을 설정하는 방법을 알아봅니다. [Google 설명서](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

### 모바일 앱을 Adobe Experience Platform SDK와 통합합니다 {#integrate-mobile-app}

Adobe Experience Platform Mobile SDK는 Android 및 iOS 호환 SDK를 통해 모바일용 클라이언트측 통합 API를 제공합니다. 팔로우 [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} 앱에서 Adobe Experience Platform Mobile SDK를 사용하여 설정하려면 다음을 수행하십시오.

이 작업을 완료하여에 모바일 속성도 만들고 구성해야 했습니다 [!DNL Adobe Experience Platform Data Collection]. 일반적으로 관리할 각 모바일 애플리케이션에 대해 모바일 속성을 만듭니다. 에서 모바일 속성을 만들고 구성하는 방법을 알아봅니다 [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.


## 1단계: Adobe Experience Platform 데이터 수집에 앱 푸시 자격 증명 추가 {#push-credentials}

올바른 사용자 권한을 부여했으면 이제 Adobe Experience Platform 데이터 수집에서 모바일 애플리케이션 푸시 자격 증명을 추가해야 합니다.

Adobe이 대신 푸시 알림을 전송하도록 승인하려면 모바일 앱 푸시 자격 증명 등록이 필요합니다. 아래 절차를 참조하십시오.

1. From [!DNL Adobe Experience Platform Data Collection], 찾아보기 **[!UICONTROL App Surfaces]** 왼쪽 레일에 있습니다.

1. 클릭 **[!UICONTROL Create App Surface]** 새 구성을 만들려면

1. 을(를) 입력합니다. **[!UICONTROL Name]** 참조하십시오.

1. From **[!UICONTROL Mobile Application Configuration]**&#x200B;운영 시스템을 선택합니다.

   * **iOS용**

      1. 모바일 앱 입력 **번들 Id** 에서 **[!UICONTROL App ID (iOS Bundle ID)]** 필드. 앱 번들 ID는 **일반** 의 기본 대상 탭 **XCode**.

      1. 켜짐 **[!UICONTROL Push Credentials]** 단추를 클릭하여 자격 증명을 추가합니다.

      1. .p8 Apple 푸시 알림 인증 키 파일을 끌어서 놓습니다. 이 키는 **인증서**, **식별자** 및 **프로필** 페이지.

      1. 다음을 제공합니다. **키 ID**. p8 인증 키를 만드는 동안 지정된 10자 문자열입니다. 아래에서도 찾을 수 있습니다 **키** 탭 **인증서**, **식별자** 및 **프로필** 페이지.

      1. 다음을 제공합니다. **팀 ID**. 멤버십 탭에서 찾을 수 있는 문자열 값입니다.
   * **Android용**

      1. 다음을 제공합니다. **[!UICONTROL App ID (Android package name)]**: 일반적으로 패키지 이름은 의 앱 id입니다 `build.gradle` 파일.

      1. 켜짐 **[!UICONTROL Push Credentials]** 단추를 클릭하여 자격 증명을 추가합니다.

      1. FCM 푸시 자격 증명을 끌어다 놓습니다. 푸시 자격 증명을 가져오는 방법에 대한 자세한 내용은 [Google 설명서](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.



1. 클릭 **[!UICONTROL Save]** 앱 구성을 만들려면


## 2단계: Adobe Experience Platform 데이터 수집에서 모바일 태그 속성 설정 {#launch-property}

모바일 속성을 설정하면 모바일 앱 개발자 또는 마케터가 세션 시간 초과와 같은 모바일 SDK 속성을 구성할 수 있습니다. [!DNL Adobe Experience Platform] 타겟팅할 샌드박스 및 **[!UICONTROL Adobe Experience Platform Datasets]** 로 데이터를 전송하는 데 모바일 SDK에 사용할 수 있습니다.

설정 방법에 대한 자세한 내용 및 절차 **모바일 속성** 에서 자세히 설명하는 단계를 참조하십시오. [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

푸시 알림이 작동하는 데 필요한 SDK를 얻으려면 Android와 iOS 모두에 대해 다음 SDK 확장이 필요합니다.

* **[!UICONTROL Mobile Core]** (자동으로 설치됨)
* **[!UICONTROL Profile]** (자동으로 설치됨)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, 선택 사항이지만 모바일 구현을 디버깅하는 것이 좋습니다.

추가 정보 [!DNL Adobe Experience Platform Data Collection] 태그 [Adobe Experience Platform 설명서](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

만든 후 새 태그 속성을 열고 라이브러리를 만듭니다. 방법은 다음과 같습니다.

1. 찾아보기 **게시 흐름** 왼쪽 탐색에서 를 선택하고 을(를) 선택합니다. **라이브러리 추가**.
1. 라이브러리 이름을 입력하고 환경을 선택합니다.
1. 선택 **변경된 모든 리소스 추가**, 및 **저장 및 개발에 빌드**.
1. 마지막으로 이 라이브러리를 **작업 라이브러리 선택** 버튼을 클릭합니다.


## 3단계: 모바일 속성에서 Adobe Campaign 확장 구성 {#configure-extension}

다음 **Adobe Campaign Classic 확장** Adobe Experience Platform Mobile SDK용 는 모바일 앱에 대한 푸시 알림을 활성화하고 사용자 푸시 토큰을 수집하고 Adobe Experience Platform 서비스와의 상호 작용 측정을 관리하는 데 도움이 됩니다.

이 확장은 환경에 사전 설치되어 있으며 구성해야 합니다. 모바일 태그 속성에 대한 확장을 구성하려면 다음 단계를 수행합니다.

1. 이전에 만든 태그 속성을 엽니다.
1. 왼쪽 탐색에서 **확장**, 그리고 를 엽니다. **카탈로그** 탭. 검색 필드를 사용하여 **Adobe Campaign Classic** 확장.
1. Campaign Classic 카드에서 **설치** 버튼을 클릭합니다.
1. 에 설명된 대로 설정을 입력합니다. [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

이제 Campaign을 앱에 자세히 설명되어 있는 대로 추가할 수 있습니다.  [Adobe Experience Platform Mobile SDK 설명서](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## 4단계: Campaign에서 모바일 서비스 구성{#push-service}

모바일 앱을에서 설정했으면 [!DNL Adobe Experience Platform Data Collection]에서 푸시 알림을 전송하려면 두 개의 서비스(iOS 장치용으로 하나씩, Android 장치용)를 만들어야 합니다 **[!DNL Adobe Campaign]**.

에서 iOS 및 Android 푸시 알림용 서비스를 만들고 구성하는 방법을 알아봅니다 [이 섹션](../send/push.md#push-config).
