# Utility Methods

## Set DeviceToken <a id="UtilityMethods(Android)-SetDeviceToken"></a>

The Roam SDK is capable of sending push notifications to your users. [Add Firebase to your Android project](https://firebase.google.com/docs/android/setup) to get the device token.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.setDeviceToken("FCM DeviceToken")
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.setDeviceToken("FCM DeviceToken");
```
{% endtab %}
{% endtabs %}

## Get DeviceToken <a id="UtilityMethods(Android)-GetDeviceToken"></a>

To get the `FCM DeviceToken` from the SDK.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getDeviceToken()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getDeviceToken();
```
{% endtab %}
{% endtabs %}

## Check location permission <a id="UtilityMethods(Android)-Checklocationpermission"></a>

Check whether your App has location permission. Returns a boolean, which is `true` if the location permission has been granted, and `false` otherwise.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.checkLocationPermission()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.checkLocationPermission();
```
{% endtab %}
{% endtabs %}

## Check location services <a id="UtilityMethods(Android)-Checklocationservices"></a>

Check whether the device has location services enabled. Returns a boolean, which is `true` if the location services are on, and `false` otherwise.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.checkLocationServices()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.checkLocationServices();
```
{% endtab %}
{% endtabs %}

## Check Background Location Permission <a id="UtilityMethods(Android)-CheckBackgroundLocationPermission"></a>

Check whether your App has background location permission. Returns a boolean, which is `true` if the background location permission has been granted, and `false` otherwise.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.checkBackgroundLocationPermission()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.checkBackgroundLocationPermission();
```
{% endtab %}
{% endtabs %}

## Request Location Permissions <a id="UtilityMethods(Android)-RequestLocationPermissions"></a>

Call this method to request the user to enable location permissions.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.requestLocationPermission(this)
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.requestLocationPermission(this);
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
override fun onRequestPermissionsResult(requestCode: Int, permissions:
    Array<String>, grantResults:IntArray) {
        when (requestCode) {
            Roam.REQUEST_CODE_LOCATION_PERMISSION->
            if (grantResults[0] ==PackageManager.PERMISSION_GRANTED) {
            ....
            } else if (grantResults[0] ==PackageManager.PERMISSION_DENIED) {
            ....
            }
        }
}
```
{% endtab %}

{% tab title="Java" %}
```java
//Callback from request location permission method.
@Override
public void onRequestPermissionsResult(int requestCode, String permissions[], int[] grantResults) {
   switch (requestCode) {
      case Roam.REQUEST_CODE_LOCATION_PERMISSION:
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            ...
         } else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {
            ...   
         }
      break;
   }
}
```
{% endtab %}
{% endtabs %}

## Request Location Services <a id="UtilityMethods(Android)-RequestLocationServices"></a>

Call this method to enable location services.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.requestLocationServices(this)
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.requestLocationServices(this);
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
      super.onActivityResult(requestCode, resultCode, data)
      if (requestCode == Roam.REQUEST_CODE_LOCATION_ENABLED) {
            ....
      }
}
```
{% endtab %}

{% tab title="Java" %}
```java
//Callback from request location services method.
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
   super.onActivityResult(requestCode, resultCode, data);
   if (requestCode == Roam.REQUEST_CODE_LOCATION_ENABLED) {
   }
}
```
{% endtab %}
{% endtabs %}

## Request Background Location Permission <a id="UtilityMethods(Android)-RequestBackgroundLocationPermission"></a>

Call this method to request the user to enable background location permissions.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.requestBackgroundLocationPermission(this)
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.requestBackgroundLocationPermission(this);
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
override fun onRequestPermissionsResult(requestCode: Int, permissions:
Array<String>, grantResults: IntArray) {
    when (requestCode) {
    Roam.REQUEST_CODE_BACKGROUND_LOCATION_PERMISSION->
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            ...
        } 
        else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {
            ...
        }
    }
}
```
{% endtab %}

{% tab title="Java" %}
```java
//Callback from request background location permission method.
@Override
public void onRequestPermissionsResult(intrequestCode, Stringpermissions[],
int[] grantResults) {
    switch (requestCode) {
        case Roam.REQUEST_CODE_BACKGROUND_LOCATION_PERMISSION:
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {  
               ...      
        } 
        else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {         
                ...        
        }
        break;   
    }
}
```
{% endtab %}
{% endtabs %}

