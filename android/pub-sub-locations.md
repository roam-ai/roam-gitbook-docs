# Pub/Sub Locations

## Creating Users <a id="Creating-Users"></a>

Once the SDK is initialized, we need to _create_ or _get a user_ to start the tracking and use other methods. Every user created will have a unique GeoSpark identifier which will be used later to login and access developer APIs. We can call it as GeoSpark userId.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.createUser("SET USER DESCRIPTION HERE", object : GeoSparkCallback {
      override fun onSuccess(geosparkUser: GeoSparkUser) {
            // do something when create user success
            // access geospark user id with geosparkUser.getUserId()
            // access geospark user description with geosparkUser.getDescription()
      }

      override fun onFailure(geosparkError: GeoSparkError) {
            // do something when create user failure
            // access geospark error code with geosparkError.getCode()
            // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.createUser("SET USER DESCRIPTION HERE", new GeoSparkCallback() {
    @Override
    public void onSuccess(GeoSparkUser geosparkUser) {
        // do something when create user success
        // access geospark user id with geosparkUser.getUserId()
        // access geospark user description with geosparkUser.getDescription()
    }
    @Override
    public void onFailure(GeoSparkError geosparkError) {
        // do something when create user failure
        // access geospark error code with geosparkError.getCode()
        // access geospark error message with geosparkError.getMessage()
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
GeoSpark.setDescription("SET USER DESCRIPTION HERE")
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.setDescription("SET USER DESCRIPTION HERE");
```
{% endtab %}
{% endtabs %}

### Get User

If you already have a GeoSpark userID which you would like to reuse instead of creating a new user, use the below to get user session.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getUser("GEOSPARK USER ID", object : GeoSparkCallback {
      override fun onSuccess(geosparkUser: GeoSparkUser) {
        // do something when get user success
        // access geospark user id with geosparkUser.getUserId()
        // access geospark user description with geosparkUser.getDescription()
      }

      override fun onFailure(error: GeoSparkError) {
        // do something when get user failure
        // access geospark error code with error.getCode()
        // access geospark error message with error.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.getUser("GEOSPARK USER ID", new GeoSparkCallback() {
    @Override
    public void onSuccess(GeoSparkUser geosparkUser) {
        // do something when get user success
        // access geospark user id with geosparkUser.getUserId()
        // access geospark user description with geosparkUser.getDescription()
    }
    @Override
    public void onFailure(GeoSparkError error) {
        // do something when get user failure
        // access geospark error code with error.getCode()
        // access geospark error message with error.getMessage()
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
GeoSpark.startTracking(TrackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.startTracking(TrackingMode);
```
{% endtab %}
{% endtabs %}

Use the tracking modes while you use the `startTracking` method `GeoSpark.startTracking`

### Tracking Modes

GeoSpark has three default tracking modes along with a custom version. They differ based on the frequency of location updates and battery consumption. The higher the frequency, the higher is the battery consumption. You must use [foreground service](https://developer.android.com/about/versions/oreo/background-location-limits) for continuous tracking.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// active tracking
GeoSpark.startTracking(GeoSparkTrackingMode.ACTIVE)
// balanced tracking
GeoSpark.startTracking(GeoSparkTrackingMode.BALANCED)
// passive tracking
GeoSpark.startTracking(GeoSparkTrackingMode.PASSIVE)
```
{% endtab %}

{% tab title="Java" %}
```java
// active tracking
GeoSpark.startTracking(GeoSparkTrackingMode.ACTIVE);
// balanced tracking
GeoSpark.startTracking(GeoSparkTrackingMode.BALANCED);
// passive tracking
GeoSpark.startTracking(GeoSparkTrackingMode.PASSIVE);
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
//Update location based on distance between locations.
val trackingMode = GeoSparkTrackingMode.Builder("DISTANCE IN METERS", "STATIONARY DURATION IN SECONDS")
                  .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                  .build()
```
{% endtab %}

{% tab title="Java" %}
```java
//Update location based on distance between locations.
GeoSparkTrackingMode trackingMode = new GeoSparkTrackingMode.Builder("DISTANCE IN METERS", "STATIONARY DURATION IN SECONDS")
                        .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                        .build();
```
{% endtab %}
{% endtabs %}

**Time between location updates example code:**

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
//Update location based on time interval.
val trackingMode = GeoSparkTrackingMode.Builder("INTERVAL IN SECONDS")
                  .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                  .build()
```
{% endtab %}

{% tab title="Java" %}
```java
//Update location based on time interval.
GeoSparkTrackingMode trackingMode = new GeoSparkTrackingMode.Builder("INTERVAL IN SECONDS")
                        .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                        .build();
```
{% endtab %}
{% endtabs %}

You may see a delay if the user's device is in low power mode or has connectivity issues.

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.stopTracking()
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.stopTracking();
```
{% endtab %}
{% endtabs %}

## Publish Locations <a id="Publish-Messages"></a>

It will publish location data and these data will be sent to Roam servers for further processing and data will be saved in our database servers.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
val locationData = GeoSparkPublish.Builder()
            .build()
GeoSpark.publishAndSave(locationData)
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSparkPublish geoSparkPublish = new GeoSparkPublish.Builder()
                                .build();
GeoSpark.publishAndSave(geoSparkPublish);
```
{% endtab %}
{% endtabs %}

To stop publishing locations.

{% tabs %}
{% tab title="Kotlin" %}
```text
GeoSpark.stopPublishing()
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.stopPublishing();
```
{% endtab %}
{% endtabs %}

## Subscribe Messages

Now that you have enabled the location listener, use the below method to subscribe to your own or other user's location updates and events. 

### **Subscribe**

{% tabs %}
{% tab title="Kotlin" %}
```javascript
GeoSpark.subscribe(TYPE, "USER-ID")
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
GeoSpark.unSubscribe(TYPE, "USER-ID")
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.unSubscribe(TYPE, "USER-ID");
```
{% endtab %}
{% endtabs %}

| **Type** | **Description** |
| :--- | :--- |
| GeoSpark.Subscribe.EVENTS | Subscribe to your own events.   |
| GeoSpark.Subscribe.LOCATION | Subscribe to your own location \(or\) other user's location updates. |
| GeoSpark.Subscribe.BOTH | Subscribe to your own events and location \(or\) other user's location updates. |

## Location Listener

In order to listen to location updates locally, you can follow the below steps for pub/sub tracking.

{% page-ref page="sdk-methods/listeners-and-events.md" %}

