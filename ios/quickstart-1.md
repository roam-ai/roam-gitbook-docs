# Quickstart

The Roam iOS SDK makes it quick and easy to build a location tracker for your iOS app. We provide powerful and customizable tracking modes and features that can be used to collect your users’ location updates.

## Requirements <a id="Requirements"></a>

To use the Roam SDK, the following things are required:

* Get yourself a free [Roam Account](https://roam.ai/dashboard/signup/). No credit card required.
* Create a project and add an iOS app to the project.
* You need the SDK\_KEY in your project settings which you’ll need to initialize the SDK.
* Now you’re ready to integrate the SDK into your iOS application. 

The Roam iOS SDK requires Xcode 10.0 or later and is compatible with apps targeting iOS version 10 and above

## Run the example application

The Roam Example repository on [GitHub](https://github.com/roam-ai/roam-ios) includes example apps that demonstrate the use of the v3  Roam SDK for iOS.

See a Swift example app in `Example/`.

To run the example app, clone this repository, add your publishable `YOUR-PUBLISHABLE-KEY` key in `AppDelegate.swift`, and build the app.

Make sure the bundle\_id is the same as the one registered in our Roam Playground dashboard.

{% embed url="https://github.com/roam-ai/roam-ios" %}

## Xcode Setup <a id="Xcode-Setup"></a>

To integrate the Roam SDK, you need a Roam account.

1. Go to Xcode &gt; File &gt; New Project
2. Configure the information property list file `Info.plist` with an XML snippet that contains data about your app. You need to add strings for `NSLocationWhenInUseUsageDescription` in the `Info.plist` file to prompt the user during location permissions for foreground location tracking. For background location tracking, you also need to add a string for `NSLocationAlwaysUsageDescription` and `NSLocationAlwaysAndWhenInUseUsageDescription` in the same `Info.plist` file.

   ```text
   <key>NSLocationWhenInUseUsageDescription</key>
   <string>Add description for foreground only location usage.</string>
   <key>NSLocationAlwaysUsageDescription</key>
   <string>Add description for background location usage. iOS 10 and below"</string>
   <key>NSLocationAlwaysAndWhenInUseUsageDescription</key>
   <string>Add description for background location usage. iOS 11 and above</string>
   ```

![](https://user-images.githubusercontent.com/19217956/123445597-aa8cf380-d5f5-11eb-9188-15ad742f11a8.png)

Next you need to enable`Background fetch` and `Location updates` under `Project Setting` &gt; `Capabilities` &gt; `Background Modes`.

![](../.gitbook/assets/image%20%288%29.png)

## SDK Installation <a id="CocoaPods-Installation"></a>

There are several ways to integrate the Roam Mobile SDK for iOS into your own project:

*  Swift Package Manager
*  CocoaPods
*  Carthage \(Will be added soon\)
*  Dynamic Frameworks

### **Swift Package Manager Installation**

Swift Package Manager is distributed with Xcode. To start adding the AWS SDK to your iOS project, open your project in Xcode and select File &gt; Swift Packages &gt; Add Package Dependency.

![](https://user-images.githubusercontent.com/19217956/123749908-9259f480-d8d3-11eb-8193-1a02d940a298.png)

Enter the URL for the Roam SDK for iOS Swift Package Manager GitHub repo \([https://github.com/roam-ai/roam-ios](https://github.com/roam-ai/roam-ios)\) into the search bar and click Next.

![](https://user-images.githubusercontent.com/19217956/123750283-0d230f80-d8d4-11eb-9bfc-7f2004b612c5.png)

You'll see the repository rules for which version of the SDK you want Swift Package Manager to install. Choose the first rule, Version, and select Up to Next Minor as it will use the latest compatible version of the dependency that can be detected from the main branch, then click Next.

![](https://user-images.githubusercontent.com/19217956/123750579-612df400-d8d4-11eb-918a-48799fa7999b.png)

Select `roam-ios`, then click Finish.

![Screenshot 2021-06-29 at 12 22 38 PM](https://user-images.githubusercontent.com/19217956/123750894-b8cc5f80-d8d4-11eb-9bdc-e809ad706702.png)

You can always go back and modify which SPM packages are included in your project by opening the Swift Packages tab for your project: Click on the Project file in the Xcode navigator, then click on your project's icon, then select the Swift Packages tab.

### **CocoaPods Installation**

Follow the steps below to add the SDK to the project using CocoaPods. Add the below to the `Podfile`

```text
pod 'roam-ios'
```

Then run `pod install`.

This will add the Roam SDK and its dependencies to your project. The Roam SDK depends on `CoreLocation`, `AWSMobileClient` and `AWSIoT` for fetching locations and its transmission to our servers. The SDK supports iOS 10 and above.

### **Manual Installation**

If you’re not familiar with using Cocoapods or prefer manual installation, we’ve added a ZIP file to the SDK. Use this link to download the [Roam.zip](https://github.com/roam-ai/roam-ios/releases/download/0.0.6/Roam.xcframework.zip) file.

Unzip the file and add the Roam `Roam.framework` to your Xcode project by dragging the file into your Project Navigator.

You can do this by selecting the project file in the navigator on the left side of the Xcode window, and then navigating to the Linked Frameworks and Libraries section. From there, click the “+” button to add the Roam framework. You will also want to add the following frameworks from this [link](https://github.com/aws-amplify/aws-sdk-ios).

```text
AWSAuthCore.xcframework
AWSCognitoIdentityProvider.xcframework
AWSCognitoIdentityProviderASF.xcframework
AWSCore.xcframework
AWSIoT.xcframework
AWSMobileClientXCF.xcframework
```

Make sure the the added frameworks under Linked Frameworks and Libraries section are selected as `Embed & Sign`

![](https://user-images.githubusercontent.com/19217956/123446788-d8bf0300-d5f6-11eb-96e2-d88e432c209c.png)

## Initialize SDK <a id="Initialize-SDK"></a>

Add the following code in `AppDelegate` file. This code imports the SDK and allows the SDK to use other methods.

```text
import Roam
```

After import, add the below code under`application(_:didFinishLaunchingWithOptions:)` in your `AppDelegate` file. The SDK must be initialized before calling any of the other SDK methods using your project's publishable key.

```text
Roam.initialize("YOUR-SDK-KEY-GOES-HERE")
```

## Request Permissions <a id="Request-Permissions"></a>

Before you start location tracking, you need to get permission from the user for your application to access locations.

1. Import `CoreLocation` at the top of the `AppDelegate` file.

   ```text
   import CoreLocation
   ```

2. Make the below class declaration for Location Manager and add this line before the return statement in `application(_:didFinishLaunchingWithOptions:)` With this line, you ask users to allow the app to access location data both in the background and the foreground.

   ```text
   let locationManager = CLLocationManager()
   locationManager.requestLocation()
   ```

## Location Tracking <a id="Location-Tracking"></a>

### Start Tracking <a id="Start-Tracking"></a>

```swift
Roam.startSelfTracking(TrackingMode)
```

Use one of the tracking modes while you use the `Roam.startSelfTracking`  method.

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

```swift
Roam.stopSelfTracking()
```

## Tracking Modes

### Adaptive Tracking

Roam has three default tracking modes along with a custom version. They are different based on the frequency of location updates and battery consumption. The higher the frequency, the higher the battery consumption.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

```swift
//active tracking
Roam.startSelfTracking(RoamTrackingMode.active)
// balanced tracking
Roam.startSelfTracking(RoamTrackingMode.balanced)
// passive tracking
Roam.startSelfTracking(RoamTrackingMode.passive)
```

### **Distance Interval** Tracking <a id="Custom-Tracking-Modes"></a>

The SDK also provides a custom tracking mode which allows you to customize and build your own tracking mode as per your requirement.

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Distance Interval | Meters | 1m ~ 2500m |

**Distance between location updates example code:**

```swift
// Define a custom tracking method
let trackingMethod = RoamTrackingCustomMethods()

// Update the settings for the created method as per need
trackingMethod.activityType = .fitness
trackingMethod.pausesLocationUpdatesAutomatically = true
trackingMethod.showsBackgroundLocationIndicator = true
trackingMethod.useSignificant = false
trackingMethod.useRegionMonitoring = false
trackingMethod.useVisits = false
trackingMethod.accuracyFilter = 10
trackingMethod.desiredAccuracy = .kCLLocationAccuracyNearestTenMeters

// Update the distance intervel as per the use case in meters
trackingMethod.distanceFilter = 10

// Start the tracking with the above created custom tracking method
Roam.startSelfTracking(.custom, options: trackingMethod)
```

### **Time Interval** Tracking <a id="Custom-Tracking-Modes"></a>

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Time Interval | seconds | 1s - 10000s |

**Time between location updates example code:**

```swift
// Define a custom tracking method
let trackingMethod = RoamTrackingCustomMethods()

// Update the settings for the created method as per need
trackingMethod.activityType = .fitness
trackingMethod.pausesLocationUpdatesAutomatically = true
trackingMethod.showsBackgroundLocationIndicator = true
trackingMethod.useSignificant = false
trackingMethod.useRegionMonitoring = false
trackingMethod.useVisits = false
trackingMethod.accuracyFilter = 10
trackingMethod.desiredAccuracy = .kCLLocationAccuracyNearestTenMeters

// Update the time intervel as per the use case in seconds
trackingMethod.updateInterval = 10

// Start the tracking with the above created custom tracking method
Roam.startSelfTracking(.custom, options: trackingMethod)
```

## Location Listener

To listen to location updates create a class that implements RoamDeleagate and then call `Roam.delegate.`

Set your RoamDeleagate in a code path that will be initialized and executed in the background. For example, make your AppDelegate implement RoamDeleagate, not a ViewController. AppDelegate will be initialized in the background, whereas a ViewController may not be.

{% hint style="info" %}
Note: In self tracking, you can listen to only location, error and offline trips status data since the locations are not being sent to our servers for processing events.
{% endhint %}

{% tabs %}
{% tab title="Swift" %}
```swift
import UIKit
import Roam
import CoreLocation

@main
class AppDelegate: UIResponder, UIApplicationDelegate, RoamDelegate {
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        Roam.delegate = self
        Roam.initialize("YOUR-SDK-KEY-GOES-HERE")
        return true
    }
    func didUpdateLocation(_ location: RoamLocation) {
        // Do something with the user location
    }
```
{% endtab %}
{% endtabs %}