## Check Location Tracking <a id="UtilityMethods(Android)-CheckLocationTracking"></a>

Check whether location tracking is started or not. This method returns a boolean value.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.isLocationTracking()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.isLocationTracking();
```
{% endtab %}
{% endtabs %}

## Update Current Location <a id="UtilityMethods(Android)-UpdateCurrentLocation"></a>

Using the `updateCurrentLocation` method, you can update the user's current location, you can set the accuracy from 10 to 100 meters \(default is 10\).

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.updateCurrentLocation(DesiredAccuracy, accuracy)
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.updateCurrentLocation(DesiredAccuracy, accuracy);
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
This method should be used only if you need to update the current location of the device with better accuracy. Using this method consistently will consume more battery.

The higher the accuracy the longer the response time time. In some cases it could take up to 30 seconds depending on the GPS signal strength.
{% endhint %}

| **Parameter** | **Description** |
| :--- | :--- |
| DesiredAccuracy | RoamTrackingMode.DesiredAccuracy.**HIGH** or RoamTrackingMode.DesiredAccuracy.**MEDIUM** or RoamTrackingMode.DesiredAccuracy.**LOW** |

## Logout <a id="Logout"></a>

Logout from Roam SDK, using `logout()` method.

**NOTE :** You need to reinitialize the SDK in case you want to login again.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.logout(object : RoamLogoutCallback {
        override fun onSuccess(message: String) {
                
        }
        override fun onFailure(roamError: RoamError) {
                // Access Error code and message here
                // roamError.code
                // roamError.message
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.logout(new RoamLogoutCallback() {
      @Override
      public void onSuccess(String message) {

      }

      @Override
      public void onFailure(RoamError roamError) {
                // Access Error code and message here
                // roamError.code;
                // roamError.message;
      }
});
```
{% endtab %}
{% endtabs %}

## Notification Opened Handler <a id="UtilityMethods(Android)-NotificationOpenedHandler"></a>

By using this method inside FirebaseMessagingService class, track the campaign impressions and counts.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
override fun onMessageReceived(RemoteMessage remoteMessage) {
  super.onMessageReceived(remoteMessage)
  val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as
        NotificationManager
  ....
  intent.putExtra(Roam.EXTRA, Roam.notificationReceiveHandler(remoteMessage.getData()))
  ....
}
```
{% endtab %}

{% tab title="Java" %}
```java
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
   super.onMessageReceived(remoteMessage);
   NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
   ...
   intent.putExtra(Roam.EXTRA, Roam.notificationReceiveHandler(remoteMessage.getData()));
   ...
   notificationManager.notify(NotificationID, builder.build());
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
      ....
    Roam.notificationOpenedHandler(intent)
)
```
{% endtab %}

{% tab title="Java" %}
```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    ...
    Roam.notificationOpenedHandler(getIntent());
}
```
{% endtab %}
{% endtabs %}

## Disable Battery Optimization \(android 6+\) <a id="UtilityMethods(Android)-DisableBatteryOptimization(android6+)"></a>

When running the SDK on Android 6 \(and higher\), it is recommended to ask the user to disable battery optimization for your application. This ensures that location tracking continues to work when the device is in Doze mode.

Moreover, on Android Pie, disabling battery optimization prevents Adaptive Battery from [bucketing](https://developer.android.com/about/versions/pie/power#buckets) your app based on usage and [restricting background processing](https://developer.android.com/reference/android/app/ActivityManager#isBackgroundRestricted), which can impact the detection quality of the SDK.

After explaining the benefits of disabling battery optimization, call the `disableBatteryOptimization()` method of the Roam class.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.disableBatteryOptimization()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.disableBatteryOptimization();
```
{% endtab %}
{% endtabs %}

This will trigger a system dialog asking the user to allow disabling battery optimization for your app.

## Check Battery Optimization <a id="UtilityMethods(Android)-CheckBatteryOptimization"></a>

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.isBatteryOptimizationEnabled()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.isBatteryOptimizationEnabled();
```
{% endtab %}
{% endtabs %}



