# Android

For reference check our sample app and ensure all the 10 TODO Steps:--[https://github.com/geosparks/geospark-android-migration-example ](https://github.com/geosparks/geospark-android-migration-example%20)

**Note**:\(After updating SDK from 2.2.5 to 3.0.4\)

**After initialising SDK :-**

Add the below code under the Application class onCreate\(\) method.

```java
public class MainApplication extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        GeoSpark.initialize(this,"YOUR-PUBLISHABLE-KEY");
        
        //Add the below code
        GeoSpark.setTrackingInAppState(GeoSparkTrackingMode.AppState.ALWAYS_ON);
        GeoSpark.locationPublisher(true);
        GeoSpark.offlineLocationTracking(true);
    }
}
```

## **Removed Context From Methods**

The following methods do not require context.

### **User**

```java
createUser("SET USER DESCRIPTION HERE", new GeoSparkCallback());

getUser(GEOSPARK USER ID", new GeoSparkCallback());

setDescription("SET USER DESCRIPTION HERE");

toggleEvents(geofence, trip, location, movingGeofence, new GeoSparkCallback());

getEventsStatus(new GeoSparkCallback());
```

### **Permissions**

```java
checkLocationPermission();

checkLocationServices();

checkBackgroundLocationPermission();
```

### **Tracking**

```java
isLocationTracking();

startTracking(TrackingMode);

stopTracking();

getCurrentLocation(accuracy, new GeoSparkLocationCallback());

updateCurrentLocation(accuracy);
```

### **Trips**

```java
startTrip(String message);

stopTrip(String message);

activeTrips(new GeoSparkActiveTripsCallback());
```

### **Utility**

```java
logout(new GeoSparkLogoutCallBack());

setDeviceToken("FCM DeviceToken");

getDeviceToken();

notificationOpenedHandler(getIntent());

disableBatteryOptimization();

isBatteryOptimizationEnabled();
```

## **User description**

We have removed the success and failure callback function.

```java
GeoSpark.setDescription( "User Description");
```

## **Toggle Event Flags**

To listen to events on the server-side, you should enable geofence, trip, location and movingGeofence events for the user using the method below.

```java
GeoSpark.toggleEvents(geofence, trip, location, movingGeofence, new GeoSparkCallback() {
    @Override
    public void onSuccess(GeoSparkUser geosparkUser) {
        // do something when toggle events success
        // access location events status with geosparkUser.getLocationEvents()
        // access geofence events status with geosparkUser.getGeofenceEvents()
        // access trips events status with geosparkUser.getTripsEvents()
        // get moving geofence event status with geosparkUser.getMovingGeofenceEvents()
    }
    @Override
    public void onFailure(GeoSparkError error ) {
        // do something when toggle events failure
    }
});
```

## **Start Location Tracking**

We have introduced new tracking modes in v3, with the following presets:

* Passive
* Active
* Reactive
* Custom

```java
/*You can now start tracking your users. GeoSpark has three default tracking 
modes.*/

GeoSpark.startTracking(GeoSparkTrackingMode.PASSIVE);
GeoSpark.startTracking(GeoSparkTrackingMode.REACTIVE);
GeoSpark.startTracking(GeoSparkTrackingMode.ACTIVE);

/* The SDK also provides a custom tracking mode that allows you 
to customize and build your own tracking mode.*/

GeoSparkTrackingMode trackingMode = new GeoSparkTrackingMode.Builder()
       .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
       .setStopDuration("DURATION IN SECONDS")
       .setDistanceFilter("DISTANCE IN METERS")
       .build();
GeoSpark.startTracking(trackingMode);
```

## **Location Listener**

To listen to your own or other user's location updates, create a class that extends GeoSparkReceiver.

```java
public class MyGeoSparkReceiver extends GeoSparkReceiver {
        @Override
        public void onLocationUpdated(Context context, String json){
            // receive own location updates here
            // do something with location data using json
        }
        @Override
        public void onLocationReceived(Context context, String json) {
            // receive other user's location updates here
            // do something with json
        }
        @Override
        public void onReceiveTripStatus(Context context, TripStatusListener listener) {
            // receive real time trip status here
            // do something with trip status data
        }

        @Override
        public void onEventReceived(Context context, String json) {
            //access event data here
        }

        @Override
        public void onError(Context context, GeoSparkError geosparkError) {
            //access error data here
        }
}
```

## **Current Location**

Get the current location of the user. You can set the accuracy between 10 to 100 meters \(default is 10\).

```java
GeoSpark.getCurrentLocation(DesiredAccuracy, Accuracy, new GeoSparkLocationCallback()
  {
	    @Override
		public void location(Location location) {
        // do something with location data using location
        }

        @Override
        public void onFailure(GeoSparkError geoSparkError) {
        //access error data here
        }
});
```



| Parameter | Description |
| :--- | :--- |
| DesiredAccuracy | GeoSparkTrackingMode.DesiredAccuracy.HIGH \(or\) GeoSparkTrackingMode.DesiredAccuracy.MEDIUM \(or\) GeoSparkTrackingMode.DesiredAccuracy.LOW |

## **Update Current Location**

Using the `updateCurrentLocation` method, you can update the user's current location, you can set the accuracy between 10 to 100 meters \(default is 10\).

```java
GeoSpark.updateCurrentLocation(DesiredAccuracy, accuracy);
```

| Parameter | Description |
| :--- | :--- |
| DesiredAccuracy | GeoSparkTrackingMode.DesiredAccuracy.HIGH \(or\) GeoSparkTrackingMode.DesiredAccuracy.MEDIUM \(or\) GeoSparkTrackingMode.DesiredAccuracy.LOW |

## **ActiveTrips**

Get **online** and **offline** active trips using the `activeTrips()` method.

```java
GeoSpark.activeTrips(boolean, new GeoSparkActiveTripsCallback() {
        @Override
        public void onSuccess(GeoSparkTrip geoSparkTrip) {
       	    //access geospark trips geoSparkTrip.getActiveTrips();
		}

		@Override
		public void onFailure(GeoSparkError geoSparkError) {
			//access error data here
		}
});
```

| Parameter | Description |
| :--- | :--- |
| Boolean | **true** for offline trips **false** for online trips |

## **StopTrip**

Renamed from endTrip to stopTrip.

```java
GeoSpark.stopTrip("GEOSPARK-TRIP-ID", new GeoSparkTripCallback() {
		@Override
		public void onSuccess(String message) {
      
		}
		@Override
		public void onFailure(GeoSparkError geosparkError) {
			//access error data here
		}
});
```

