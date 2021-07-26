---
description: >-
  GeoSpark provides an Cordova plugin that enables App developers to track
  location, geofence and trips.
---

# Quickstart

## Step 1: Install the plugin

In your project directory, install from npm, and then add it

```javascript
$ npm i cordova-plugin-geospark
$ cordova plugin add cordova-plugin-geospark
```

## Step 2: Install SDK

### iOS

#### **Configure Project**

To configure the location services, add following entries to the `Info.plist` file.

```text
pod 'GeoSpark' 
```

![](../.gitbook/assets/step-2img1%20%281%29.png)

Then, in your project settings, go to `Capabilities > Background Modes` and turn on background fetch, location updates, remote-notifications.

![](../.gitbook/assets/3%20%281%29.png)

Then, go to Build Settings in the project targets and change `Always Embed Swift Standard Libraries` to `Yes`.

## Step 3: Initialize SDK

### Android

```javascript
///In GeoSparkPlugin class include the code below.

@Override
public void initialize(CordovaInterface cordova, CordovaWebView webView) {
    super.initialize(cordova, webView);
        GeoSpark.initialize( this.cordova.getActivity().getApplication(), "PUBLISHABLEKEY");
} 
```

### iOS

Import GeoSpark into your AppDelegate file.

```swift
import GeoSpark
```

Initialize the SDK in your `AppDelegate` class before calling any other GeoSpark methods under this `application:didFinishLaunchingWithOptions:`

```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions 
launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  GeoSpark.intialize("PUBLISHABLEKEY")
  return true
}
```

## Step 4. Create a user

GeoSpark SDK needs a User ID object to identify the device.

```javascript
cordova.plugins.geospark.createUser("Description", function(success){
    // do something on success
}, function(error){
    // do something on error
});
```

##  Step 5: Get permissions

Get location permission from the App user on the device. Also check if the user has turned on location services for the device. In addition, get motion permission for iOS.

```javascript
// Call this method to check Location Permission for Android & iOS
cordova.plugins.geospark.checkLocationPermission(function(status){
    // do something with status
});
// Call this method to request Location Permission for Android & iOS
cordova.plugins.geospark.requestLocationPermission(function(status){
    // do something with status
});  
```

### iOS

```javascript
// Call this method to check Motion Permission for iOS
cordova.plugins.geospark.checkActivityPermission(function(status){
 // do something with status
});

// Call this method to request Motion Permission for iOS
cordova.plugins.geospark.requestActivityPermission(function(status){
 // do something with status
});
```

### Android

```javascript
// Call this method to check Location services for Android
cordova.plugins.geospark.checkLocationServices(function(status){
 // do something with status
});
// Call this method to request Location services for Android
cordova.plugins.geospark.requestLocationServices(function(status){

 // do something with status
});
```

## Step 6. Start Location tracking

To start tracking the location.

```javascript
cordova.plugins.geospark.startTracking();
```

