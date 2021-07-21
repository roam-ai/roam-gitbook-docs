---
description: >-
  Listeners are needed to consume the location or event data from the SDK
  iteself. In order to enable listerners, the below setps are needed.
---

# Listeners and Events

## Self Tracking

To listen to location updates create a class that extends GeoSparkReceiver. Then register the receiver by adding a receiver element to the application element in your manifest.

{% hint style="info" %}
Note: In self tracking, you can listen to only location, error and offline trips status data since the locations are not being sent to our servers for processing events.
{% endhint %}

```markup
<application>
        ...
     <receiver android:name=".MyGeoSparkReceiver"
                    android:enabled="true"
                    android:exported="false">
         <intent-filter>
         <action android:name="com.geospark.android.RECEIVED"/>
         </intent-filter>
     </receiver>
         ...
</application>

```

Then add the code to the receiver.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
public class MyGeoSparkReceiver : GeoSparkReceiver() {
    override fun onLocationUpdated(context: Context, geosparkLocation: GeoSparkLocation) {
        // receive own location updates here
        // do something with location data using location
    }

    override fun onReceiveTripStatus(context: Context, listener: TripStatusListener) {
        // receive real time trip status here
        // do something with trip status data
    }

    override fun onError(context: Context, geosparkError: GeoSparkError) {
        //access error data here
    }
}
```
{% endtab %}

{% tab title="Java" %}
```java
public class MyGeoSparkReceiver extends GeoSparkReceiver {

    @Override
    public void onLocationUpdated(Context context, GeoSparkLocation geosparkLocation) {
        // receive own location updates here
		// do something with location data using location
    }

    @Override
    public void onReceiveTripStatus(Context context, TripStatusListener listener) { 
        // receive real time trip status here
		// do something with trip status data
    }

    @Override
    public void onError(Context context, GeoSparkError geosparkError) {
         //access error data here
    }
}
```
{% endtab %}
{% endtabs %}

## Pub/Sub Tracking

Before adding listerners for locations and other data, we need to toggle the listener flags for the user in order to get the data.

To do that, you need to set the location and event listener to `true` using the below method. By default, the status will set to `false` and needs to be set to `true` in order to stream the location and events updates to the same device or other devices.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.toggleListener(locations, events, object : GeoSparkCallback {
    override fun onSuccess(geosparkUser: GeoSparkUser) {
        // do something when toggle listener success
        // access locations listener status with geosparkUser.getLocationListenerStatus()
        // access events listener status with geosparkUser.getEventListenerStatus()
    }

    override fun onFailure(geosparkError: GeoSparkError) {
        // do something when toggle listener failure
    }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.toggleListener(locations, events, new GeoSparkCallback() {
    @Override
    public void onSuccess(GeoSparkUser geosparkUser) {
        // do something when toggle listener success
        // access locations listener status with geosparkUser.getLocationListenerStatus()
        // access events listener status with geosparkUser.getEventListenerStatus()
    }
    @Override
    public void onFailure(GeoSparkError geosparkError ) {
        // do something when toggle listener failure
    }
});
```
{% endtab %}
{% endtabs %}

You can also get the current status of listeners with the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getListenerStatus(object : GeoSparkCallback {
    override fun onSuccess(geosparkUser: GeoSparkUser) {
        // do something when get listener status success
        // get location listener status with geosparkUser.getLocationListenerStatus
        // get events listener status with geosparkUser.getEventListenerStatus
    }
    override fun onFailure(geosparkError: GeoSparkError) {
        // do something when get listener status failure
    }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.getListenerStatus(new GeoSparkCallback() {
    @Override
    public void onSuccess(GeoSparkUser geosparkUser) {
        // do something when get listener status success
        // get location listener status with geosparkUser.getLocationListenerStatus
        // get events listener status with geosparkUser.getEventListenerStatus
    }
    @Override
    public void onFailure(GeoSparkError geosparkError ) {
        // do something when get listener status failure
    }
});
```
{% endtab %}
{% endtabs %}

To listen to events on the server-side, you should enable events for the user using the method below.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.toggleEvents(geofence, trip, location, movingGeofence, object : GeoSparkCallback {
    override fun onSuccess(geosparkUser: GeoSparkUser) {
        // do something when toggle events success
        // access location events status with geosparkUser.getLocationEvents()
        // access geofence events status with geosparkUser.getGeofenceEvents()
        // access trips events status with geosparkUser.getTripsEvents()
        // get moving geofence event status with geosparkUser.getMovingGeofenceEvents()
    }

    override fun onFailure(error: GeoSparkError) {
        // do something when toggle events failure
    }

```
{% endtab %}
{% endtabs %}

Now, to listen to location updates and events, create a class that extends GeoSparkReceiver. Then register the receiver by adding a receiver element to the application element in your manifest.

```markup
<application>
        ...
     <receiver android:name=".MyGeoSparkReceiver"
                    android:enabled="true"
                    android:exported="false">
         <intent-filter>
         <action android:name="com.geospark.android.RECEIVED"/>
         </intent-filter>
     </receiver>
         ...
</application>

```

Then add the code to the receiver.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
public class MyGeoSparkReceiver : GeoSparkReceiver() {
    override fun onLocationUpdated(context: Context, geosparkLocation: GeoSparkLocation) {
        // receive own location updates here
        // do something with location data using location
    }

    override fun onLocationReceived(context: Context, geosparkLocationReceived: GeoSparkLocationReceived) {
        // receive other user's location updates here
        // do something with location
    }
    
    override fun onEventReceived(context: Context, geoSparkEvent: GeoSparkEvent) {
        //access event data here
    }

    override fun onReceiveTripStatus(context: Context, listener: TripStatusListener) {
        // receive real time trip status here
        // do something with trip status data
    }

    override fun onError(context: Context, geosparkError: GeoSparkError) {
        //access error data here
    }
}
```
{% endtab %}

{% tab title="Java" %}
```java
public class MyGeoSparkReceiver extends GeoSparkReceiver {

    @Override
    public void onLocationUpdated(Context context, GeoSparkLocation geosparkLocation) {
        // receive own location updates here
		// do something with location data using location
    }

    @Override
    public void onLocationReceived(Context context, GeoSparkLocationReceived geosparkLocationReceived) {
        // receive other user's location updates here
		// do something with location
    }

    @Override
    public void onEventReceived(Context context, GeoSparkEvent geoSparkEvent) {
		//access event data here
    }

    @Override
    public void onReceiveTripStatus(Context context, TripStatusListener listener) { 
        // receive real time trip status here
		// do something with trip status data
    }

    @Override
    public void onError(Context context, GeoSparkError geosparkError) {
         //access error data here
    }
}
```
{% endtab %}
{% endtabs %}

