---
description: >-
  Listeners are needed to consume the location or event data from the SDK
  iteself. In order to enable listerners, the below setps are needed.
---

# Listeners and Events

## Self Tracking

To listen to location updates create a class that implements GeoSparkDelegate and then call `GeoSpark.delegate.`

Set yourGeoSparkDelegate in a code path that will be initialized and executed in the background. For example, make your AppDelegate implement GeoSparkDelegate, not a ViewController. AppDelegate will be initialized in the background, whereas a ViewController may not be.

{% hint style="info" %}
Note: In self tracking, you can listen to only location, error and offline trips status data since the locations are not being sent to our servers for processing events.
{% endhint %}

{% tabs %}
{% tab title="Swift" %}
```swift
class AppDelegate: UIResponder,UIApplicationDelegate,GeoSparkDelegate{
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey:
Any]?) -> Bool {
        GeoSpark.initialize("YOUR SDK KEY GOES HERE")
        GeoSpark.delegate = self
        return true
    }
func didUpdateLocation(_ geospark: GeoSparkLocation) {
    //receive own location updates here
    //do something with location data using location
    }  
func didReceiveTripStatus(_ tripStatus: TripStatusListener) {
    //do something with trip status data
    }  
}
```
{% endtab %}

{% tab title="Objective-C" %}
```swift
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    // Override point for customization after application launch.
    [GeoSpark setDelegate:self];
    return YES;
}
- (void)didUpdateLocation:(GeoSparkLocation *)location{
    //receive own location updates here
    //do something with location data using location
}
- (void)didReceiveTripStatus:(TripStatusListener *)tripStatus{
    //do something with trip status data
}
```
{% endtab %}
{% endtabs %}

## Pub/Sub Tracking

Before adding listerners for locations and other data, we need to toggle the listener flags for the user in order to get the data.

To do that, you need to toggle the location and event listener to `true`. By default, the status will set to `false` and needs to be set to `true` in order to stream the location and events updates to the same device or other devices.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.toggleListener(Events: true, Locations: true) { (geosparkUser, error) in
      // access location lister status with geosparkUser?.locationListener
      // access events lister status geosparkUser?.eventListener
      // access geospark error code with error?.code
      // access geospark error message with error?.message 
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```
[GeoSpark toggleListenerWithHandler:^(GeoSparkUser * user , GeoSparkError * error) {
      // access location lister status with geosparkUser?.locationListener
      // access events lister status geosparkUser?.eventListener
      // access geospark error code with error?.code
      // access geospark error message with error?.message    
}];
```
{% endtab %}
{% endtabs %}

You can also get the current status of listeners with the below method.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getListenerStatus({ (geosparkUser, error) in
      // access location lister status with geosparkUser?.locationListener
      // access events lister status geosparkUser?.eventListener
      // access geospark error code with error?.code
      // access geospark error message with error?.message
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark getListenerStatusWithHandler:^(GeoSparkUser * user , GeoSparkError * error) {
      // access location lister status with geosparkUser?.locationListener
      // access events lister status geosparkUser?.eventListener
      // access geospark error code with error?.code
      // access geospark error message with error?.message    
}];
```
{% endtab %}
{% endtabs %}

To listen to events on the server-side, you should enable events for the user using the below method.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.toggleEvents(Geofence: true, Location: true, Trips: true, MovingGeofence: true { (GeoSparkUser, error) in
      // access location events status with geosparkUser?.locationEvents
      // access geofence events status with geosparkUser?.geofenceEvents
      // access trips events status with geosparkUser?.tripsEvents
      // access moving geofence events status with geosparkUser?.movingGeofenceEvents
      // access geospark error code with error?.code
      // access geospark error message with error?.message 
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```
[GeoSpark toggleEventsWithHandler:^(GeoSparkUser * user , GeoSparkError * error) {
      // access location events status with geosparkUser?.locationEvents
      // access geofence events status with geosparkUser?.geofenceEvents
      // access trips events status with geosparkUser?.tripsEvents
      // access moving geofence events status with geosparkUser?.movingGeofenceEvents
      // access geospark error code with error?.code
      // access geospark error message with error?.message    
}];
```
{% endtab %}
{% endtabs %}

To listen to location updates create a class that implements GeoSparkDelegate and then call `GeoSpark.delegate.`

Set yourGeoSparkDelegate in a code path that will be initialized and executed in the background. For example, make your AppDelegate implement GeoSparkDelegate, not a ViewController. AppDelegate will be initialized in the background, whereas a ViewController may not be

{% tabs %}
{% tab title="Swift" %}
```swift
class AppDelegate: UIResponder,UIApplicationDelegate,GeoSparkDelegate{
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey:
Any]?) -> Bool {
        GeoSpark.initialize("YOUR SDK KEY GOES HERE")
        GeoSpark.delegate = self
        return true
    }
func didUpdateLocation(_ geospark: GeoSparkLocation) {
    //receive own location updates here
    //do something with location data using location
    }
func didReceiveUserLocation(_ location:GeoSparkLocationReceived) {
    //receive other user's location updates here
    } 
func didReceiveEvent(_ events:GeoSparkEvents) {
    //receive  user's events updates here
    }
func didReceiveTripStatus(_ tripStatus: TripStatusListener) {
    //do something with trip status data
    }   
}
```
{% endtab %}

{% tab title="Objective-C" %}
```swift
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    // Override point for customization after application launch.
    [GeoSpark setDelegate:self];
    return YES;
}
- (void)didUpdateLocation:(GeoSparkLocation *)location{
    //receive own location updates here
    //do something with location data using location
}
- (void)didReceiveEvents:(GeoSparkEvents *)events{
    //receive  user's events updates here
}
- (void)didReceiveUserLocation:(GeoSparkLocationReceived *)location{
    //receive other user's location updates here
}
- (void)didReceiveTripStatus:(TripStatusListener *)tripStatus{
    //do something with trip status data
}
```
{% endtab %}
{% endtabs %}



