# Quickstart

The GeoSpark iOS SDK makes it quick and easy to build a location tracker for your iOS app. We provide powerful and customizable tracking modes and features that can be used to collect your users’ location updates.

## Requirements <a id="Requirements"></a>

To use the GeoSpark SDK, the following things are required:

* Get yourself a free [GeoSpark Account](http://motion.dev/signup). No credit card required.
* Create a project and add an iOS app to the project.
* You need the SDK\_KEY in your project settings which you’ll need to initialize the SDK.
* Now you’re ready to integrate the SDK into your iOS application. 

The GeoSpark iOS SDK requires Xcode 10.0 or later and is compatible with apps targeting iOS version 10 and above

## Run the example application

The GeoSpark Example repository on [GitHub](https://github.com/geosparks/geospark-sdk-ios) includes example apps that demonstrate the use of the v3  GeoSpark SDK for iOS.

See a Swift example app in `Examples/`.

To run the example app, clone this repository, add your publishable "YOUR-SDK-KEY" key in `AppDelegate.swift`, and build the app.

Make sure the bundle\_id is the same as the one registered in our GeoSpark Playground dashboard.

{% embed url="https://github.com/geosparks/geospark-sdk-ios" %}

## Xcode Setup <a id="Xcode-Setup"></a>

To integrate the GeoSpark SDK, you need a GeoSpark account.

1. Go to Xcode &gt; File &gt; New Project
2. Configure the information property list file `Info.plist` with an XML snippet that contains data about your app. You need to add strings for `NSLocationWhenInUseUsageDescription` in the `Info.plist` file to prompt the user during location permissions for foreground location tracking. For background location tracking, you also need to add a string for `NSLocationAlwaysUsageDescription` and `NSLocationAlwaysAndWhenInUseUsageDescription` in the same `Info.plist` file. 

```markup
<key>NSLocationWhenInUseUsageDescription</key>
<string>Add description for foreground only location usage.</string>

<key>NSLocationAlwaysUsageDescription</key>
<string>Add description for background location usage. iOS 10 and below"</string>

<key>NSLocationAlwaysAndWhenInUseUsageDescription</key>
<string>Add description for background location usage. iOS 11 and above</string>
```

1. Next you need to enable

`Background fetch` and `Location updates` under `Project Setting` &gt; `Capabilities` &gt; `Background Modes`.![](blob:https://geosparkai.atlassian.net/0567fccc-f9cd-4aed-99bb-ffd40ecb1a5d#media-blob-url=true&id=c932b7b5-7c68-42f7-8bc4-6f89cb0e733e&collection=contentId-1064796161&contextId=1064796161&mimeType=image%2Fpng&name=2cc43aff-8a5b-4c7b-86c2-ae8f609f2ffa.png&size=79702&width=1280&height=417)

## SDK Installation <a id="CocoaPods-Installation"></a>

### CocoaPods Installation

Follow the steps below to add the SDK to the project using CocoaPods. Add the below to the `Podfile`

```markup
pod 'GeoSpark'
```

Then run `pod install`.

This will add the GeoSpark SDK and its dependencies to your project. The GeoSpark SDK depends on `CoreLocation`, `AWSMobileClient` and `AWSIoT` for fetching locations and its transmission to our servers. The SDK supports iOS 10 and above.

### Manual Installation

If you’re not familiar with using Cocoapods or prefer manual installation, we’ve added a ZIP file to the SDK. Use this link to download the [GeoSpark.framework.zip](https://github.com/geosparks/geospark-sdk-ios/releases/download/3.1.6/GeoSpark.framework.zip) file. 

Unzip the file and add the GeoSpark SDK `GeoSpark.framework` to your Xcode project by dragging the file into your Project Navigator.![](blob:https://geosparkai.atlassian.net/997da5b3-f160-437f-b240-4b6a5afe372b#media-blob-url=true&id=4b34491a-a000-4b02-9fa8-8df4f06342e8&collection=contentId-1064796161&contextId=1064796161&mimeType=image%2Fpng&name=wQcTKbTdAmnCM_Bij6T-sGoiJ8eBo-DRbUbiW_dvsuB14KNJi9EQ96o5E9O0Fu8toR_hmU7Xzgay-t-kt5y4sErnoKmI5o59sl4UfNivKrWlA2ys52MGFBwUOcx1RzRIvnklPLk2&size=49854&width=394&height=435)

![](../.gitbook/assets/image%20%2811%29.png)

You can do this by selecting the project file in the navigator on the left side of the Xcode window, and then navigating to the Linked Frameworks and Libraries section. From there, click the “+” button to add the GeoSpark framework.![](blob:https://geosparkai.atlassian.net/e188e1d2-6901-4cf0-9a81-b7a9abaab6d9#media-blob-url=true&id=8cafe20c-01c5-463a-8e79-6764701f4242&collection=contentId-1064796161&contextId=1064796161&mimeType=image%2Fpng&name=sde-FVntSuYdGFg42U3k4vq8lnC-ZvwTCT2o74X8ihXBY2n5HdTcrVSX2sMSFUnfi3OtBAc4besx5GP3zfLNXMZdZlTS1DLOERGtfgkj250TT5beO8ItPEFoRn_6Bvk131jXhWPi&size=34114&width=1194&height=564)

![](../.gitbook/assets/image%20%281%29.png)

We have to add to below [AWS framework](https://github.com/aws-amplify/aws-sdk-ios)

* AWSAuthCore.framework
* AWSCognitoIdentityProvider.framework
* AWSCognitoIdentityProviderASF.framework
* AWSCore.framework
* AWSMobileClient.framework
* AWSPinpoint.framework

## Initialize SDK <a id="Initialize-SDK"></a>

Add the following code in `AppDelegate.`. This code imports the SDK and allows the SDK to use other methods.

```swift
import GeoSpark
```

After import, add the below code under `application(_:didFinishLaunchingWithOptions:)` in your `AppDelegate` class. The SDK must be initialized before calling any of the other SDK methods using your project's SDK key.

```swift
GeoSpark.initialize("YOUR-PUBLISHABLE-KEY-GOES-HERE")
```

## Request Permissions <a id="Request-Permissions"></a>

Before you start location tracking, you need to get permission from the user for your application to access locations. 

1. Import `CoreLocation` at the top of the `AppDelegate`. file.  

```swift
import CoreLocation
```

   2.  Make the below class declaration for Location Manager.

```swift
let locationManager = CLLocationManager()
```

   3. Open `AppDelegate.` and add this line before the return statement in `application(_:didFinishLaunchingWithOptions:).` With this line, you ask users to allow the app to access location data both in the background and the foreground.

```swift
 locationManager.requestLocation()
```

## Location Tracking <a id="Location-Tracking"></a>

### Start Tracking <a id="Start-Tracking"></a>

```swift
GeoSpark.startSelfTracking(TrackingMode)
```

Use one of the tracking modes while you use the `GeoSpark.startSelfTracking`  method.

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

```swift
GeoSpark.stopSelfTracking()
```

## Tracking Modes

### Adaptive Tracking

GeoSpark has three default tracking modes along with a custom version. They are different based on the frequency of location updates and battery consumption. The higher the frequency, the higher the battery consumption.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

```swift
//active tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.active);
// balanced tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.balanced);
// passive tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.passive);
```

### **Distance Interval** Tracking <a id="Custom-Tracking-Modes"></a>

The SDK also provides a custom tracking mode which allows you to customize and build your own tracking mode as per your requirement.

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Distance Interval | Meters | 1m ~ 2500m |

**Distance between location updates example code:**

```swift
// define a custom tracking method
let trackingMethod = GeoSparkTrackingMethods.custom
// update the settings for the created method as per need
trackingMethod.activityType = .fitness
trackingMethod.pausesLocationUpdatesAutomatically = true
trackingMethod.showsBackgroundLocationIndicator = true
trackingMethod.distanceFilter = 10
trackingMethod.useSignificantLocationChanges = false
trackingMethod.useRegionMonitoring = false
trackingMethod.useVisits = false
trackingMethod.useSignificantLocationChanges = false
trackingMethod.desiredAccuracy = .nearestTenMeters
GeoSpark.startSelfTracking(.custom, options: trackingMethod)
```

### **Time Interval** Tracking <a id="Custom-Tracking-Modes"></a>

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Time Interval | seconds | 1s - 10000s |

**Time between location updates example code:**

```swift
// define a custom tracking method
let trackingMethod = GeoSparkTrackingMethods.custom
trackingMethod.allowBackgroundLocationUpdates = true
trackingMethod.desiredAccuracy = kCLLocationAccuracyBest
// Update interval in seconds
trackingMethod.updateInterval = 10
GeoSpark.startSelfTracking(.custom, options: trackingMethod)
```

## Location Listener

In order to listen to location updates locally, you can follow the below steps for self tracking.

{% page-ref page="sdk-methods-1/listeners-and-events.md" %}



