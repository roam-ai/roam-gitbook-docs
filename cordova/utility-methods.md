---
description: An archive of our SDK methods.
---

# Utility Methods

## Initialize SDK

### Android

```javascript
//In GeoSparkPlugin class include the code below.
@Override
public void initialize(CordovaInterface cordova, CordovaWebView webView) {
    super.initialize(cordova, webView);
    GeoSpark.initialize( this.cordova.getActivity().getApplication(), "PUBLISHABLEKEY");
}
```

### iOS

Import GeoSpark into your `AppDelegate` file.

{% tabs %}
{% tab title="Swift" %}
```swift
import GeoSpark
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
#import <GeoSpark/GeoSpark.h>
```
{% endtab %}
{% endtabs %}

Initialize the SDK in your AppDelegate class before calling any other GeoSpark methods under this `application:didFinishLaunchingWithOptions:`

```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions 
launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  GeoSpark.intialize("PUBLISHABLEKEY")
  return true
}
```

## Set DeviceToken

### Android

GeoSpark SDK is capable of sending push notifications to your users. [Add Firebase to your Android project](https://firebase.google.com/docs/android/setup) to get device token.

```javascript
GeoSpark.setDeviceToken(this, "FCM DeviceToken");
```

### iOS

GeoSpark SDK is capable of sending push notifications to your users. Check here to get device token.

```javascript
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken{
  [GeoSpark setDeviceToken:deviceToken];
}
```

## Create User

GeoSpark SDK needs an User ID object to identify the device. The SDK has a convenience method `createUser()` to create a user which returns User ID.

```javascript
cordova.plugins.geospark.createUser("Description", function(success){
    // do something on success
}, function(error){
    // do something on error
});
```

## Get User

If you already have an User ID, then SDK has a convenience method `getUser()` to start the session for the existing user.

```javascript
cordova.plugins.geospark.getUser("UserId", function(success){
    // do something on success
}, function(error){
    // do something on error
});  
```

## User Description

Adding description for the user makes it easier for you to identify your users, while tracking them in SDK. GeoSpark SDKs provide you with the option to modify the description any time for a user. This can also help you in easily identifying users on dashboard simply via the description.

```javascript
cordova.plugins.geospark.setDescription("Description", function(success){
    // do something on success
}, function(error){
     // do something on error
});
```

## Toggle User Events

Use this method after user creation to enable user events for geofence, activity and trips. By default, all user events will be disabled post user creation.

```javascript
cordova.plugins.geospark.toggleEvents(geofence, trip, activity,
function(success){
    // do something on success
}, function(error)  {
    // do something on error
});
```

## Get User Event Status

Use this method after user creation to get the current status of user events for geofence, activity and trips.

```javascript
cordova.plugins.geospark.getEventsStatus(function(success){
    // do something on success
}, function(error){
    // do something on error
});
```

## Check Location Permission

The SDK requires Location Permission to be granted.

```javascript
// Call this method to check Location Permission for Android & iOS
cordova.plugins.geospark.checkLocationPermission(function(status){
    // do something with status
});  
```

{% hint style="info" %}
status will be a string, one of:

* GRANTED
* DENIED
{% endhint %}

## Check Motion Permission

### iOS

The SDK requires motion permission to be granted.

```javascript
// Call this method to check Motion Permission for iOS
cordova.plugins.geospark.checkActivityPermission(function(status){
    // do something with status
});   
       
```

{% hint style="info" %}
status will be a string, one of:

* GRANTED
* DENIED
{% endhint %}

## Check Location Tracking

Check whether location tracking is started or not. This method returns boolean value.

```javascript
cordova.plugins.geospark.isLocationTracking(function(status){
    // do something with status
});
```

{% hint style="info" %}
status will be a string, one of:

* ENABLED
* DISABLED
{% endhint %}

## Check Location Services

### Android

The SDK requires GPS to be enabled and Location Services to be enabled with High Accuracy.

```javascript
// Call this method to check Location services for Android
cordova.plugins.geospark.checkLocationServices(function(status){
    // do something with status
}); 
```

{% hint style="info" %}
Status will be a string, one of:

* ENABLED
* DISABLED
{% endhint %}

## Request Location Permission

To request location permissions for the app, call

```javascript

// Call this method to request Location Permission for Android & iOS
cordova.plugins.geospark.requestLocationPermission(function(status){
    // do something with status
});
```

{% hint style="info" %}
Status will be a string, one of:

* ENABLED
* DISABLED
{% endhint %}

## Request Motion Permissions

### iOS

To request location permissions for the app, call

```javascript
// Call this method to request Motion Permission for iOS
cordova.plugins.geospark.requestActivityPermission(function(status){
    // do something with status
});            
               
```

{% hint style="info" %}
Status will be a string, one of:

* GRANTED
* DENIED
{% endhint %}

## Request Location Services

### Android

To enable GPS for the app, call

```javascript
// Call this method to request Location services for Android
cordova.plugins.geospark.requestLocationServices(function(status){
                    
    // do something with status
});
```

{% hint style="info" %}
status will be a string, one of:

* ENABLED
* DISABLED
{% endhint %}

## Start Location Tracking

To start tracking the user location.

```javascript
cordova.plugins.geospark.startTracking();
```

## Stop Location Tracking

You can stop tracking the user location.

```javascript
cordova.plugins.geospark.stopTracking();
```

## Location listener

You only need to call these methods once, as these settings will be persisted across App sessions.

To listen for location updates, you can add event listeners:

```markup
<application>
        ...
    <receiver android:name=".GeoSparkPlugin$GeoSparkCordovaReceiver"
                android:enabled="true"
                android:exported="false">
            <intent-filter>
            <action android:name="com.geospark.android.RECEIVED"/>
            </intent-filter>
    </receiver>
    ...
</application>
```

### Android

To listen for location in the background, register the `receiver` by adding a receiver element to the `application` element in your manifest.

```javascript
onDeviceReady: function() {
    this.receivedEvent('deviceready');
    cordova.plugins.geospark.onEvents(app.onGeoSparkEvents);
    cordova.plugins.geospark.onError(app.onGeoSparkError);
}


onGeoSparkEvents: function(userId, location) {
    // do something with userId, location
},
onGeoSparkError: function(error) {
    // do something on error
}
```

You can also remove event listeners:

```javascript
cordova.plugins.geospark.offEvents();
cordova.plugins.geospark.offError();
```

##  Current Location

Get current location of the user. You can set the accuracy from 20 to 100 meters.

```javascript
cordova.plugins.geospark.getCurrentLocation(accuracy, function(success){
    // do something on success
}, function(error){
    // do something on error
});
```

## Update Current Location

Using `updateCurrentLocation` method, one can update user current location, you can set the accuracy from 20 to 100 meters \(default is 20\).

```javascript
cordova.plugins.geospark.updateCurrentLocation(accuracy);
```

**Note:** This method should be used only if you need to update the current location of the device with better accuracy. Using this method often might consume battery.

## Start Trip

Start trips in GeoSpark SDK, using `startTrip()` method.

```javascript
cordova.plugins.geospark.startTrip("TripId", "Description", function(success){
    // do something on success
}, function(error){
    // do something on error
});
```

## End Trip

End trips in GeoSpark SDK, using `endTrip()` method.

```javascript
cordova.plugins.geospark.endTrip("TripId", function(success){
    // do something on success
}, function(error){
    // do something on error
}); 
```

## Active Trips

Get active trips in GeoSpark SDK, using `activeTrips()` method.

```javascript
cordova.plugins.geospark.activeTrips(function(success){
    // do something on success
}, function(error){
    // do something on error
});     
```

## SetTrackingInAppState

Call this method to configure GeoSpark SDK settings for enabling location tracking during given app states.

### iOS

Call this method to configure GeoSpark SDK settings for enabling location tracking during given app states.

```javascript
cordova.plugins.geospark.setTrackingInAppState([SETTINGS])
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SETTINGS</td>
      <td style="text-align:left">
        <p>Option 1: FOREGROUND (or) BACKGROUND (or) Terminated</p>
        <p>Option 2: ALWAYS_ON</p>
      </td>
    </tr>
  </tbody>
</table>

### Android

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SETTINGS</td>
      <td style="text-align:left">
        <p>Option 1: FOREGROUND (or) BACKGROUND</p>
        <p>Option 2: ALWAYS_ON</p>
      </td>
    </tr>
  </tbody>
</table>

```javascript
cordova.plugins.geospark.setTrackingInAppState([SETTINGS])

```

## SetTrackingInMotion

Call this method to configure GeoSpark SDK settings for enabling location tracking during given motion tracking.

### iOS

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SETTINGS</td>
      <td style="text-align:left">
        <p>Option 1: Stationary (or) Walking (or) Running (or) AutoMotive</p>
        <p>Option 2: ALL</p>
      </td>
    </tr>
  </tbody>
</table>

```javascript
cordova.plugins.geospark.setTrackingInMotion([SETTINGS])
```

### Android

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SETTINGS</td>
      <td style="text-align:left">
        <p>Option 1: Stationary (or) Walking (or) Running (or) AutoMotive</p>
        <p>Option 2: ALL</p>
      </td>
    </tr>
  </tbody>
</table>

```javascript
cordova.plugins.geospark.setTrackingInMotion([SETTINGS])
```

## Notification Opened Handler

By using this method inside FirebaseMessagingService class, track the campaigns impressions and counts.

```java
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
    super.onMessageReceived(remoteMessage);
    NotificationManager notificationManager = (NotificationManager)
context.getSystemService(Context.NOTIFICATION_SERVICE);
    ...
    intent.putExtra(GeoSpark.EXTRA,
GeoSpark.notificationReceiveHandler(remoteMessage.getData()));
    ...
    notificationManager.notify(NotificationID, builder.build());
}
```

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    ...
    GeoSpark.notificationOpenedHandler(this, getIntent());
}
```

