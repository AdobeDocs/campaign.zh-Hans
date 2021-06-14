---
product: Adobe Campaign
title: 将Campaign SDK与您的应用程序集成
description: 了解如何将Campaign Android和iOS SDK与您的应用程序集成
version: v8
feature: 推送
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: eec769a09d59034dde59983bd0a53a4ac4fddde5
workflow-type: tm+mt
source-wordcount: '1567'
ht-degree: 1%

---

# 将Campaign SDK与您的应用程序{#integrate-campaign-sdk}集成

使用适用于iOS和Android的Campaign SDK来促进将移动应用程序集成到Adobe Campaign平台。

[兼容性矩阵](../start/compatibility-matrix.md#MobileSDK)中列出了支持Android和iOS的版本以及Campaign v8的兼容版本SDK。

>[!NOTE]
>
>作为Campaign管理员，您可以从[Experience Cloud软件分发](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html)下载Campaign SDK。 有关更多信息，请联系[Adobe客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。


## 声明集成设置{#declaring-integration-settings}

要将Campaign SDK集成到移动应用程序中，功能管理员必须向开发人员提供以下信息：

* **集成密钥**:以启用Adobe Campaign平台来识别移动应用程序。

   >[!NOTE]
   >
   >此集成密钥在Adobe Campaign控制台中的专用于移动设备应用程序的服务的&#x200B;**[!UICONTROL Information]**&#x200B;选项卡中输入。 请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app)。

* **跟踪URL**:与Adobe Campaign跟踪服务器的地址匹配。
* **营销URL**:以启用订阅的收集。

* **在Android中**:

   ```sql
   Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
   Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
   Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
   ```

* **在iOS中**:

   ```sql
   Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl setMarketingHost:strMktHost];
   [nl setTrackingHost:strTckHost];
   [nl setIntegrationKey:strIntegrationKey];
   ```

## 集成Android SDK

Android SDK是使用JAVA编写的Jar库。 它允许Android开发人员与Adobe Campaign集成：注册新设备、将设备与用户链接、跟踪行为等。

在此部分中，了解如何在实施[Google Firebase Cloud Messaging(FCM)](https://firebase.google.com/docs/cloud-messaging/)的Android应用程序中使用Android SDK。

### 配置FCM

要在Android上使用推送通知，您必须拥有FCM帐户，配置Android应用程序以接收通知，并将应用程序关联到FCM帐户。 请参阅[Google文档](https://firebase.google.com/docs/cloud-messaging/)，以了解更多信息。

请参阅[Google文档](https://firebase.google.com/docs/android/setup) ，将Firebase添加到您的Android项目。

了解如何在[Google Documentation](https://firebase.google.com/docs/android/setup)的应用程序中实施FCM。

>[!NOTE]
>
> * 请不要忘记下载google-services.json并将其添加到您的项目中。
   >
   > 
* `apiKey`必须与在链接到此Android应用程序的Adobe Campaign移动应用程序中设置的`projectKey`匹配。


### 配置Android SDK

1. **初始化SDK**

   在使用Android SDK之前，您需要对其进行初始化。 可以在活动的`onCreate`函数中初始化SDK。

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

   `IntegrationKey`必须与在链接到此Android应用程序的Adobe Campaign移动应用程序中设置的“IntegrationKey”匹配。

1. **将移动设备注册到Adobe Campaign服务器**

   注册功能允许您：

   * 将通知ID或推送ID（iOS的deviceToken和Android的registrationID）发送到Adobe Campaign。
   * 恢复协调密钥或userKey（例如，电子邮件或帐号）

   您必须在应用程序初始化或用户操作时，将设备注册到Adobe Campaign。 使用`registerDevice`方法可以轻松完成该操作。

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

1. **当用户的移动设备令牌发生更改时通知Campaign**

   我们建议您在调用`onTokenRefresh`函数时使用`registerDevice`函数，以通知Adobe Campaign用户的移动设备令牌发生更改。

   例如：

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

1. **配置Firebase Messaging Service**

   扩展`onMessageReceived`回调中的`FirebaseMessagingService`以接收消息。 我们建议您在调用`onMessageReceived`回调时调用`notifyReceive`函数，以在移动设备上启用通知接收跟踪。 在Adobe Campaign中，此通知名为&#x200B;**print**&#x200B;通知：应在请求操作系统显示通知之前调用此函数。

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

   对于Campaign Android SDK v1.1.1

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

1. **跟踪数据消息的打开情况**

   对于数据消息，您可以使用`notifyOpening`函数跟踪用户何时单击通知以将其打开。 当用户单击通知时，将创建通知活动（在`onMessageReceived`函数调用期间创建）

   对于Campaign Android SDK v1.1.1

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

1. **跟踪通知消息的打开数和点击数**

   对于通知消息，需要使用应用程序启动活动中的`notifyOpening`函数完成打开/点击跟踪，如下所示：

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
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
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
   > 如果用户在目标活动中使用`click_action`选项，则需要执行类似管理。


1. **接收数据消息的跟踪**

   对于数据消息，将在`onMessageReceived`调用级别接收跟踪。 需要调用“notifyReceive”函数。

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
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
               public void onNeolaneException(NeolaneException arg0, Object arg1) {}
               public void onIOException(IOException arg0, Object arg1) {}
               public void onComplete(String arg0, Object arg1){}
       });
   }
   ```

1. **接收通知消息的跟踪**

   对于通知消息，跟踪接收必须配置在两个级别：

   * `onMessageReceived` （应用程序不在后台）：在上一节中已完成实施
   * `onCreate` 启动活动(或使用函数的定 `click_action`位活动)。（应用程序不在后台）。

   它需要在打开/点击跟踪的同一时间完成。

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
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
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


## 集成iOS SDK

1. **将移动设备注册到Adobe Campaign服务器**

   注册功能允许您：

   * 将通知ID或推送ID（iOS的deviceToken和Android的registrationID）发送到Adobe Campaign。
   * 恢复协调密钥或userKey（例如，电子邮件或帐号）

   ```sql
   // Callback called on successful registration to the APNs
    - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
   {
     // Pass the token to Adobe Campaign
     Neolane_SDK *nl = [Neolane_SDK getInstance];
     [nl registerDevice:tokenString:self.userKey:dic];
   }
   ```

1. **启用跟踪函数**

   利用跟踪函数，可在激活（打开）通知时进行跟踪。

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

1. **无提示通知跟踪**

   iOS允许您发送静默通知、通知或数据，这些通知或数据将直接发送到移动应用程序，而不显示。 Adobe Campaign允许您跟踪它们。

   要跟踪无提示通知，请按照以下示例操作：

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

1. **配置注册状态**

   委托协议允许您获取&#x200B;**registerDevice**&#x200B;调用的结果，并可用于了解注册期间是否发生错误。

   **registerDeviceStatus**&#x200B;原型为：

   ```sql
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
   ```

   * **** 状态允许您了解注册是否成功或是否发生错误。

   * **** ErrorReason为您提供有关所发生错误的更多信息。有关可用错误及其说明的更多信息，请参阅下表。


| 状态 | 说明 | 错误原因 |
| ---------------------------------------------------------- | ------------------------------------------------------ | ----------------------------------------- |
| ACCRegisterDeviceStatusSuccess | 注册成功 | EMPTY |
| ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty | ACC营销服务器主机名为空或未设置。 | EMPTY |
| ACCRegisterDeviceStatusFailureIntegrationKeyEmpty | 集成键值为空或未设置。 | EMPTY |
| ACCRegisterDeviceStatusFailureConnectionIssue | 与ACC的连接问题 | 更多信息（使用操作系统当前语言） |
| ACCRegisterDeviceStatusFailureUnknownUUID | 提供的UUID（集成密钥）未知。 | EMPTY |
| ACCRegisterDeviceStatusFailureExpectedError | 向ACC服务器返回意外错误。 | 返回到ACC的错误消息。 |


{style=&quot;table-layout:auto&quot;}

    **Neolane_SDKelegate**协议和**registerDeviceStatus**委托定义如下：
    
    &quot;&#39;sql
    // Neolane_SDK.h
    // Campaign SDK
    ..
    ..
    //注册设备状
    态Enumtypedef NS_ENUM(NSUInteger， ACCRegisterDeviceStatus){
    ACCRegisterDeviceSuccess， //重新注册
    SeciputeACCRegisterDeviceStatusFailureMarketingServerHostname， //营销活动服务器为空或未设置
    ACCRegisterDeviceStatus/EmptyFailuteFailureFaule/集成密钥为空或未
    设置ACCRegisterDeviceStatusFailureConnectionIssue， //与Campaign的连接问题， 
    errorReasonACCRegisterDeviceStatusFailureUuidUUID中的更多信息， //提供的UID（集成密钥）为
    unknownACCRegisterDeviceStatusError //ErrorError，/ErrorrrError，有关注册协议的详细信息，请
    /
    /Reror，请注册原因
    /DeviceStatus委托 &lt;nsobject>
    @protocol Neolane_SDKelegate 
    @optional-(void)registerDeviceStatus:(ACCRegisterDeviceStatus)状态：(NSString *)errorReason;
    @end
    @interface Neolane_SDK:NSObject {
    }
    ...
    ...
    // registerDeviceStatus委托
    @property（非原子、弱）id &lt;neolane_sdkdelegate> 委托；
    ...
    ...
    @end
    &quot;
    
    要实施**registerDeviceStatus**委托，请执行以下步骤：
    
    1.在SDK初始化期间实施**setDelegate**。
    
    &quot;&#39;sql
    // AppDelegate.m
    ...
    ...
    -(BOOL)应用程序：(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
    {
    ..
    ...
    //获取存储
    
    的设置NSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];
    NSString *strMktHost = [defaults objectForKey:@&quot;mktHost&quot;];
    NSString *strHost = [defaults objectForKey:@&quot;tckHost&quot;];
     *STRNS集成=[keyDefaults]
    userKey = [defaults objectForKey:@&quot;userKey&quot;];
    
    //在首次启动时配置Campaign SDK 
    Neolane_SDK *nl = [Neolane_SDK getInstance];
    [nl setMarketingHost:strMktHost];
    [nlTrackingHost:strTckHost];
    [setIntegrationKey:strKey];
    ;[setNl]//此处
    ...
    ...
    }
    “
    
    1”在类的**@interface**中添加协议。
    
    &quot;&#39;sql
    // AppDelegate.h
    
    #import  &lt;uikit>
    #import  &lt;corelocation>
    #import &quot;Neolane_SDK.h&quot;
    
    @class LandingPageViewController;
    
    @interface AppDelegate :UIResponder  &lt;uiapplicationdelegate> {
    CLLocationManager *locationManager;
    NSString *userKey;
    NSString *mktServerUrl;
    NSString *tckServerUrl;
    NSString *homeURL;
    NSString *strLandingPageUrl;
    NSTimer *timer}
    &#39;
    
    
    1&quot;。在**AppDelegate**中实施委托。
    
    &quot;&#39;sql
    // AppDelegate.m
    
    #import &quot;AppDelegate.h&quot;
    #import &quot;Neolane_SDK.h&quot;
    #import &quot;LandingPageViewController.h&quot;
    #import &quot;RootViewController.h&quot;
    ..
    ...
    -(void)registerDeviceStatus:(ACCRegisterDeviceStatus)status :(NSString *)errorReason
    {
    NSLog(@&quot;registerStatus:%lu&quot;,status)；如果(
    
    errorReason != nil)
    NSLog(@&quot;errorReason:%@&quot;,errorReason);
    
    if(status == ACCRegisterDeviceStatusSuccess)
    {
    //注册成功
    ...
    ...
    }
    else { //发生错误
    NSString *message;
    交换机（状态）{
    case ACCRegisterDeviceStatusFailureUnknownUUID:
    message = @&quot;Unkown IntegrationKey(UUID)&quot;;
    break;
    caseACCRdeviceEgstStatusServerEmptyMarketingFailule:
    message = @&quot;营销URL未设置或为空&quot;;
    break;
    case ACCRegisterDeviceStatusFailureIntegrationKeyEmpty:
    message = @&quot;集成密钥未设置或空&quot;;
    break;
    case ACRegDeviceStatusConnectionIonIsue: [NS/>NSS20stringWithFormat:@&quot;%@ %@&quot;,@&quot;连接问题：&quot;,errorReason];
    break;
    case ACCRegisterDeviceStatusFailureExceptedError:
    default:
    message = [NSStringWithFormat:@&quot;%@&quot;,@&quot;意外错误&quot;,errorReason];
    a
    ...
    ...
    }
    }
    @end
    &quot;`

    
    
## 变量 {#variables}

利用变量，可在收到通知后定义移动应用程序行为。 这些变量必须在移动设备应用程序代码和Adobe Campaign控制台的专用移动设备应用程序服务的&#x200B;**[!UICONTROL Variables]**&#x200B;选项卡中定义。

[!DNL :arrow_upper_right:] 请参阅Campaign Classicv7 **文档，了** 解有关移动设备应用程序的更多信息： [iOS的配置步](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html) 骤和Android [的配置步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html)。

以下是允许移动设备应用程序收集通知中任何添加变量的代码示例。 在我们的示例中，我们使用“VAR”变量。

* **在Android中**:

   ```sql
   public void onReceive(Context context, Intent intent) {
        ...
       String event = intent.getStringExtra("VAR");
        ...
   }
   ```

* **在iOS中**:

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
>Adobe建议选择短变量名称，因为对于iOS和Android，通知大小限制为4kB。

## 通知服务扩展{#notification-service-extension}

**对于iOS**

必须在通知服务扩展级别下载媒体。

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

## 通知内容扩展{#notification-content-extension}

**对于iOS**

在此级别，您需要：

* 将内容扩展关联到由Adobe Campaign发送的类别：

   如果您希望移动应用程序显示图像，则可以在Adobe Campaign中将类别值设置为“image”，在移动应用程序中，您可以创建通知扩展，其中&#x200B;**UNNotificationExtensionCategory**&#x200B;参数设置为“image”。 在设备上收到推送通知时，将根据定义的类别值调用扩展。

* 定义通知布局

   您需要使用相关小组件定义布局。 对于图像，小组件名为&#x200B;**UIImageView**。

* 显示媒体

   您需要添加代码以将媒体数据馈送到小组件。 以下是图像的代码示例：

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
