# Android

## Modified

We have modified below methods for Start Tracking to track locations locally and not publish to servers.

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

## Added

We have added below methods to enable location publish to our servers for processing events for geofence, location, trips and moving geofence. If the location is not published, the location data will remain in the device itself for its own consumption and will not be sent to our servers.

### Publish Messages

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

### Subscribe Messages

Now that you have enabled the location listener, use the below method to subscribe to your own or other user's location updates and events. 

#### **Subscribe**

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

#### **Unsubscribe**

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

