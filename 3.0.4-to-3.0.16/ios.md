# iOS

## **Start Location Tracking**

We have introduced new tracking modes in v3, with the following presets:

* Passive
* Active
* Reactive
* Custom

```swift
/*You can now start tracking your users. GeoSpark has three default tracking 
modes.*/

GeoSpark.startTracking(GeoSparkTrackingMode.passive)
GeoSpark.startTracking(GeoSparkTrackingMode.active)
GeoSpark.startTracking(GeoSparkTrackingMode.reactive)

/* The SDK also provides a custom tracking mode that allows you 
to customize and build your own tracking mode.*/

let trackingMethod = GeoSparkTrackingMethods.custom
trackingMethod.activityType = .fitness
trackingMethod.distanceFilter = 10
trackingMethod.desiredAccuracy = .kCLLocationAccuracyBest
GeoSpark.startTracking(.custom, options: trackingMethod)
```

## **Active Trips**

Get **online** and **offline** active trips, using `activeTrips()` method.

```swift
// Online Trip
GeoSpark.activeTrips(false) { (trips, error) in           
}
// Offline Trip
GeoSpark.activeTrips(true) { (trips, error) in           
}
```

## **Stop Trip**

We have renamed endTrip to stopTrip.

```swift
 GeoSpark.stopTrip("TRIPID") { (status, error) in       
 }
```

## Toggle Event Flags

To listen to events on the server-side, you need to enable geofence, trip, location and movingGeofence events for the user using the method below.

```swift
GeoSpark.toggleEvents(Geofence: BOOL, Trip: BOOL, Location: BOOL, MovingGeofence: BOOL) { (user, error) in
}
```

