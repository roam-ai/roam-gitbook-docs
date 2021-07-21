# Get Current Location

## Current Location

Get the current location of the user. You can set the accuracy from 5 to 100 meters \(default is 10\). This method has two outputs.

1. Callback Method which returns the current location with faster response time and the accuracy depends on the current GPS connectivity.
2. Location Receiver which returns the next two location updates which will be higher accuracy compared to the callback and takes time from few hundred milliseconds to a couple of seconds based on the GPS and network connectivity.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getCurrentLocation(accuracy)
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.getCurrentLocation(accuracy);
```
{% endtab %}
{% endtabs %}

To listen to location updates create a class that extends GeoSparkReceiver. Then register the receiver by adding a receiver element to the application element in your manifest.

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
class MyGeoSparkReceiver : GeoSparkReceiver() {
      override fun onLocationUpdated(context: Context?, geosparkLocation: GeoSparkLocation?) {
            // receive own location updates here
            // do something with location data using location
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
}
```
{% endtab %}
{% endtabs %}

Get the current location of the user in the callback.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getCurrentLocation(DesiredAccuracy, accuracy, object : GeoSparkLocationCallback {
            override fun location(location: Location?) {
            }
            override fun onFailure(geoSparkError: GeoSparkError) {
                geoSparkError.code
                geoSparkError.message
            }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.getCurrentLocation(DesiredAccuracy, accuracy, new GeoSparkLocationCallback(){
    @Override
    public void location(Location location) {
    }
    @Override
    public void onFailure(GeoSparkError geoSparkError) {
            geoSparkError.getCode();
            geoSparkError.getMessage(); 
    }
});
```
{% endtab %}
{% endtabs %}

| **Parameter** | **Description** |
| :--- | :--- |
| DesiredAccuracy | GeoSparkTrackingMode.DesiredAccuracy.**HIGH** or GeoSparkTrackingMode.DesiredAccuracy.**MEDIUM** or GeoSparkTrackingMode.DesiredAccuracy.**LOW** |

