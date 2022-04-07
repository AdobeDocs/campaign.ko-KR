---
title: Campaign SDK와 앱 통합
description: Campaign Android 및 iOS SDK를 앱과 통합하는 방법을 알아봅니다
version: v8
feature: Push
role: Developer
level: Experienced
exl-id: 31c13d7e-55d1-4fbb-82e0-5779a17d65ac
source-git-commit: 8417b1b4b7370e2a2eed76e9f1ac395eccf0ac66
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Campaign SDK와 앱 통합 {#integrate-campaign-sdk}

iOS 및 Android용 Campaign SDK를 사용하여 모바일 애플리케이션을 Adobe Campaign 플랫폼에 쉽게 통합할 수 있습니다.

Android 및 iOS 지원 버전과 Campaign v8용 Campaign SDK 호환 버전은 [호환성 매트릭스](../start/compatibility-matrix.md#MobileSDK) .

>[!NOTE]
>
>Campaign 관리자는 [Experience Cloud 소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). 자세한 내용은 [고객 지원 Adobe](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).


## 통합 설정 선언 {#declaring-integration-settings}

Campaign SDK를 모바일 애플리케이션에 통합하려면 기능 관리자가 개발자에게 다음 정보를 제공해야 합니다.

* **통합 키**: Adobe Campaign 플랫폼을 활성화하여 모바일 애플리케이션을 식별합니다.

   >[!NOTE]
   >
   >이 통합 키는 Adobe Campaign 콘솔의 **[!UICONTROL Information]** 모바일 애플리케이션 전용 서비스 탭. 을(를) 참조하십시오. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app).

* **추적 URL**: Adobe Campaign 추적 서버의 주소와 일치합니다.
* **마케팅 URL**: 을 클릭하여 구독을 수집할 수 있습니다.

* **Android에서**:

   ```sql
   Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
   Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
   Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
   ```

* **iOS에서**:

   ```sql
   Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl setMarketingHost:strMktHost];
   [nl setTrackingHost:strTckHost];
   [nl setIntegrationKey:strIntegrationKey];
   ```

## Android SDK 통합

Android SDK는 JAVA로 작성된 jar 라이브러리입니다. Android 개발자는 이 플러그인을 사용하여 Adobe Campaign과 통합할 수 있습니다. 새 장치를 등록하고, 장치를 사용자에게 연결하고, 동작을 추적하는 등의 작업을 수행할 수 있습니다.

이 섹션에서 다음을 구현하는 Android 애플리케이션에서 Android SDK를 사용하는 방법을 알아봅니다. [Google Firebase Cloud Messaging(FCM)](https://firebase.google.com/docs/cloud-messaging/).

>[!CAUTION]
>
> Campaign v8의 경우 Campaign Android SDK v1.1.1을 사용합니다.

### FCM 구성

Android에서 푸시 알림을 사용하려면 FCM 계정이 있어야 하며 알림을 받도록 Android 애플리케이션을 구성하고 애플리케이션을 FCM 계정에 연결해야 합니다. 추가 정보 [Google 설명서](https://firebase.google.com/docs/cloud-messaging/).

을(를) 참조하십시오. [Google 설명서](https://firebase.google.com/docs/android/setup) android 프로젝트에 Firebase를 추가하려면 다음을 수행합니다.

에서 애플리케이션에서 FCM을 구현하는 방법을 알아봅니다 [Google 설명서](https://firebase.google.com/docs/android/setup).

>[!NOTE]
>
> * google-services.json을 다운로드하여 프로젝트에 추가하는 것을 잊지 마십시오.
>
> * 다음 `apiKey` 와 일치해야 함 `projectKey` 이 Android 애플리케이션에 연결된 Adobe Campaign Mobile 애플리케이션에서 을 설정합니다.


### Android SDK 구성

1. **SDK 초기화**

   Android SDK를 사용하기 전에 초기화해야 합니다. SDK 초기화는 `onCreate` 활동 함수입니다.

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       // initialize Campaign SDK
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       Neolane.getInstance().setIntegrationKey(settings.getString(YourApplicationActivity.APPUUID_NAME, YourApplicationActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(YourApplicationActivity.SOAPRT_NAME, YourApplicationActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(YourApplicationActivity.TRACKRT_NAME, YourApplicationActivity.DFT_TRACKRT));
       ...
   }
   ```

   다음 `IntegrationKey` 는 이 Android 애플리케이션에 연결된 Adobe Campaign Mobile 애플리케이션의 &#39;IntegrationKey&#39; 세트와 일치해야 합니다.

1. **Adobe Campaign 서버에 모바일 장치 등록**

   등록 기능을 사용하면 다음 작업을 수행할 수 있습니다.

   * 알림 ID 또는 푸시 ID(iOS용 deviceToken 및 Android용 registrationID)를 Adobe Campaign에 보냅니다.
   * 조정 키 또는 userKey 복구(예: 이메일 또는 계정 번호)

   앱 초기화 또는 사용자 작업 시 Adobe Campaign에 장치를 등록해야 합니다. 이 작업은 `registerDevice` 메서드를 사용합니다.

   ```sql
   public void onClick(View v)
   {
   SharedPreferences settings = this.context.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   EditText mailEdit = (EditText) this.context.findViewById(R.id.editText1);
   
   final String FCMRegistrationId = FirebaseInstanceId.getInstance().getToken();
   if (FCMRegistrationId != null)
       NeoTripActivity.registerOnNeolane(this.context, FCMRegistrationId, mailEdit.getText().toString());
   
   }
   ```

   YourApplicationActivity.java

   ```sql
   public static void registerOnNeolane(final Context ctx, String registrationId, String userKey)
   {
       NeolaneAsyncRunner neolaneAs = new NeolaneAsyncRunner(Neolane.getInstance());
       // Additional Subscription Parameters
       Map<String,Object> additionnalParam = new HashMap<String, Object>();
       additionnalParam.clear();
       SharedPreferences settings = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN1_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME1_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE1_NAME, ""));   
       }
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN2_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME2_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE2_NAME, ""));   
       }
       if ( additionnalParam.isEmpty() )
       {
           additionnalParam = null;
       }
       // Campaign Registration
       neolaneAs.registerDevice(registrationId, userKey, additionnalParam, ctx, new RequestListener() {
       public void onComplete(String e, Object obj)
       {
           Intent upd = new Intent();
           upd.setAction(BROADCAST_NEWREGISTER_ACTION);
           ctx.sendBroadcast(upd);
       }
   
       public void onNeolaneException(NeolaneException e, Object obj)
       {
           sendErrorMsg(e.getErrorString());
       }
   
       public void onIOException(IOException e, Object obj)
       {
           sendErrorMsg(e.getMessage());
       }
   
       public void sendErrorMsg(String err)
       {
           SharedPreferences.Editor edit = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE).edit();
           edit.putBoolean(YourApplicationActivity.REGISTRATION_ERROR_NEOLANE_KEYNAME, true);
           edit.commit();
           Intent toast = new Intent();
           toast.setAction(BROADCAST_TOAST_DISPLAY_TEXT);
           toast.putExtra("text", "An error happened, please register again (" + err + ")");
           ctx.sendBroadcast(toast);
       }
       });
   }
   ```

1. **사용자의 모바일 장치 토큰이 변경되면 Campaign에 알립니다**

   을 사용하는 것이 좋습니다 `registerDevice` 함수 호출 시 `onTokenRefresh` 사용자의 모바일 장치 토큰에 변경 사항을 Adobe Campaign에 알리는 함수입니다.

   예제:

   YourApplicationFirebaseInstanceIDService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.util.Log;
   
   import com.google.firebase.iid.FirebaseInstanceId;
   import com.google.firebase.iid.FirebaseInstanceIdService;
   
   import static android.content.SharedPreferences.*;
   
   public class YourApplicationFirebaseInstanceIDService extends FirebaseInstanceIdService 
   {
       @Override
       public void onTokenRefresh() 
       {
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (!settings.getBoolean(YourApplicationActivity.USE_GCM, false))
           {
           String refreshedToken = FirebaseInstanceId.getInstance().getToken();
           String userKey = settings.getString(YourApplicationActivity.USERKEY_NAME, "");
           Editor edit = settings.edit();
           edit.putString(YourApplicationActivity.FCM_REGISTRATIONID_NAME, refreshedToken);
           edit.commit();
           YourApplicationActivity.registerOnNeolane(this, refreshedToken, userKey);
           }
       }
   }
   ```

