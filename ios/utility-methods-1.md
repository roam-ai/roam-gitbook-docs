# Utility Methods

## Set DeviceToken <a id="UtilityMethods(iOS)-SetDeviceToken"></a>

The GeoSpark SDK is capable of sending push notifications to your users. [Check here](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/index.html#//apple_ref/doc/uid/TP40008194-CH3-SW1) to get the device token.

{% tabs %}
{% tab title="Swift" %}
```swift
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
     GeoSpark.setDeviceToken(deviceToken)
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken{
    [GeoSpark setDeviceToken:deviceToken];
}
```
{% endtab %}
{% endtabs %}

## Check Location Permission <a id="UtilityMethods(iOS)-CheckLocationPermission"></a>

Check whether your app has location permission.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.isLocationEnabled()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark isLocationEnabled];
```
{% endtab %}
{% endtabs %}

## Location Permission Status <a id="UtilityMethods(iOS)-LocationPermissionStatus"></a>

By using the `locationPermissionStatus` method you can check the location permission status.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.locationPermissionStatus()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [GeoSpark locationPermissionStatus];
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
notDetermined = 0

restricted = 1

denied = 2

authorizedAlways = 3

authorizedWhenInUse = 4
{% endhint %}

## Request Location Permission <a id="UtilityMethods(iOS)-RequestLocationPermission"></a>

Check whether your App has location permission.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.requestLocation()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [GeoSpark requestLocation];
```
{% endtab %}
{% endtabs %}

## Check Location Tracking <a id="UtilityMethods(iOS)-CheckLocationTracking"></a>

Check whether location tracking is started or not. This method returns a boolean value.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.isLocationTracking()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark isLocationTracking];
```
{% endtab %}
{% endtabs %}

## Current Location <a id="UtilityMethods(iOS)-CurrentLocation"></a>

Get the current location of the user. You can set the accuracy between 5 to 100 meters \(default is 10\).

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getCurrentLocation(accuracy) { (location, error) in
    //location?.coordinate.latitude           
    //location?.coordinate.longitude       
    //location?.altitude
    //  error?.code
    //  error?.message 
}
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark getCurrentLocation:<#(NSInteger)#> handler:^(CLLocation * location, GeoSparkError * error) {
    //location?.coordinate.latitude           
    //location?.coordinate.longitude       
    //location?.altitude
    //  error?.code
    //  error?.message 
}];
```
{% endtab %}
{% endtabs %}

## Update Current Location <a id="UtilityMethods(iOS)-UpdateCurrentLocation"></a>

Using the `updateCurrentLocation` method, you can update user current location. You can set the accuracy between 5 to 100 meters \(default is 10\).

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.updateCurrentLocation(accuracy)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark updateCurrentLocation:accuracy];
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
This method should be used only if you need to update the current location of the device with better accuracy. Using this method consistently will consume more battery.  
  
The higher the accuracy the longer the response time time. In some cases it could take up to 30 seconds depending on the GPS signal strength.
{% endhint %}

## Notification Opened Handler <a id="UtilityMethods(iOS)-NotificationOpenedHandler"></a>

By using this method inside the Notification delegate method you can track the campaign's impressions and counts.

{% tabs %}
{% tab title="Swift" %}
```swift
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void)
        {
                GeoSpark.notificationOpenedHandler(response)
                completionHandler()
        }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
- (void)userNotificationCenter:(UNUserNotificationCenter *)center didReceiveNotificationResponse:(UNNotificationResponse *)response withCompletionHandler:(void (^)(void))completionHandler{
    [GeoSpark notificationOpenedHandler:response];
}
```
{% endtab %}
{% endtabs %}

