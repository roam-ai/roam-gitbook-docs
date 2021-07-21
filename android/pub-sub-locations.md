# Pub/Sub Locations

## Creating Users <a id="Creating-Users"></a>

Once the SDK is initialized, we need to _create_ or _get a user_ to start the tracking and use other methods. Every user created will have a unique Roam identifier which will be used later to login and access developer APIs. We can call it as Roam userId.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.createUser("SET-USER-DESCRIPTION-HERE", object : RoamCallback {
      override fun onSuccess(roamUser: RoamUser) {
        // Access Roam user data below
        // roamUser.getUserId();
        // roamUser.getDescription();
        // roamUser.getEventListenerStatus();
        // roamUser.getLocationListenerStatus();
        // roamUser.getLocationEvents();
        // roamUser.getGeofenceEvents();
        // roamUser.getMovingGeofenceEvents();
        // roamUser.getTripsEvents();
      }

      override fun onFailure(roamError: RoamError) {
        // Access error code & message below
        // roamError.getCode()
        // roamError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.createUser("YOUR-USER-DESCRIPTION-GOES-HERE", new RoamCallback() {
            @Override
            public void onSuccess(RoamUser roamUser) {
                // Access Roam user data below
                // roamUser.getUserId();
                // roamUser.getDescription();
                // roamUser.getEventListenerStatus();
                // roamUser.getLocationListenerStatus();
                // roamUser.getLocationEvents();
                // roamUser.getGeofenceEvents();
                // roamUser.getMovingGeofenceEvents();
                // roamUser.getTripsEvents();
            }

            @Override
            public void onFailure(RoamError roamError) {
                // Access error code & message below
                // roamError.getCode();
                // roamError.getMessage();
            }
        });
```
{% endtab %}
{% endtabs %}

The option _user description_ can be used to update your user information such as name, address or add an existing user ID. Make sure the information is encrypted if you are planning to save personal user information like email or phone number.

You can always set or update user descriptions later using the below code.

{% tabs %}
{% tab title="Kotlin" %}
```java
Roam.setDescription("SET-USER-DESCRIPTION-HERE")
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.setDescription("SET-USER-DESCRIPTION-HERE");
```
{% endtab %}
{% endtabs %}

### Get User

If you already have a Roam userID which you would like to reuse instead of creating a new user, use the below to get user session.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getUser("ROAM-USER-ID", object : RoamCallback {
      override fun onSuccess(roamUser: RoamUser) {
        // Access Roam user data below
        // roamUser.getUserId();
        // roamUser.getDescription();
        // roamUser.getEventListenerStatus();
        // roamUser.getLocationListenerStatus();
        // roamUser.getLocationEvents();
        // roamUser.getGeofenceEvents();
        // roamUser.getMovingGeofenceEvents();
        // roamUser.getTripsEvents();
      }

      override fun onFailure(roamError: RoamError) {
        // Access error code & message below
        // roamError.getCode()
        // roamError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getUser("YOUR-ROAM-USER-ID", new RoamCallback() {
            @Override
            public void onSuccess(RoamUser roamUser) {
                // Access Roam user data below
                // roamUser.getUserId();
                // roamUser.getDescription();
                // roamUser.getEventListenerStatus();
                // roamUser.getLocationListenerStatus();
                // roamUser.getLocationEvents();
                // roamUser.getGeofenceEvents();
                // roamUser.getMovingGeofenceEvents();
                // roamUser.getTripsEvents();
            }

            @Override
            public void onFailure(RoamError roamError) {
                // Access error code & message below
                // roamError.getCode();
                // roamError.getMessage();
            }
        });
```
{% endtab %}
{% endtabs %}

## Location Tracking <a id="Location-Tracking"></a>

To publish and subscribe to location data, `startSelfTracking` methods has to be changed to `startTracking`

### Start Tracking <a id="Start-Tracking"></a>

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.startTracking(TrackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.startTracking(TrackingMode);
```
{% endtab %}
{% endtabs %}

Use the tracking modes while you use the `startTracking` method `Roam.startTracking`

### Tracking Modes

Roam has three default tracking modes along with a custom version. They differ based on the frequency of location updates and battery consumption. The higher the frequency, the higher is the battery consumption. You must use [foreground service](https://developer.android.com/about/versions/oreo/background-location-limits) for continuous tracking.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// active tracking
Roam.startTracking(RoamTrackingMode.ACTIVE)
// balanced tracking
Roam.startTracking(RoamTrackingMode.BALANCED)
// passive tracking
Roam.startTracking(RoamTrackingMode.PASSIVE)
```
{% endtab %}

{% tab title="Java" %}
```java
// active tracking
Roam.startTracking(RoamTrackingMode.ACTIVE);
// balanced tracking
Roam.startTracking(RoamTrackingMode.BALANCED);
// passive tracking
Roam.startTracking(RoamTrackingMode.PASSIVE);
```
{% endtab %}
{% endtabs %}

### Custom Tracking Modes

The SDK also provides a custom tracking mode that allows you to customize and build your own tracking modes.

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Distance Interval | Meters | 1m ~ 2500m |
| Time Interval | Seconds | 10s ~ 10800s |

**Distance between location updates example code:**

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// Define a custom tracking method with desired distance interval, stop duration and accuracy
val trackingMode = RoamTrackingMode.Builder(<DISTANCE-FILTER-IN-METERS>, <STOP-INTERVAL-IN-SECONDS>)
                  .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                  .build()
// Start the tracking with the above created custom tracking method
Roam.startTracking(trackingMode);
```
{% endtab %}

{% tab title="Java" %}
```java
// Define a custom tracking method with desired distance interval, stop duration and accuracy
RoamTrackingMode trackingMode = new RoamTrackingMode.Builder(<DISTANCE-FILTER-IN-METERS>, <STOP-INTERVAL-IN-SECONDS>)
                .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                .build();
// Start the tracking with the above created custom tracking method
Roam.startTracking(trackingMode);
```
{% endtab %}
{% endtabs %}

**Time between location updates example code:**

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// Define a custom tracking method with desired time interval and accuracy
val trackingMode = RoamTrackingMode.Builder(<TIME-INTERVAL-IN-SECONDS>)
                  .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                  .build()
// Start the tracking with the above created custom tracking method
Roam.startTracking(trackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
// Define a custom tracking method with desired time interval and accuracy
RoamTrackingMode trackingMode = new RoamTrackingMode.Builder(<TIME-INTERVAL-IN-SECONDS>)
                .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                .build();
// Start the tracking with the above created custom tracking method
Roam.startTracking(trackingMode);
```
{% endtab %}
{% endtabs %}

You may see a delay if the user's device is in low power mode or has connectivity issues.

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.stopTracking()
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.stopTracking();
```
{% endtab %}
{% endtabs %}

## Publish Locations <a id="Publish-Messages"></a>

It will publish location data and these data will be sent to Roam servers for further processing and data will be saved in our database servers.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
val locationData = RoamPublish.Builder().build()
Roam.publishAndSave(locationData)
```
{% endtab %}

{% tab title="Java" %}
```java
RoamPublish locationData = new RoamPublish.Builder().build();
Roam.publishAndSave(locationData);
```
{% endtab %}
{% endtabs %}

To stop publishing locations.

{% tabs %}
{% tab title="Kotlin" %}
```text
Roam.stopPublishing()
```
{% endtab %}

{% tab title="Java" %}
```
Roam.stopPublishing();
```
{% endtab %}
{% endtabs %}

## Subscribe Messages

Now that you have enabled the location listener, use the below method to subscribe to your own or other user's location updates and events. 

### **Subscribe**

{% tabs %}
{% tab title="Kotlin" %}
```javascript
Roam.subscribe(TYPE, "ROAM-USER-ID");
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.subscribe(TYPE, "USER-ID");
```
{% endtab %}
{% endtabs %}

### **UnSubscribe**

{% tabs %}
{% tab title="Kotlin" %}
```javascript
Roam.unSubscribe(TYPE, "ROAM-USER-ID")
```
{% endtab %}

{% tab title="Java" %}
```
Roam.unSubscribe(TYPE, "ROAM-USER-ID");
```
{% endtab %}
{% endtabs %}

| **Type** | **Description** |
| :--- | :--- |
| Roam.Subscribe.EVENTS | Subscribe to your own events.   |
| Roam.Subscribe.LOCATION | Subscribe to your own location \(or\) other user's location updates. |
| Roam.Subscribe.BOTH | Subscribe to your own events and location \(or\) other user's location updates. |

## Location Listener

Before adding listerners for locations and other data, we need to toggle the listener flags for the user in order to get the data.

To do that, you need to set the location and event listener to `true` using the below method. By default, the status will set to `false` and needs to be set to `true` in order to stream the location and events updates to the same device or other devices.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.toggleListener(locations, events, object : RoamCallback {
    override fun onSuccess(roamUser: RoamUser) {
        // do something when toggle listener success
        // access locations listener status with roamUser.getLocationListenerStatus()
        // access events listener status with roamUser.getEventListenerStatus()
    }

    override fun onFailure(roamError: RoamError) {
        // do something when toggle listener failure
    }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.toggleListener(true, true, new RoamCallback() {
            @Override
            public void onSuccess(RoamUser roamUser) {
	              // Access Roam user data below
                // roamUser.getUserId();
                // roamUser.getDescription();
                // roamUser.getEventListenerStatus();
                // roamUser.getLocationListenerStatus();
                // roamUser.getLocationEvents();
                // roamUser.getGeofenceEvents();
                // roamUser.getMovingGeofenceEvents();
                // roamUser.getTripsEvents();
            }

            @Override
            public void onFailure(RoamError roamError) {
      	        // Access error code & message below
                // roamError.getCode();
                // roamError.getMessage();
            }
        });
```
{% endtab %}
{% endtabs %}

You can also get the current status of listeners with the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getListenerStatus(object : RoamCallback {
    override fun onSuccess(roamUser: RoamUser) {
        // do something when get listener status success
        // get location listener status with roamUser.getLocationListenerStatus
        // get events listener status with roamUser.getEventListenerStatus
    }
    override fun onFailure(roamError: RoamError) {
        // do something when get listener status failure
    }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getListenerStatus(new RoamCallback() {
            @Override
            public void onSuccess(RoamUser roamUser) {
	              // Access Roam user data below
                // roamUser.getUserId();
                // roamUser.getDescription();
                // roamUser.getEventListenerStatus();
                // roamUser.getLocationListenerStatus();
                // roamUser.getLocationEvents();
                // roamUser.getGeofenceEvents();
                // roamUser.getMovingGeofenceEvents();
                // roamUser.getTripsEvents();
            }

            @Override
            public void onFailure(RoamError roamError) {
      	        // Access error code & message below
                // roamError.getCode();
                // roamError.getMessage();
            }
      });
```
{% endtab %}
{% endtabs %}

To listen to events on the server-side, you should enable events for the user using the method below.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.toggleEvents(geofence, trip, location, movingGeofence, object : RoamCallback {
    override fun onSuccess(roamUser: RoamUser) {
        // do something when toggle events success
        // access location events status with roamUser.getLocationEvents()
        // access geofence events status with roamUser.getGeofenceEvents()
        // access trips events status with roamUser.getTripsEvents()
        // get moving geofence event status with roamUser.getMovingGeofenceEvents()
    }

    override fun onFailure(error: roamError) {
        // do something when toggle events failure
    }

```
{% endtab %}

{% tab title="Java" %}
```java
Roam.toggleEvents(true, true, true, true, new RoamCallback() {
            @Override
            public void onSuccess(RoamUser roamUser) {
	              // Access Roam user data below
                // roamUser.getUserId();
                // roamUser.getDescription();
                // roamUser.getEventListenerStatus();
                // roamUser.getLocationListenerStatus();
                // roamUser.getLocationEvents();
                // roamUser.getGeofenceEvents();
                // roamUser.getMovingGeofenceEvents();
                // roamUser.getTripsEvents();
            }

            @Override
            public void onFailure(RoamError roamError) {
      	        // Access error code & message below
                // roamError.getCode();
                // roamError.getMessage();
            }
        });
```
{% endtab %}
{% endtabs %}

Now, to listen to location updates and events, create a class that extends RoamReceiver. Then register the receiver by adding a receiver element to the application element in your manifest.

```markup
<application>
        ...
     <receiver android:name=".LocationReceiver"
                    android:enabled="true"
                    android:exported="false">
         <intent-filter>
         <action android:name="com.roam.android.RECEIVED"/>
         </intent-filter>
     </receiver>
         ...
</application>

```

Then add the code to the receiver.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
public class LocationReceiver : RoamReceiver() {
    override fun onLocationUpdated(context: Context, roamLocation: RoamLocation) {
        // receive own location updates here
        // do something with location data using location
    }

    override fun onLocationReceived(context: Context, roamLocationReceived: RoamLocationReceived) {
        // receive other user's location updates here
        // do something with location
    }
    
    override fun onEventReceived(context: Context, roamEvent: RoamEvent) {
        //access event data here
    }

    override fun onReceiveTripStatus(context: Context, listener: TripStatusListener) {
        // receive real time trip status here
        // do something with trip status data
    }

    override fun onError(context: Context, roamError: RoamError) {
        //access error data here
    }
}
```
{% endtab %}

{% tab title="Java" %}
```java
public class LocationReceiver extends RoamReceiver {

    @Override
    public void onLocationUpdated(Context context, RoamLocation roamLocation) {
        // receive own location updates here
		    // do something with location data using location
    }

    @Override
    public void onLocationReceived(Context context, RoamLocationReceived roamLocationReceived) {
        // receive other user's location updates here
    		// do something with location
    }

    @Override
    public void onEventReceived(Context context, RoamEvent roamEvent) {
    		//access event data here
    }

    @Override
    public void onReceiveTripStatus(Context context, TripStatusListener listener) { 
        // receive real time trip status here
    		// do something with trip status data
    }

    @Override
    public void onError(Context context, RoamError roamError) {
         //access error data here
    }
}
```
{% endtab %}
{% endtabs %}