```swift
-(void)userNotificationCenter:(UNUserNotificationCenter *)center didReceiveNotificationResponse:(UNNotificationResponse *)response withCompletionHandler:(void (^)(void))completionHandler{
  [GeoSpark notificationOpenedHandler:response];
  completionHandler();
}
```

## Logout

Logout from GeoSpark SDK, using logout\(\) method.

**NOTE** : You need to reinitialize the SDK in case you want to login again.

```javascript
cordova.plugins.geospark.logout(function(success){
    // do something on success
}, function(error){
    // do something on error
});   
```

## Disable Battery Optimization \(android 6+\)

When running the SDK on Android 6 \(and higher\), it is recommended to ask the user to disable battery optimization for your application. This makes sure that detections continue to work properly when the device is in Doze mode. Moreover, on Android Pie, it prevents Adaptive Battery from [bucketing](https://developer.android.com/about/versions/pie/power#buckets) your app based on usage and [restricting background processing](https://developer.android.com/reference/android/app/ActivityManager#isBackgroundRestricted), all of which that can impact the detection quality of the SDK.

After explaining to the user about the benefits of disabling battery optimization, call the `disableBatteryOptimization()` method of the GeoSpark class.

```javascript
cordova.plugins.geospark.disableBatteryOptimization();
```

## Check Battery Optimization

Check battery optimization

```java
cordova.plugins.geospark.isBatteryOptimizationEnabled(function(status){

    // do something with status
});
```

{% hint style="info" %}
status will be a string, one of:

* ENABLED
* DISABLED
{% endhint %}

