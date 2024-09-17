---
product: campaign
title: 푸시 알림 채널 변경 예정 사항
description: 푸시 알림 채널 변경 예정 사항
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="Campaign Classic v7에도 적용됩니다."
badge-v8: label="v8" type="Positive" tooltip="Campaign v8에 적용"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: e7f0f20deb930be2a3b2f798f70d17644c646fb6
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 1%

---

# 푸시 알림 채널 변경 사항 {#push-upgrade}

Campaign을 사용하여 iOs 및 Android 디바이스에서 푸시 알림을 전송할 수 있습니다. 이를 위해 Campaign은 모바일 애플리케이션 구독 서비스를 사용합니다.

Android FCM(Firebase Cloud Messaging) 서비스에 대한 몇 가지 중요한 변경 사항은 2024년에 릴리스되며, Adobe Campaign 구현에 영향을 줄 수 있습니다. 이 변경 사항을 지원하려면 Android 푸시 메시지에 대한 구독 서비스 구성을 업데이트해야 할 수 있습니다.

또한 Adobe은 보다 안전하고 확장 가능한 인증 기반 연결보다 토큰 기반 연결을 APNs로 이동하는 것이 좋습니다.

## Google Android FCM(Firebase Cloud Messaging) 서비스 {#fcm-push-upgrade}

### 변경 사항 {#fcm-changes}

서비스 개선을 위한 Google의 지속적인 노력의 일환으로 레거시 FCM API는 **2024년 7월 22일**&#x200B;에 중단됩니다. [Google Firebase 설명서](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}에서 Firebase Cloud Messaging HTTP 프로토콜에 대해 자세히 알아보세요.

Adobe Campaign Classic v7 및 Adobe Campaign v8은 이미 푸시 알림 메시지를 보내기 위해 최신 API를 지원합니다. 그러나 일부 이전 구현은 여전히 이전 API에 의존합니다. 이러한 구현을 업데이트해야 합니다.

### 영향을 받습니까? {#fcm-impact}

현재 구현이 기존 API를 사용하여 FCM에 연결하는 구독 서비스를 지원하는 경우 영향을 받습니다. 서비스가 중단되지 않도록 하려면 최신 API로 전환해야 합니다. 이 경우 Adobe 팀이 연락을 드릴 것입니다.

영향을 받았는지 확인하려면 아래 필터에 따라 **서비스 및 구독**&#x200B;을 필터링할 수 있습니다.

![](assets/filter-services-fcm.png)


* 활성 푸시 알림 서비스에서 **HTTP(레거시)** API를 사용하는 경우 이 변경으로 인해 설정이 직접 영향을 받습니다. 아래 설명된 대로 현재 구성을 검토하고 최신 API로 이동해야 합니다.

* Android 푸시 알림용 **HTTP v1** API만 사용하는 경우 이미 규정을 준수하고 있으므로 추가 작업이 필요하지 않습니다.

### 업데이트 방법 {#fcm-transition-procedure}

#### 필수 구성 요소 {#fcm-transition-prerequisites}

* Campaign Classic v7의 경우 20.3.1 릴리스에서 HTTP v1에 대한 지원이 추가되었습니다. 환경이 이전 버전에서 실행 중인 경우 HTTP v1로 전환하기 위한 필수 조건은 환경을 [최신 Campaign Classic 빌드](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}(으)로 업그레이드하는 것입니다. Campaign v8의 경우 HTTP v1은 모든 릴리스에서 지원되며 업그레이드할 필요가 없습니다.

* 모바일 애플리케이션을 HTTP v1로 이동하려면 Android Firebase 관리 SDK 서비스의 계정 JSON 파일이 필요합니다. [Google Firebase 설명서](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}에서 이 파일을 가져오는 방법을 알아보세요.

* 하이브리드, 호스팅 및 Managed Services 배포의 경우 아래 전환 절차 외에도 Adobe에 문의하여 실시간(RT) 실행 서버를 업데이트합니다. 중간 소싱 서버는 영향을 받지 않습니다.

* Campaign Classic v7 온-프레미스 사용자는 마케팅 및 실시간 실행 서버를 모두 업그레이드해야 합니다. 중간 소싱 서버는 영향을 받지 않습니다.