1. **Firebase 메시징 서비스 구성**

   확장 `FirebaseMessagingService` 에서 `onMessageReceived` 메시지를 수신할 콜백입니다. 을(를) 호출할 것을 추천합니다 `notifyReceive` 함수 `onMessageReceived` 모바일 장치에서 알림 수신을 추적할 수 있도록 콜백이 호출됩니다. Adobe Campaign에서 이 이름은 다음과 같습니다 **인쇄** 알림: 이 함수는 OS에서 알림을 표시하도록 요청하기 바로 전에 호출해야 합니다.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService 
       {
       private static final String TAG = "MyFirebaseMsgService";
   
       @Override
       public void onMessageReceived(RemoteMessage message) 
           {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
           }
       }   
   ```


   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras)
   {
       if( message == null ) message = "No Content";
       if( title == null )   title = "No title";
       if( url == null )     url = "http://www.tripadvisor.fr";
       int iconId = R.drawable.notif_neotrip;
   
       // notify Adobe Campaign that a notification just arrived
       SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
       NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
       nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
       public void onNeolaneException(NeolaneException arg0, Object arg1) {}
       public void onIOException(IOException arg0, Object arg1) {}
       public void onComplete(String arg0, Object arg1){}
       });
       if (yourApplication.isActivityVisible())
       {
       Log.i("INFO", "The application has the focus" );
       ...
       }
       else
       {
       // notification creation
       NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
       Notification notification;
   
       // Activity to start
       Intent notifIntent = new Intent(context.getApplicationContext(), NotificationActivity.class);
       notifIntent.putExtra("notificationText", message);
       notifIntent.putExtra(NotificationActivity.NOTIFICATION_URL_KEYNAME, url);
       notifIntent.putExtra("_dId", deliveryId);
       notifIntent.putExtra("_mId", messageId);
       notifIntent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
       PendingIntent contentIntent = PendingIntent.getActivity(context, 1, notifIntent, PendingIntent.FLAG_UPDATE_CURRENT);
   
       notification = new Notification.Builder(context)
               .setContentTitle(title)
               .setContentText(message)
               .setSmallIcon(iconId)
               .setContentIntent(contentIntent)
               .build();
   
       // launch the notification
       notification.flags |= Notification.FLAG_AUTO_CANCEL;
       notificationManager.notify(1234, notification);
       }
   }
   ```

