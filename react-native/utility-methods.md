---
description: An archive of our SDK methods.
---

# Utility Methods

## Initialize SDK

Import the module in `App.js` file

```jsx
import GeoSpark from 'react-native-geospark'; 
```

### **Android**

Initialize the SDK with your `publishable key`.

```java
//In onCreate method of your Application class include the code below.
public class MainApplication extends Application implements ReactApplication {
   @Override
   public void onCreate() {
        super.onCreate();
        SoLoader.init(this, / native exopackage / false);
        GeoSpark.initialize(this, "PUBLISH_KEY");
   }
}    
```

### **iOS**

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

Initialize the SDK in your `AppDelegate` class before calling any other GeoSpark methods under this `application:didFinishLaunchingWithOptions:`

{% code title="Swift" %}
```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
    GeoSpark.intialize("PUBLISHABLEKEY")
    return true
}
```
{% endcode %}

## Set DeviceToken

### Android

GeoSpark SDK is capable of sending push notifications to your users.[Add Firebase to your Android project](https://firebase.google.com/docs/android/setup) to get device token.

```java
GeoSpark.setDeviceToken(context, "FCM DeviceToken");
```

### IOS

GeoSpark SDK is capable of sending push notifications to your users.[Check here](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/index.html#//apple_ref/doc/uid/TP40008194-CH3-SW1) to get device token.

```objectivec
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken{
 		 [GeoSpark setDeviceToken:deviceToken];
 }
```

## Create a user

GeoSpark SDK needs a User ID object to identify the device. The SDK has a convenience method `createUser()` to create a user which returns User ID.

```jsx
GeoSpark.createUser("User Description", (success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});
```

## Get User

If you already have a User ID object. The SDK has a convenience method `getUser()` to start the session for the existing user.

```jsx
GeoSpark.getUser("userId", (success) => {
    // do something on success                               
 }, (error) => {
    // do something on error                   
});
```

## User Description

Adding description for the user makes it easier for you to identify your users, while tracking them in SDK. GeoSpark SDKs provide you with the option to modify the description any time for a user. This can also help you in easily identifying users on dashboard simply via the description.

```jsx
GeoSpark.setDescription("User description", (success) => {
    // do something on success
}, (error) => {
    // do something on success
});
```

## Toggle User Events

Use this method after user creation to enable user events for geofence, activity and trips. By default, all user events will be disabled post user creation.

```jsx
GeoSpark.toggleEvents(geofence, trip, activity, (success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});
```

## Get User Event Status

Use this method after user creation to get the current status of user events for geofence, activity and trips.

```jsx
GeoSpark.getEventsStatus((success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});
```

## Check location permission

The SDK requires Location Permission to be granted.

```jsx
GeoSpark.checkLocationPermission( (status) => {
    // do something with status
});  
```

{% hint style="info" %}
status will be a string, one of:

* GRANTED
* DENIED
{% endhint %}

## Check motion permission

The SDK requires motion Permission to be granted.

```jsx
GeoSpark.checkMotionPermission( (status) => {
    // do something with status
});  
```

{% hint style="info" %}
status will be a string, one of:

* GRANTED
* DENIED
{% endhint %}

## Check background location permission

### Android

The SDK requires background location permission to be granted.

```jsx
GeoSpark.checkBackgroundLocationPermission( (status) => {
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

```jsx
GeoSpark.isLocationTracking( (status) => {
    // do something with status
});
```

## Check location services

### **Android**

The SDK requires GPS to be enabled and Location Services to be enabled with High Accuracy.

```jsx
GeoSpark.checkLocationServices( (status) => {
    // do something with status
});  
```

{% hint style="info" %}
status will be a string, one of:

* ENABLED
* DISABLED
{% endhint %}

## Request location permissions

To request location permissions for the app, call

```jsx
GeoSpark.requestLocationPermission();  
```

## Request motion permissions

To request location permissions for the app, call

```jsx
GeoSpark.requestMotionPermission();  
```

## Request background location permissions

### Android

To request location permissions for the app, call

```jsx
GeoSpark.requestBackgroundLocationPermission();
```

## Request location services

### **Android**

To enable GPS for the app, call

```jsx
GeoSpark.requestLocationServices();
```

## Start location tracking

To start tracking the user location.

```jsx
GeoSpark.startTracking(this);
```

## Stop location tracking

You can stop tracking the user location.

```jsx
GeoSpark.stopTracking(this);
```

## Location Listener

You only need to call these methods once, as these settings will be persisted across App sessions.

To listen for location updates, you can add event listeners:

```jsx
GeoSpark.startListener('location', (result) => {
    // do something with result.location, result.user, result.activity
});
```

Add event listeners outside of your component lifecycle \(e.g., outside of `componentDidMount`\) if you want them to work when the app is in the background.

You can also remove event listeners:

```jsx
GeoSpark.stopListener('location');  
```

## Current Location

Get current location of the user. You can set the accuracy from 20 to 100 meters.

### Android

```jsx
GeoSpark.getCurrentLocation(accuracy, (success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});
```

### IOS

```jsx
GeoSpark.getCurrentLocationIos(accuracy, (success) => { 
  // do something on success    
});
```

## Update Current Location

Using `updateCurrentLocation` method, one can update user current location, you can set the accuracy from 20 to 100 meters \(default is 20\).

```jsx
GeoSpark.updateCurrentLocation(Accuracy);
```

{% hint style="info" %}
This method should be used only if you need to update the current location of the device with better accuracy. Using this method often might consume battery.
{% endhint %}

## Start Trip

Start trips in Geospark SDK, using `startTrip()` method.

```jsx
GeoSpark.startTrip("Trip Id","Description", (success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});
```

## End Trip

End trips in Geospark SDK, using `endTrip()` method.

```jsx
GeoSpark.endTrip("tripId", (success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});
```

## Active Trips

Get active trips in GeoSpark SDK, using `activeTrips()` method.

```jsx
GeoSpark.activeTrips( (success) => { 
  // do something on success    
}, (error) => {
 // do something on error
});               
```

## SetTrackingInAppState

Call this method to configure GeoSpark SDK settings for enabling location tracking during given App states.

### **iOS**

```jsx
GeoSpark.setTrackingInAppState([Settings]); 
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
        <p>Option 1 : [GeoSpark.IOSType.Foreground (OR) GeoSpark.IOSType.Background
          (OR) GeoSpark.IOSType.Terminated]</p>
        <p>Option 2 : [GeoSpark.IOSType.AlwaysOn]</p>
      </td>
    </tr>
  </tbody>
</table>

### **Android**

```jsx
GeoSpark.setTrackingInAppState([Settings]); 
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
        <p>Option 1 : [GeoSpark.Type.FOREGROUND (OR) GeoSpark.Type.BACKGROUND]</p>
        <p>Option 2 : [GeoSpark.Type.ALWAYS_ON]</p>
      </td>
    </tr>
  </tbody>
</table>

## SetTrackingInMotion

Call this method to configure GeoSpark SDK settings for enabling location tracking during given motion tracking.

### **iOS**

```jsx
GeoSpark.setTrackingInMotion([Settings]);                            
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
        <p>Option 1 : [GeoSpark.IOSType.Running (OR) GeoSpark.IOSType.Walking (OR)
          GeoSpark.IOSType.AutoMotive (OR)GeoSpark.IOSType.Stationary]</p>
        <p>Option 2 : [GeoSpark.IOSType.All]</p>
      </td>
    </tr>
  </tbody>
</table>

### **Android**

```jsx
GeoSpark.setTrackingInMotion([Settings]);                            
```

| Parameter | Description |
| :--- | :--- |
| SETTINGS | Option 1 : \[GeoSpark.Type.STOP \(OR\) GeoSpark.Type.WALK \(OR\) GeoSpark.Type.RUNNING \(OR\) GeoSpark.Type.BICYCLE \(OR\) GeoSpark.Type.DRIVE\] Option 2 : \[GeoSpark.Type.ALL\] |

## Notification Opened Handler

By using this method inside FirebaseMessagingService class, track the campaigns impressions and counts.

### Android

```java
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
   super.onMessageReceived(remoteMessage);
   NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
   ...
   intent.putExtra(GeoSpark.EXTRA, GeoSpark.notificationReceiveHandler(remoteMessage.getData()));
   ...
   notificationManager.notify(NotificationID, builder.build());
}
```

{% code title="MainActivity.java" %}
```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    ...
    GeoSpark.notificationOpenedHandler(this, getIntent());
}
```
{% endcode %}

### IOS

```objectivec
-(void)userNotificationCenter:(UNUserNotificationCenter *)center didReceiveNotificationResponse:(UNNotificationResponse *)response withCompletionHandler:(void (^)(void))completionHandler{
  [GeoSpark notificationOpenedHandler:response];
  completionHandler();
}
```

## Logout

Logout from GeoSpark SDK, using `logout()` method.

**NOTE :** You need to reinitialize the SDK in case you want to login again.

```jsx
GeoSpark.logout((success) => {
    // do something on success
}, (error) => {
    // do something on success
});
```

## **Disable Battery Optimization \(android 6+\)**

When running the SDK on Android 6 \(and higher\), it is recommended to ask the user to disable battery optimization for your application. This makes sure that detections continue to work properly when the device is in Doze mode. Moreover, on Android Pie, it prevents Adaptive Battery from [bucketing](https://developer.android.com/about/versions/pie/power#buckets) your app based on usage and [restricting background processing](https://developer.android.com/reference/android/app/ActivityManager#isBackgroundRestricted), all of which that can impact the detection quality of the SDK.

After explaining to the user about the benefits of disabling battery optimization, call the `disableBatteryOptimization()` method of the GeoSpark class.

```jsx
GeoSpark.disableBatteryOptimization();
```

This will trigger a system dialog asking the user to allow disabling battery optimization for your app.

## Check **Battery Optimization**

```jsx
GeoSpark.isBatteryOptimizationEnabled( (status) => {
   // do something with status
});
```

