---
description: Integrate our SDK in your iOS app.
---

# Quickstart

GeoSpark provides an iOS SDK that enables App developers to track location, geofence and trips.

## Step 1: Install SDK

Install using Cocoapods, open `podfile` add SDK to file.

```groovy
pod 'GeoSpark'
```

Once you have updated your Podfile run `pod install` in your terminal.

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

## **Step 2: Configure project**

To configure the location services, add following entries to the `Info.plist` file.

![](../.gitbook/assets/step-2img1.png)

Then, in your project settings, go to `Capabilities > Background Modes` and turn on background fetch, location updates ,remote-notifications.

![](../.gitbook/assets/3%20%281%29%20%284%29.png)

## **Step 3: Initialize SDK**

Initialize the SDK in your `AppDelegate` class before calling any other GeoSpark methods under this `application:didFinishLaunchingWithOptions:`

{% tabs %}
{% tab title="Swift" %}
```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
    GeoSpark.intialize("PUBLISHABLEKEY")
        return true
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [GeoSpark intialize:@"PUBLISHABLEKEY"];
    return YES;
}
```
{% endtab %}
{% endtabs %}

## **Step 4: Create User**

The SDK needs an User ID object to identify the device. Before creating user you should have device token as you cannot create user without device token.

{% tabs %}
{% tab title="Swift" %}
```swift
  GeoSpark.createUser("User Description",{ (user) in
      // user.userId
    },onFailure: { (error) in
      // error.errorCode
      // error.errorMessage
  })
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
  [GeoSpark createUser:@"User Description" :^(GeoSparkUser * user) {
      // user.userId
    } onFailure:^(GeoSparkError * error) {
      // error.errorCode
      // error.errorMessage
  }];
```
{% endtab %}
{% endtabs %}

## **Step 5: Start Location Tracking**

To start tracking the location

{% tabs %}
{% tab title="Swift" %}
```swift
// To enable motion and location, call requestMotion and requestLocation methods.
if GeoSpark.isMotionEnabled() == false {
    GeoSpark.requestMotion()
 }else if GeoSpark.isLocationEnabled() == false{
    GeoSpark.requestLocation()
  }else {
    GeoSpark.startTracking()
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
if ([GeoSpark isMotionEnabled] == false) {
    [GeoSpark requestMotion];
 }else if ([GeoSpark isLocationEnabled] == false){
    [GeoSpark requestLocation];
 }else {
    [GeoSpark startTracking];
 }
```
{% endtab %}
{% endtabs %}