* Campaign Classic v7 온-프레미스 또는 하이브리드 사용자는 Android 라우팅 외부 계정이 `androidPushConnectorV2.js`(으)로 구성되어 있는지 확인하세요. [자세히 알아보기](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android#configuring-external-account-android)

#### 전환 절차 {#fcm-transition-steps}

환경을 HTTP v1로 이동하려면 다음 단계를 수행합니다.

1. **서비스 및 구독** 목록으로 이동합니다.
1. **HTTP(레거시)** API 버전을 사용하는 모든 모바일 응용 프로그램을 나열합니다.
1. 이러한 각 모바일 응용 프로그램에 대해 **API 버전**&#x200B;을(를) **HTTP v1**(으)로 설정하십시오.
1. JSON 키 파일을 직접 로드하려면 **[!UICONTROL Load project json file to extract project details...]** 링크를 클릭하십시오.

   다음 세부 정보를 수동으로 입력할 수도 있습니다.

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. 구성이 올바르고 마케팅 서버가 FCM에 액세스할 수 있는지 확인하려면 **[!UICONTROL Test the connection]**&#x200B;을(를) 클릭하십시오. 중간 소싱 배포의 경우 **[!UICONTROL Test connection]** 단추는 서버에 Android FCM(Firebase Cloud Messaging) 서비스에 대한 액세스 권한이 있는지 확인할 수 없습니다.
1. 필요한 경우 **[!UICONTROL Application variables]**&#x200B;을(를) 사용하여 푸시 메시지 콘텐츠를 보강할 수 있습니다. 이는 완전히 맞춤화가 가능하며 모바일 디바이스로 전송되는 메시지 페이로드의 일부입니다.
1. **[!UICONTROL Finish]**&#x200B;을(를) 클릭한 뒤 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

   다음은 푸시 알림을 추가로 개인화할 FCM 페이로드 이름입니다. 이러한 옵션은 [여기](#fcm-apps)에 자세히 설명되어 있습니다.

   | 메시지 유형 | 구성 가능한 메시지 요소(FCM 페이로드 이름) | 구성 가능한 옵션(FCM 페이로드 이름) |
   |:-:|:-:|:-:|
   | 데이터 메시지 | N/A | validate_only |
   | 알림 메시지 | 제목, 본문, android_channel_id, 아이콘, 사운드, 태그, 색상, click_action, 이미지, 티커, 고정, 가시성, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>이러한 변경 사항이 모든 서버에 적용되면 Android 장치에 대한 모든 **새로운** 푸시 알림 배달에서 HTTP v1 API를 사용합니다. 재시도 중, 진행 중 및 사용 중인 기존 푸시 게재는 여전히 HTTP(기존) API를 사용합니다. 아래 섹션에서 업데이트 방법을 알아보세요.

#### 기존 템플릿 업데이트 {#fcm-transition-update}

전환 HTTP v1이 완료되면 Android 푸시 알림용 **게재 템플릿**&#x200B;을 업데이트하여 일괄 처리 메시지 수를 늘려야 합니다. 이렇게 하려면 Android 게재 템플릿의 속성을 찾은 다음 **게재** 탭에서 [메시지 일괄 처리 수량](../../v8/send/configure-and-send.md#delivery-batch-quantity)을 **256**(으)로 설정합니다. 이 변경 사항을 Android 게재에 사용되는 모든 게재 템플릿과 기존의 모든 Android 게재에 적용합니다.

HTTP v1을 지원하는 버전으로 업그레이드하기 전에 만든 기존 게재 및 게재 템플릿을 업데이트할 수도 있습니다. 다음을 수행하십시오.

* 관리 Cloud Service 또는 호스팅 고객의 경우 Adobe에 연락하여 기존 Android 게재 템플릿을 업데이트합니다.

* 온-프레미스 환경의 경우 `fcm-httpv1-migration.js` 스크립트를 다운로드하고 아래에 자세히 설명된 대로 실행합니다.

  [fcm-httpv1-migration.zip](assets/do-not-localize/fcm-httpv1-migration.zip) 다운로드

  >[!CAUTION]
  >
  >스크립트는 마케팅, 중간 소싱 및 실시간 환경에서 실행해야 합니다.


  +++기존 게재 및 템플릿 업데이트 단계(온-프레미스만 해당)

  HTTP v1을 지원하는 버전으로 업그레이드하기 전에 생성된 모든 게재 및 게재 템플릿을 패치하려면 다음 단계를 수행합니다.

   1. 패치 작업 중에 예기치 않은 문제가 발생한 경우 복원할 수 있도록 기존 게재 및 게재 템플릿을 패키지로 내보냅니다.
   1. Posgresql에서 다음 명령을 실행합니다.

      ```sql
      pg_dump -Fp -f /sftp/<db_name>-nmsdelivery-before_rd_script.sql -t nmsdelivery -d <db_name>
      ```

   1. 기본적으로 스크립트는 `dryrun` 모드에 있으며 해당 모드에서 시작하여 일부 게재를 패치해야 하는지 확인할 수 있습니다.

      명령

      ```sql
      nlserver javascript -instance:<instance_name> -file fcm-httpv1-migration.js 
      ```

      출력

      ```sql
      ...
      HH:MM:SS >   Processing delivery (id:123456,  label:'Deliver on Android - New', name:'DM1234')
      HH:MM:SS >   Dry run: Would update androidCheckParams for delivery (id:123456,  label:'Deliver on Android - New', name:'DM1234')
      HH:MM:SS >   Processing delivery (id:567890,  label:'Deliver on Android - New', name:'DM5678')
      HH:MM:SS >   Dry run: Would update androidCheckParams for delivery (id:567890,  label:'Deliver on Android - New', name:'DM5678')
      ...
      HH:MM:SS >   Summary (XYZ processed deliverie(s) or delivery template(s)):
      HH:MM:SS >>  - X had not patchable androidCheckParams formula!
      HH:MM:SS >   - Y had androidCheckParams formula patched.
      HH:MM:SS >   - Z ignored as alreading having androidCheckParams formula patched.
      ```

      >[!NOTE]
      >
      >`not patchable` 게재를 수동으로 업데이트해야 합니다. 해당 ID는 로그에서 찾을 수 있습니다.

   1. 다음과 같은 방법으로 실행 모드에서 스크립트를 실행하여 게재를 업데이트합니다.

      ```sql
      nlserver javascript -instance:<instance_name> -file fcm-httpv1-migration.js -arg:run
      ```

+++

### 내 Android 앱의 영향은 무엇입니까? {#fcm-apps}

Android 모바일 애플리케이션의 코드에는 특정 변경 사항이 필요하지 않으며 알림 동작은 변경되지 않아야 합니다.

그러나 HTTP v1을 사용하면 **[!UICONTROL HTTPV1 additional options]**&#x200B;을(를) 통해 푸시 알림을 추가로 개인화할 수 있습니다.

![](assets/android-push-additional-options.png)

다음을 수행할 수 있습니다.

* 알림의 티커 텍스트를 설정하려면 **[!UICONTROL Ticker]** 필드를 사용하십시오.
* **[!UICONTROL Image]** 필드를 사용하여 알림에 표시할 이미지의 URL을 설정하십시오.
* **[!UICONTROL Notification Count]** 필드를 사용하여 응용 프로그램 아이콘에 직접 표시할 읽지 않은 새 정보의 수를 설정하십시오.
* **[!UICONTROL Sticky]** 옵션을 false로 설정하여 사용자가 클릭할 때 알림이 자동으로 해제되도록 합니다. true로 설정하면 사용자가 알림을 클릭할 때에도 알림이 계속 표시됩니다.
* 알림의 **[!UICONTROL Notification Priority]** 수준을 기본값, 최소, 낮음 또는 높음으로 설정하십시오.
* 알림의 **[!UICONTROL Visibility]** 수준을 공개, 비공개 또는 비밀로 설정합니다.

**[!UICONTROL HTTP v1 additional options]** 및 이러한 필드를 채우는 방법에 대한 자세한 내용은 [FCM 설명서](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}를 참조하십시오.



## Apple iOS APNs(푸시 알림 서비스) {#apns-push-upgrade}

### 변경 사항 {#ios-changes}

Apple에서 권장하는 대로 상태 비저장 인증 토큰을 사용하여 APNs(Apple 푸시 알림 서비스)와의 통신을 보호해야 합니다.

토큰 기반 인증은 APNs와 통신하는 상태 비저장 방법을 제공합니다. 상태 비저장 통신은 APNs가 공급자 서버와 관련된 인증서 또는 기타 정보를 조회할 필요가 없기 때문에 인증서 기반 통신보다 빠릅니다. 토큰 기반 인증을 사용하면 다음과 같은 다른 이점이 있습니다.

* 여러 공급자 서버에서 동일한 토큰을 사용할 수 있습니다.

* 하나의 토큰을 사용하여 회사의 모든 앱에 대한 알림을 배포할 수 있습니다.

[Apple 개발자 설명서](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}에서 APNs에 대한 토큰 기반 연결에 대해 자세히 알아보세요.

Adobe Campaign Classic v7 및 Adobe Campaign v8은 토큰 기반 연결과 인증서 기반 연결을 모두 지원합니다. 구현이 인증서 기반 연결을 사용하는 경우 Adobe은 토큰 기반 연결로 업데이트할 것을 강력히 권장합니다.

### 영향을 받습니까? {#ios-impact}

현재 구현이 APNs에 연결하기 위해 인증서 기반 요청을 사용하는 경우 영향을 받습니다. 토큰 기반 연결로 전환하는 것이 좋습니다.

영향을 받았는지 확인하려면 아래 필터에 따라 **서비스 및 구독**&#x200B;을 필터링할 수 있습니다.

![](assets/filter-services-ios.png)


* 활성 푸시 알림 서비스에서 **인증서 기반 인증** 모드(.p12)를 사용하는 경우 아래 설명된 대로 현재 구현을 검토하고 **토큰 기반 인증** 모드(.p8)로 이동해야 합니다.

* 설정에서 iOS 푸시 알림에 대해 **토큰 기반 인증** 모드만 사용하는 경우 구현이 이미 최신 상태이므로 추가 작업이 필요하지 않습니다.

### 업데이트 방법 {#ios-transition-procedure}

#### 필수 구성 요소 {#ios-transition-prerequisites}

* Campaign Classic v7의 경우 20.2 릴리스에서 **토큰 기반 인증** 모드에 대한 지원이 추가되었습니다. 환경이 이전 버전에서 실행 중인 경우 이 변경을 위한 필수 조건은 환경을 [최신 Campaign Classic 빌드](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}(으)로 업그레이드하는 것입니다. Campaign v8의 경우 **토큰 기반 인증** 모드가 모든 릴리스에서 지원되며 업그레이드할 필요가 없습니다.

* 서버에서 사용하는 토큰을 생성하려면 APNs 인증 토큰 서명 키가 필요합니다. [Apple 개발자 설명서](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}에 설명된 대로 Apple 개발자 계정에서 이 키를 요청합니다.

* 하이브리드, 호스팅 및 Managed Services 배포의 경우 아래 전환 절차 외에도 Adobe에 문의하여 실시간(RT) 실행 서버를 업데이트합니다. 중간 소싱 서버는 영향을 받지 않습니다.

* Campaign Classic v7 온-프레미스 사용자는 마케팅 및 실시간 실행 서버를 모두 업그레이드해야 합니다. 중간 소싱 서버는 영향을 받지 않습니다.

#### 전환 절차 {#ios-transition-steps}

iOS 모바일 애플리케이션을 토큰 기반 인증 모드로 이동하려면 다음 단계를 따르십시오.

1. **서비스 및 구독** 목록으로 이동합니다.
1. **인증서 기반 인증** 모드(.p12)를 사용하는 모든 모바일 응용 프로그램을 나열합니다.
1. 이러한 각 모바일 응용 프로그램을 편집하고 **인증서/개인 키** 탭으로 이동합니다.
1. **인증 모드** 드롭다운에서 **토큰 기반 인증** 모드(.p8)를 선택합니다.
1. APNs 연결 설정 **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** 및 **[!UICONTROL Bundle Id]**&#x200B;을(를) 입력한 다음 **[!UICONTROL Enter the private key...]**&#x200B;을(를) 클릭하여 p8 인증서를 선택하십시오.

   ![](assets/token-based-certif.png)

1. **[!UICONTROL Test the connection]**&#x200B;을(를) 클릭하여 구성이 올바르고 서버에서 APNs에 액세스할 수 있는지 확인합니다. 중간 소싱 배포의 경우 **[!UICONTROL Test connection]** 단추는 서버에 APNs 액세스 권한이 있는지 확인할 수 없습니다.
1. **[!UICONTROL Next]**&#x200B;을(를) 클릭하여 프로덕션 응용 프로그램 구성을 시작하고 위에 설명된 것과 동일한 단계를 수행합니다.
1. **[!UICONTROL Finish]**&#x200B;을(를) 클릭한 뒤 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

이제 iOS 애플리케이션이 토큰 기반 인증 모드로 이동되었습니다.