1. **데이터 메시지 열기 추적**

   데이터 메시지의 경우 사용자가 알림을 클릭하여 언제 알림을 열지를 추적할 수 있습니다. `notifyOpening` 함수 위에 있어야 합니다. 사용자가 알림(다음 기간 동안 만들어짐)을 클릭하면 알림 활동이 만들어집니다 `onMessageReceived`함수 호출)

   ```sql
   public class NotificationActivity extends Activity {
       public void onCreate(Bundle savedBundle) {
           [...]
           Bundle extra = getIntent().getExtras();
           if (extra != null) {
               // reinit the Campaign sdk
               SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
               Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
               Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));               
               Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
               // Get the messageId and the deliveryId to perform tracking
               String deliveryId = extra.getString("_dId");
               String messageId = extra.getString("_mId");
   
               if (deliveryId != null && messageId != null) 
               {
                   try {
                   Neolane.getInstance().notifyOpening(messageId, Integer.valueOf(deliveryId));
                   } catch (NeolaneException e) {
                   // ...
                   } catch (IOException e) {
                   // ...
                   }
               }
           }
       }
   }
   ```

1. **알림 메시지 열기 및 클릭 추적**

   알림 메시지의 경우 열기/클릭 추적을 `notifyOpening` 함수 내에 있어야 합니다.

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       // initialize Campaign SDK
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```

   >[!NOTE]
   >
   > 사용자가 `click_action` 타깃팅된 활동 내의 옵션.


1. **데이터 메시지에 대한 추적 받기**

   데이터 메시지의 경우 추적이에서 수신됩니다 `onMessageReceived` 호출 수준. &#39;notifyReceive&#39; 함수를 호출해야 합니다.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService {
   private static final String TAG = "MyFirebaseMsgService";
   
   @Override
   public void onMessageReceived(RemoteMessage message) 
       {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
       }
   }
   ```

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras){
       .....
       .....
           // notify Campaign that a notification just arrived
           SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
               public void onNeolaneException(NeolaneException arg0, Object arg1) {}
               public void onIOException(IOException arg0, Object arg1) {}
               public void onComplete(String arg0, Object arg1){}
       });
   }
   ```

1. **알림 메시지에 대한 추적 받기**

   알림 메시지의 경우 추적 수신은 두 가지 수준에서 구성해야 합니다.

   * `onMessageReceived` (응용 프로그램이 백그라운드에 없음): 구현은 이전 섹션에서 수행되었습니다
   * `onCreate` 실행 활동(또는 타깃팅된 경우) `click_action`가 사용됩니다. (응용 프로그램이 백그라운드에 없습니다.)

   열기/클릭 추적과 동시에 수행해야 합니다.

   ```sql
   /** Called when the activity is first created. */
       @Override
       public void onCreate(Bundle savedInstanceState)
       {
           super.onCreate(savedInstanceState);
   
           SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
           // initialize Campaign SDK
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```


## iOS SDK 통합

1. **Adobe Campaign 서버에 모바일 장치 등록**

   등록 기능을 사용하면 다음 작업을 수행할 수 있습니다.

   * 알림 ID 또는 푸시 ID(iOS용 deviceToken 및 Android용 registrationID)를 Adobe Campaign에 보냅니다.
   * 조정 키 또는 userKey 복구(예: 이메일 또는 계정 번호)

   ```sql
   // Callback called on successful registration to the APNs
    - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
   {
     // Pass the token to Adobe Campaign
     Neolane_SDK *nl = [Neolane_SDK getInstance];
     [nl registerDevice:tokenString:self.userKey:dic];
   }
   ```

1. **추적 함수 활성화**

   추적 함수를 사용하면 알림이 활성화되는 시점을 추적할 수 있습니다(열기).

   ```sql
   (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   if( launchOptions ) { // Retrieve notification parameters here ... // Track application opening Neolane_SDK
   *nl = [Neolane_SDK getInstance]; [nl track:launchOptions:NL_TRACK_CLICK]; } 
   ...  
   completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **자동 알림 추적**

   iOS을 사용하면 자동 알림, 알림 또는 데이터를 표시하지 않고 모바일 애플리케이션으로 직접 전송할 수 있습니다. Adobe Campaign에서 추적할 수 있습니다.

   자동 알림을 추적하려면 아래 예를 따르십시오.

   ```sql
   // AppDelegate.m
   ...
   ...
   #import "AppDelegate.h"
   #import "Neolane_SDK.h"
   ...
   ...
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   NSLog(@"IN didReceiveRemoteNotification:fetchCompletionHandler");
   if (launchOptions) NSLog(@"IN launchOptions: %@", [launchOptions description]);
   NSLog(@"Application state: %ld", (long)application.applicationState);
   
   // Silent Notification (specific case, can use NL_TRACK_RECEIVE as the user does not have click/open the notification)
   if ([launchOptions[@"aps"][@"content-available"] intValue] == 1 )
       {
   NSLog(@"Silent Push Notification");
   ...  
   ...
   //Call receive tracking
           Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl track:launchOptions:NL_TRACK_RECEIVE];
   
   completionHandler(UIBackgroundFetchResultNoData); //Do not show notification
   return;
   }  
   ...
   ...
           completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **등록 상태 구성**

   위임 프로토콜을 사용하면 **registerDevice** 및 를 호출하여 등록 중 오류가 발생했는지 확인할 수 있습니다.

   다음 **registerDeviceStatus** 프로토타입:

   ```sql
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
   ```

   * **상태** 등록에 성공했는지 또는 오류가 발생했는지 알 수 있습니다.

   * **ErrorReason** 발생한 오류에 대한 자세한 정보를 제공합니다. 사용 가능한 오류 및 설명에 대한 자세한 내용은 아래 표를 참조하십시오.

   | 상태 | 설명 | ErrorReason |
   | ---------------------------------------------------------- | ------------------------------------------------------ | ----------------------------------------- |
   | ACCRregisterDeviceStatusSuccess | 등록 성공 | EMPTY |
   | ACCReisterDeviceStatusFailureMarketingServerHostnameEmpty | ACC 마케팅 서버 호스트 이름이 비어 있거나 설정되지 않았습니다. | EMPTY |
   | ACCReisterDeviceStatusFailureIntegrationKeyEmpty | 통합 키가 비어 있거나 설정되지 않았습니다. | EMPTY |
   | ACCReisterDeviceStatusFailureConnectionIssue | ACC의 연결 문제 | 추가 정보(OS 현재 언어) |
   | ACCRregisterDeviceStatusFailureUnknownUUID | 제공된 UUID(통합 키)를 알 수 없습니다. | EMPTY |
   | ACCRregisterDeviceStatusFailureUnexpectedError | ACC 서버에 예기치 않은 오류가 반환되었습니다. | ACC에 오류 메시지가 반환되었습니다. |

   {style=&quot;table-layout:auto&quot;}

   **Neolane_SDKDelegate** 프로토콜 및 **registerDeviceStatus** 위임 정의는 다음과 같습니다.

   ```sql
   //  Neolane_SDK.h
   //  Campaign SDK
   ..
   .. 
   // Register Device Status Enum
   typedef NS_ENUM(NSUInteger, ACCRegisterDeviceStatus) {
   ACCRegisterDeviceStatusSuccess,                               // Resistration Succeed
   ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty,   // The Campaign marketing server hostname is Empty or not set
   ACCRegisterDeviceStatusFailureIntegrationKeyEmpty,            // The integration key is empty or not set
   ACCRegisterDeviceStatusFailureConnectionIssue,                // Connection issue with Campaign, more information in errorReason
   ACCRegisterDeviceStatusFailureUnknownUUID,                    // The provided UUID (integration key) is unknown
   ACCRegisterDeviceStatusFailureUnexpectedError                 // Unexpected error returned by Campaign server, more information in errorReason
   };
   // define the protocol for the registerDeviceStatus delegate
   @protocol Neolane_SDKDelegate <NSObject>
   @optional
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status :(NSString *) errorReason;
   @end
   @interface Neolane_SDK: NSObject {
   } 
   ...
   ...
   // registerDeviceStatus delegate
   @property (nonatomic, weak) id <Neolane_SDKDelegate> delegate;
   ...
   ...
   @end
   ```

   구현하려면 **registerDeviceStatus** 위임, 다음 단계를 수행합니다.

   1. 구현 **setDelegate** 를 클릭합니다.

      ```sql
      // AppDelegate.m
      ...
      ... 
      - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
      {
      ...
      ...
          // Get the stored settings
      
          NSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];
          NSString *strMktHost = [defaults objectForKey:@"mktHost"];
          NSString *strTckHost = [defaults objectForKey:@"tckHost"];
          NSString *strIntegrationKey = [defaults objectForKey:@"integrationKey"];
          userKey = [defaults objectForKey:@"userKey"];
      
          // Configure Campaign SDK on first launch
          Neolane_SDK *nl = [Neolane_SDK getInstance];
          [nl setMarketingHost:strMktHost];
          [nl setTrackingHost:strTckHost];
          [nl setIntegrationKey:strIntegrationKey];
          [nl setDelegate:self];    // HERE
      ...
      ...
      }
      ```

   1. 에 프로토콜을 추가합니다. **@interface** 네 수업 중에

      ```sql
      //  AppDelegate.h
      
      #import <UIKit/UIKit.h>
      #import <CoreLocation/CoreLocation.h>
      #import "Neolane_SDK.h"
      
      @class LandingPageViewController;
      
      @interface AppDelegate : UIResponder <UIApplicationDelegate, CLLocationManagerDelegate, Neolane_SDKDelegate> {
          CLLocationManager *locationManager;
          NSString *userKey;
          NSString *mktServerUrl;
          NSString *tckServerUrl;
          NSString *homeURL;
          NSString *strLandingPageUrl;
          NSTimer *timer;
      }
      ```

   1. 에서 위임 구현 **AppDelegate**.

      ```sql
      //  AppDelegate.m
      
      #import "AppDelegate.h"
      #import "Neolane_SDK.h"
      #import "LandingPageViewController.h"
      #import "RootViewController.h"
      ...
      ...
      - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status :(NSString *) errorReason
      {
          NSLog(@"registerStatus: %lu",status);
      
          if ( errorReason != nil )
              NSLog(@"errorReason: %@",errorReason);
      
          if( status == ACCRegisterDeviceStatusSuccess )
          {
              // Registration successful
              ...
              ...
          }
          else { // An error occurred
              NSString *message;
              switch ( status ){
                  case ACCRegisterDeviceStatusFailureUnknownUUID:
                      message = @"Unkown IntegrationKey (UUID)";
                      break;
                  case ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty:
                      message = @"Marketing URL not set or Empty";
                      break;
                  case ACCRegisterDeviceStatusFailureIntegrationKeyEmpty:
                      message = @"Integration Key not set or empty";
                      break;
                  case ACCRegisterDeviceStatusFailureConnectionIssue:
                      message = [NSString stringWithFormat:@"%@ %@",@"Connection issue:",errorReason];
                      break;
                  case ACCRegisterDeviceStatusFailureUnexpectedError:
                  default:
                      message = [NSString stringWithFormat:@"%@ %@",@"Unexpected Error",errorReason];
                      break;
              }
          ...
          ...
          }
      }
      @end
      ```


## 변수 {#variables}

변수를 사용하면 알림을 받은 후 모바일 애플리케이션 동작을 정의할 수 있습니다. 이러한 변수는 모바일 애플리케이션 코드와 Adobe Campaign 콘솔의 **[!UICONTROL Variables]** 전용 모바일 애플리케이션 서비스의 탭을 클릭합니다.

![](../assets/do-not-localize/book.png) 추가 정보 **Campaign Classic v7 설명서** 모바일 앱에서: [iOS 구성 단계](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target=&quot;_blank&quot;} 및 [Android용 구성 단계](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html){target=&quot;_blank&quot;}.

다음은 모바일 애플리케이션에서 알림에 추가된 변수를 수집할 수 있도록 하는 코드의 예입니다. 이 예제에서는 &quot;VAR&quot; 변수를 사용합니다.

* **Android에서**:

   ```sql
   public void onReceive(Context context, Intent intent) {
        ...
       String event = intent.getStringExtra("VAR");
        ...
   }
   ```

* **iOS에서**:

   ```sql
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
   {
       ....
       if( launchOptions )
       {
           // When application is not already launched, the notification data if any are stored in the key 'UIApplicationLaunchOptionsRemoteNotificationKey'
           NSDictionary *localLaunchOptions = [launchOptions objectForKey:@"UIApplicationLaunchOptionsRemoteNotificationKey"];
           if( localLaunchOptions )
           {
            ...
            [localLaunchOptions objectForKey:@"VAR"];
           ...
           }
      }
   }
   
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   {
       if( launchOptions )
       {
        ...
           [launchOptions objectForKey:@"VAR"];
       }
   }
   ```

>[!CAUTION]
>
>Adobe은 iOS 및 Android의 경우 알림 크기가 4kB로 제한되므로 짧은 변수 이름을 선택할 것을 권장합니다.

## 알림 서비스 확장 {#notification-service-extension}

**iOS용**

미디어는 알림 서비스 확장 수준에서 다운로드해야 합니다.

```sql
#import "NotificationService.h"

@interface NotificationService ()

@property (nonatomic, strong) void (^contentHandler)(UNNotificationContent *contentToDeliver);
@property (nonatomic, strong) UNMutableNotificationContent *bestAttemptContent;

@end

@implementation NotificationService

- (void)didReceiveNotificationRequest:(UNNotificationRequest *)request withContentHandler:(void (^)(UNNotificationContent * _Nonnull))contentHandler {
    NSDictionary *userInfo = nil;
    NSString *url = nil;

    self.contentHandler = contentHandler;
    self.bestAttemptContent = [request.content mutableCopy];

    userInfo = request.content.userInfo;
    if ( userInfo != nil )
    {
        url = userInfo[@"mediaUrl"];  // Get the url of the media to download (Adobe Campaign additional variable)
    }
    ...
    // Perform the download to local storage
```

## 알림 컨텐츠 확장 {#notification-content-extension}

**iOS용**

이 수준에서 다음을 수행해야 합니다.

* 컨텐츠 확장을 Adobe Campaign에서 보낸 카테고리에 연결합니다.

   모바일 애플리케이션에서 이미지를 표시하려는 경우 Adobe Campaign과 모바일 애플리케이션에서 카테고리 값을 &quot;이미지&quot;로 설정할 수 있으며, **UNNotificationExtensionCategory** 매개 변수가 &quot;image&quot;로 설정되어 있습니다. 장치에서 푸시 알림을 받으면 정의된 카테고리 값에 따라 확장이 호출됩니다.

* 알림 레이아웃 정의

   관련 위젯을 사용하여 레이아웃을 정의해야 합니다. 이미지의 경우 위젯의 이름이 **ImageView**.

* 미디어 표시

   미디어 데이터를 위젯에 피드하려면 코드를 추가해야 합니다. 다음은 이미지에 대한 코드 예입니다.

   ```sql
   #import "NotificationViewController.h"
   #import <UserNotifications/UserNotifications.h>
   #import <UserNotificationsUI/UserNotificationsUI.h>
   
   @interface NotificationViewController () <UNNotificationContentExtension>
   
   @property (strong, nonatomic) IBOutlet UIImageView *imageView;
   @property (strong, nonatomic) IBOutlet UILabel *notifContent;
   @property (strong, nonatomic) IBOutlet UILabel *label;
   
   @end
   
   @implementation NotificationViewController
   
   - (void)viewDidLoad {
       [super viewDidLoad];
       // Do any required interface initialization here.
   }
   
   - (void)didReceiveNotification:(UNNotification *)notification {
       self.label.text = notification.request.content.title;
       self.notifContent.text = notification.request.content.body;
       UNNotificationAttachment *attachment = [notification.request.content.attachments objectAtIndex:0];
       if ([attachment.URL startAccessingSecurityScopedResource])
       {
         NSData * imageData = [[NSData alloc] initWithContentsOfURL:attachment.URL];
         self.imageView.image =[UIImage imageWithData: imageData];
         [attachment.URL stopAccessingSecurityScopedResource];
       }
   }
   @end
   ```
