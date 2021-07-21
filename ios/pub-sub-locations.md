# Pub/Sub Locations

## Creating Users <a id="Creating-Users"></a>

Once the SDK is initialised, you need to _create_ or _get a user_ to start the tracking and use other methods. Every user created will have a unique GeoSpark identifier which will be used to login and access developer APIs. We call this GeoSpark `user_Id`. 

```swift
GeoSpark.createUser("SET-USER-DESCRIPTION-HERE") { (geosparkUser, error) in
            //   access geospark user id with geosparkUser?.userId
            //   access geospark user description with geosparkUser?.userDescription
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
  }
```

The option _user description_ can be used to update user information such as name, address or add an existing user ID. Make sure the information is encrypted if you are planning to save personal information like an email or phone number. 

You can always set or update user descriptions later using the below code.

```swift
GeoSpark.setDescription("SET-USER-DESCRIPTION-HERE")  
```

### Get User

If you already have a GeoSpark `user_ID` which you would like to reuse instead of creating a new user, use the code below to get a user session.

```swift
GeoSpark.getUser("GEOSPARK USER ID") { (geosparkUser, error) in
            //   access geospark user id with geosparkUser?.userId
            //   access geospark user description with geosparkUser?.userDescription
            //   access geospark user description with error?.code
            //   access geospark user description with error?.message
        }
```

## Location Tracking <a id="Location-Tracking"></a>

To publish and subscribe to location data, `startSelfTracking` methods has to be changed to `startTracking`

### Start Tracking <a id="Start-Tracking"></a>

```swift
GeoSpark.startTracking(TrackingMode)
```

Use the tracking modes while you use the startTracking method `GeoSpark.startTracking`

#### Tracking Modes <a id="Tracking-Modes"></a>

You can now start tracking your users. GeoSpark has three default tracking modes along with a custom version. They are different based on the frequency of location updates and battery consumption. The higher the frequency, the higher the battery consumption.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

```swift
//active tracking
GeoSpark.startTracking(GeoSparkTrackingMode.active);
// balanced tracking
GeoSpark.startTracking(GeoSparkTrackingMode.balanced);
// passive tracking
GeoSpark.startTracking(GeoSparkTrackingMode.passive);
```

### Custom Tracking Modes <a id="Custom-Tracking-Modes"></a>

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
GeoSpark.startTracking(.custom, options: trackingMethod)
```

**Time between location updates example code:**

```swift
// define a custom tracking method
let trackingMethod = GeoSparkTrackingMethods.custom
trackingMethod.allowBackgroundLocationUpdates = true
trackingMethod.desiredAccuracy = kCLLocationAccuracyBest
// Update interval in seconds
trackingMethod.updateInterval = 10
GeoSpark.startTracking(.custom, options: trackingMethod)
```

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

```swift
GeoSpark.stopTracking()
```

## Publish Messages <a id="Publish-Messages"></a>

It will publish location data and these data will be sent to Roam servers for further processing and data will be saved in our database servers.

```swift
var locationData = GeoSparkPublish()
GeoSpark.publishSave(locationData)
```

To stop publishing the location data to other clients.

```swift
GeoSpark.stopPublishing();
```

## Subscribe Messages

Now that you have enabled the location listener, use the below method to subscribe to your own or other user's location updates and events. 

### **Subscribe**

```swift
GeoSpark.subscribe(TYPE, "USER-ID");
```

### **UnSubscribe**

```swift
GeoSpark.unSubscribe(TYPE, "USER-ID");
```

| **Type** | **Description** |
| :--- | :--- |
| GeoSparkSubscribe.Events | Subscribe to your own events. |
| GeoSparkSubscribe.Location | Subscribe to your own location \(or\) other user's location updates. |
| GeoSparkSubscribe.Both | Subscribe to your own events and location \(or\) other user's location updates. |

## Location Listener

In order to listen to location updates locally, you can follow the below steps for pub/sub tracking.

{% page-ref page="sdk-methods-1/listeners-and-events.md" %}

