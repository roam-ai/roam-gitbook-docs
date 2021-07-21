# Pub/Sub Locations

## Creating Users <a id="Creating-Users"></a>

Once the SDK is initialised, you need to _create_ or _get a user_ to start the tracking and use other methods. Every user created will have a unique Roam identifier which will be used to login and access developer APIs. We call this Roam `user_Id`. 

```swift
Roam.createUser("YOUR-USER-DESCRIPTION-GOES-HERE") {(RoamUser, Error) in
            // Access Roam user data below
            // RoamUser?.userId
            // RoamUser?.description
            // RoamUser?.locationListener
            // RoamUser?.eventsListener
            // RoamUser?.locationEvents
            // RoamUser?.geofenceEvents
            // RoamUser?.tripsEvents
            // RoamUser?.nearbyEvents
            
            // Access error code & message below
            // Error?.code
            // Error?.message
        }
```

The option _user description_ can be used to update user information such as name, address or add an existing user ID. Make sure the information is encrypted if you are planning to save personal information like an email or phone number. 

You can always set or update user descriptions later using the below code.

```swift
Roam.setDescription("SET-USER-DESCRIPTION-HERE")
```

### Get User

If you already have a Roam `user_ID` which you would like to reuse instead of creating a new user, use the code below to get a user session.

```swift
Roam.getUser("YOUR-ROAM-USER-ID") {(RoamUser, Error) in
            // Access Roam user data below
            // RoamUser?.userId
            // RoamUser?.description
            // RoamUser?.locationListener
            // RoamUser?.eventsListener
            // RoamUser?.locationEvents
            // RoamUser?.geofenceEvents
            // RoamUser?.tripsEvents
            // RoamUser?.nearbyEvents
            
            // Access error code & message below
            // Error?.code
            // Error?.message
        }
```

## Location Tracking <a id="Location-Tracking"></a>

### Start Tracking <a id="Start-Tracking"></a>

{% hint style="warning" %}
To publish and subscribe to location data, `startSelfTracking` methods has to be changed to `startTracking`
{% endhint %}

```swift
Roam.startTracking(TrackingMode)
```

Use the tracking modes while you use the startTracking method `Roam.startTracking`

#### Tracking Modes <a id="Tracking-Modes"></a>

You can now start tracking your users. Roam has three default tracking modes along with a custom version. They are different based on the frequency of location updates and battery consumption. The higher the frequency, the higher the battery consumption.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

```swift
//active tracking
Roam.startTracking(RoamTrackingMode.active)
// balanced tracking
Roam.startTracking(RoamTrackingMode.balanced)
// passive tracking
Roam.startTracking(RoamTrackingMode.passive)
```

### Custom Tracking Modes <a id="Custom-Tracking-Modes"></a>

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
Roam.startTracking(.custom, options: trackingMethod)
```

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
Roam.startTracking(.custom, options: trackingMethod)

```

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

```swift
Roam.stopTracking()
```

## Publish Messages <a id="Publish-Messages"></a>

It will publish location data and these data will be sent to Roam servers for further processing and data will be saved in our database servers.

```swift
let locationData = RoamPublish()
Roam.publishSave(locationData)
```

To stop publishing the location data to other clients.

```swift
Roam.stopPublishing();
```

## Subscribe Messages

Now that you have enabled the location listener, use the below method to subscribe to your own or other user's location updates and events. 

### **Subscribe**

```swift
Roam.subscribe(TYPE, "ROAM-USER-ID");
```

### **UnSubscribe**

```swift
Roam.unSubscribe(TYPE, "ROAM-USER-ID");
```

| **Type** | **Description** |
| :--- | :--- |
| RoamSubscribe.Events | Subscribe to your own events. |
| RoamSubscribe.Location | Subscribe to your own location \(or\) other user's location updates. |
| RoamSubscribe.Both | Subscribe to your own events and location \(or\) other user's location updates. |

## Location Listener

{% hint style="success" %}
Listeners are needed to consume the location or event data from the SDK iteself. In order to enable listerners, the below setps are needed.
{% endhint %}

Before adding listerners for locations and other data, we need to toggle the listener flags for the user in order to get the data.

To do that, you need to toggle the location and event listener to `true`. By default, the status will set to `false` and needs to be set to `true` in order to stream the location and events updates to the same device or other devices.

```swift
Roam.toggleListener(Events: true, Locations: true) {(RoamUser, Error) in
            // Access Roam user data below
            // RoamUser?.userId
            // RoamUser?.description
            // RoamUser?.locationListener
            // RoamUser?.eventsListener
            // RoamUser?.locationEvents
            // RoamUser?.geofenceEvents
            // RoamUser?.tripsEvents
            // RoamUser?.nearbyEvents
            
            // Access error code & message below
            // Error?.code
            // Error?.message
        }
```

You can also get the current status of listeners with the below method.

```swift
Roam.getListenerStatus() {(RoamUser, Error) in
            // Access Roam user data below
            // RoamUser?.userId
            // RoamUser?.description
            // RoamUser?.locationListener
            // RoamUser?.eventsListener
            // RoamUser?.locationEvents
            // RoamUser?.geofenceEvents
            // RoamUser?.tripsEvents
            // RoamUser?.nearbyEvents
            
            // Access error code & message below
            // Error?.code
            // Error?.message
        }
```

To listen to events on the server-side, you should enable events for the user using the below method.

```swift
Roam.toggleEvents(Geofence: true, Location: true, Trips: true, MovingGeofence: true { (RoamUser, Error) in
            // Access Roam user data below
            // RoamUser?.userId
            // RoamUser?.description
            // RoamUser?.locationListener
            // RoamUser?.eventsListener
            // RoamUser?.locationEvents
            // RoamUser?.geofenceEvents
            // RoamUser?.tripsEvents
            // RoamUser?.nearbyEvents
            
            // Access error code & message below
            // Error?.code
            // Error?.message
 }
```

Once the listener toggles are set to true, to listen to location updates create a class that implements RoamDelegate and then call Roam.delegate.

Set your `RoamDelegate` in a code path that will be initialized and executed in the background. For example, make your AppDelegate implement RoamDelegate, not a ViewController. AppDelegate will be initialized in the background, whereas a ViewController may not be.

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
    func didReceiveEvents(_ events: RoamEvents) {
        // Do smoething with user events
    }
    func didReceiveUserLocation(_ location: RoamLocationReceived) {
        // Do something with location of other users' subscribed location
    }
    func didReceiveTripStatus(_ tripStatus: TripStatusListener) {
    //do something with trip status data
    }
}   
```

