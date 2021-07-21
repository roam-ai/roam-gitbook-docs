# Trip SDK Methods

## Create Trip

Use the below code to create a trip directly from the SDK. Set **Boolean** value `true` to create offline trip and `false` to create online trip.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.createTrip(null, null, Boolean, object : GeoSparkCreateTripCallback {
      override fun onSuccess(geosparkTrip: GeoSparkCreateTrip) {
            // do something when create trip success
            // access geospark trip created timestamp with geosparkTrip.getCreatedAt
            // access geospark trip user id with geosparkTrip.getUserId
            // access geospark trip id with geosparkTrip.getTripId
      }
            ​
      override fun onFailure(geosparkError: GeoSparkError) {
            // do something when create trip error
            // access geospark error code with geosparkError.getCode()
            // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.createTrip(null, null, Boolean, new GeoSparkCreateTripCallback() {
      @Override
      public void onSuccess(GeoSparkCreateTrip geosparkTrip) {
              // do something when create trip success
              // access geospark trip created timestamp with geosparkTrip.getCreatedAt
              // access geospark trip user id with geosparkTrip.getUserId
              // access geospark trip id with geosparkTrip.getTripId
     }
​
      @Override
      public void onFailure(GeoSparkError geosparkError) {
              // do something when create trip error
              // access geospark error code with geosparkError.getCode()
              // access geospark error message with geosparkError.getMessage()
     }
});
```
{% endtab %}
{% endtabs %}

## Get Trip Details

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getTripDetails("GEOSPARK-TRIP-ID", object : GeoSparkTripDetailCallback {
      override fun onSuccess(geosparkTrip: GeoSparkTripDetail) {
              // do something when get trip details success
              // access geospark trip created timestamp with geosparkTrip.getCreatedAt()
              // access geospark trip user id with geosparkTrip.getUserId()
              // access geospark trip id with geosparkTrip.getTripId()
      }
            ​
      override fun onFailure(geosparkError: GeoSparkError) {
              // do something when get trip details error
              // access geospark error code with geosparkError.getCode()
              // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.getTripDetails("GEOSPARK-TRIP-ID", new GeoSparkTripDetailCallback() {
            @Override
            public void onSuccess(GeoSparkTripDetail geosparkTrip) {
                // do something when get trip details success
                // access geospark trip created timestamp with geosparkTrip.getCreatedAt()
                // access geospark trip user id with geosparkTrip.getUserId()
                // access geospark trip id with geosparkTrip.getTripId()
            }
​
            @Override
            public void onFailure(GeoSparkError geosparkError) {
                // do something when get trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

## Start and Stop Trip

### Start Trip

Use the below code to start the trip with the previously created trip id.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 GeoSpark.startTrip("GEOSPARK-TRIP-ID", "GEOSPARK-TRIP-DESCRIPTION", object : GeoSparkTripCallback {
        override fun onSuccess(message: String) {
        }
                ​
        override fun onFailure(geosparkError: GeoSparkError) {
                    // do something when start trip details error
                    // access geospark error code with geosparkError.getCode()
                    // access geospark error message with geosparkError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.startTrip("GEOSPARK-TRIP-ID", "GEOSPARK-TRIP-DESCRIPTION", new GeoSparkTripCallback() {
            @Override
            public void onSuccess(String message) {
            }
​
            @Override
            public void onFailure(GeoSparkError geosparkError) {
                // do something when start trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

### Stop Trip

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.stopTrip("GEOSPARK-TRIP-ID", object : GeoSparkTripCallback {
      override fun onSuccess(message: String) {

      }
            ​
      override fun onFailure(geosparkError: GeoSparkError) {
            // do something when start trip details error
            // access geospark error code with geosparkError.getCode()
            // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}
{% endtabs %}

## Pause and Resume Trip

### Pause Trip

Use the below code to pause the trip with the previously started trip id.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.pauseTrip("GEOSPARK-TRIP-ID", object : GeoSparkTripCallback {
      override fun onSuccess(message: String) {

      }
            ​
      override fun onFailure(geosparkError: GeoSparkError) {
            // do something when start trip details error
            // access geospark error code with geosparkError.getCode()
            // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.pauseTrip("GEOSPARK-TRIP-ID", new GeoSparkTripCallback() {
            @Override
            public void onSuccess(String message) {
            }
​
            @Override
            public void onFailure(GeoSparkError geosparkError) {
                // do something when start trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

### Resume Trip

To resume the trip.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.resumeTrip("GEOSPARK-TRIP-ID", object : GeoSparkTripCallback {
      override fun onSuccess(message: String) {

      }
            ​
      override fun onFailure(geosparkError: GeoSparkError) {
            // do something when start trip details error
            // access geospark error code with geosparkError.getCode()
            // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.resumeTrip("GEOSPARK-TRIP-ID", new GeoSparkTripCallback() {
      @Override
      public void onSuccess(String message) {
      }
​
      @Override
      public void onFailure(GeoSparkError geosparkError) {
           // do something when start trip details error
           // access geospark error code with geosparkError.getCode()
           // access geospark error message with geosparkError.getMessage()
      }
});
```
{% endtab %}
{% endtabs %}

## Subscribe Trip Status <a id="Subscribe-Trip-Status"></a>

 Subscribe to `tripStatus` using `tripId` to get real-time trip status.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
//subscribe to trip status
GeoSpark.subscribeTripStatus("GeoSpark Trip ID")
```
{% endtab %}

{% tab title="Java" %}
```java
//subscribe to trip status
GeoSpark.subscribeTripStatus("GeoSpark Trip ID");
```
{% endtab %}
{% endtabs %}

To stop receiving trip status updates, use the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
//unsubscribe to trip status
GeoSpark.unSubscribeTripStatus("GeoSpark Trip ID")
```
{% endtab %}
{% endtabs %}

## Get Trip Status

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getTripStatus("GEOSPARK-TRIP-ID", object : GeoSparkTripStatusCallback {
      override fun onSuccess(geosparkTrip: GeoSparkTripStatus) {
                // do something when get trip details success
                // access geospark trip distance with geosparkTrip.getDistance()
                // access geospark trip speed with geosparkTrip.getSpeed()
      }
            ​
      override fun onFailure(geosparkError: GeoSparkError) {
              // do something when get trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
      }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.getTripStatus("GEOSPARK-TRIP-ID", new GeoSparkTripStatusCallback() {
            @Override
            public void onSuccess(GeoSparkTripStatus geosparkTrip) {
                // do something when get trip details success
                // access geospark trip distance with geosparkTrip.getDistance()
                // access geospark trip speed with geosparkTrip.getSpeed()
            }
​
            @Override
            public void onFailure(GeoSparkError geosparkError) {
                // do something when get trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

## Get Active Trips

To get the active trips. Set **Boolean** value `true` to get offline trips and `false` to get online trips.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.activeTrips(Boolean, object : GeoSparkActiveTripsCallback {
        override fun onSuccess(geoSparkTrip: GeoSparkTrip) {
                geoSparkTrip.activeTrips
        }

        override fun onFailure(geoSparkError: GeoSparkError) {
                geoSparkError.code
                geoSparkError.message
        }
})
```
{% endtab %}
{% endtabs %}

## Get Trip Summary.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.getTripSummary("GEOSPARK-TRIP-ID", object : GeoSparkTripSummaryCallback {
        override fun onSuccess(geosparkTrip: GeoSparkTripSummary) {
                // do something when get trip details success
                // access geospark trip distance covered with geosparkTrip.getDistanceCovered
                // access geospark trip route with geosparkTrip.getRoute
                // access geospark trip duration with geosparkTrip.getDuration
                // access geospark trip id with geosparkTrip.getTripId
        }
            ​
        override fun onFailure(geosparkError: GeoSparkError) {
                // do something when get trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.getTripSummary("GEOSPARK-TRIP-ID", new GeoSparkTripSummaryCallback() {
            @Override
            public void onSuccess(GeoSparkTripSummary geosparkTrip) {
                // do something when get trip details success
                // access geospark trip distance covered with geosparkTrip.getDistanceCovered
                // access geospark trip route with geosparkTrip.getRoute
                // access geospark trip duration with geosparkTrip.getDuration
                // access geospark trip id with geosparkTrip.getTripId
            }
​
            @Override
            public void onFailure(GeoSparkError geosparkError) {
                // do something when get trip details error
                // access geospark error code with geosparkError.getCode()
                // access geospark error message with geosparkError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

