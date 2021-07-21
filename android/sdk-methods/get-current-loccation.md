# Get Current Location

## Current Location

Get the current location of the user. You can set the accuracy from 5 to 100 meters \(default is 10\). This method has two outputs.

1. Callback Method which returns the current location with faster response time and the accuracy depends on the current GPS connectivity.
2. Location Receiver which returns the next two location updates which will be higher accuracy compared to the callback and takes time from few hundred milliseconds to a couple of seconds based on the GPS and network connectivity.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getCurrentLocation(accuracy)
```
{% endtab %}

{% tab title="Java" %}
```
Roam.getCurrentLocation(accuracy);
```
{% endtab %}
{% endtabs %}

To listen to location updates create a class that extends RoamReceiver. Then register the receiver by adding a receiver element to the application element in your manifest.

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
class LocationReceiver : RoamReceiver() {
      override fun onLocationUpdated(context: Context?, roamLocation: RoamLocation?) {
            // receive own location updates here
            // do something with location data using location
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
}
```
{% endtab %}
{% endtabs %}

Get the current location of the user in the callback.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getCurrentLocation(DesiredAccuracy, accuracy, object : RoamLocationCallback {
            override fun location(location: Location?) {
                // Access location data here
            }
            override fun onFailure(roamError: RoamError) {
                // Access Error code and message here
                // roamError.code
                // roamError.message
            }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getCurrentLocation(DesiredAccuracy, accuracy, new RoamLocationCallback(){
    @Override
    public void location(Location location) {
            // Access location data here
    }
    @Override
    public void onFailure(RoamError roamError) {
            // Access Error code and message here
            // roamError.getCode();
            // roamError.getMessage(); 
    }
});
```
{% endtab %}
{% endtabs %}

| **Parameter** | **Description** |
| :--- | :--- |
| DesiredAccuracy | RoamTrackingMode.DesiredAccuracy.**HIGH** RoamTrackingMode.DesiredAccuracy.**MEDIUM** RoamTrackingMode.DesiredAccuracy.**LOW** |

