# iOS

## Modified

We have modified below methods for Start Tracking to track locations locally and not publish to servers.

```text
GeoSpark.startTracking(TrackingMode)
```

## Added

We have added below methods to enable location publish to our servers for processing events for geofence, location, trips and moving geofence. If the location is not published, the location data will remain in the device itself for its own consumption and will not be sent to our servers.

### Publish Messages

It will publish location data and these data will be sent to Roam servers for further processing and data will be saved in our database servers.

```swift
var locationData = GeoSparkPublish()
GeoSpark.publishSave(locationData)
```

To stop publishing the location data to other clients.

```swift
GeoSpark.stopPublishing();
```

### Subscribe Messages

Now that you have enabled the location listener, use the below method to subscribe to your own or other user's location updates and events. 

#### **Subscribe**

```swift
GeoSpark.subscribe(TYPE, "USER-ID");
```

#### **Unsubscribe**

```swift
GeoSpark.unSubscribe(TYPE, "USER-ID");
```

| **Type** | **Description** |
| :--- | :--- |
| GeoSparkSubscribe.Events | Subscribe to your own events. |
| GeoSparkSubscribe.Location | Subscribe to your own location \(or\) other user's location updates. |
| GeoSparkSubscribe.Both | Subscribe to your own events and location \(or\) other user's location updates. |

