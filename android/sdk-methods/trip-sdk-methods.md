# Trip SDK Methods

## Create Trip

Use the below code to create a trip directly from the SDK. Set **Boolean** value `true` to create offline trip and `false` to create online trip.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.createTrip(null, null, Boolean, object : RoamCreateTripCallback {
      override fun onSuccess(roamTrip: RoamCreateTrip) {
            // do something when create trip success
            // access roam trip created timestamp with roamTrip.getCreatedAt
            // access roam trip user id with roamTrip.getUserId
            // access roam trip id with roamTrip.getTripId
      }
            ​
      override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.createTrip(null, null, Boolean, new RoamCreateTripCallback() {
      @Override
      public void onSuccess(RoamCreateTrip roamTrip) {
              // do something when create trip success
              // access roam trip created timestamp with roamTrip.getCreatedAt
              // access roam trip user id with roamTrip.getUserId
              // access roam trip id with roamTrip.getTripId
     }
​
      @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

## Get Trip Details

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getTripDetails("ROAM-TRIP-ID", object : RoamTripDetailCallback {
      override fun onSuccess(roamTrip: RoamTripDetail) {
              // do something when get trip details success
              // access roam trip created timestamp with roamTrip.getCreatedAt()
              // access roam trip user id with roamTrip.getUserId()
              // access roam trip id with roamTrip.getTripId()
      }
            ​
      override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getTripDetails("ROAM-TRIP-ID", new RoamTripDetailCallback() {
            @Override
            public void onSuccess(RoamTripDetail roamTrip) {
                // do something when get trip details success
                // access roam trip created timestamp with roamTrip.getCreatedAt()
                // access roam trip user id with roamTrip.getUserId()
                // access roam trip id with roamTrip.getTripId()
            }
​
            @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
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
 Roam.startTrip("ROAM-TRIP-ID", "ROAM-TRIP-DESCRIPTION", object : RoamTripCallback {
        override fun onSuccess(message: String) {
        }
                ​
        override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.startTrip("ROAM-TRIP-ID", "ROAM-TRIP-DESCRIPTION", new RoamTripCallback() {
            @Override
            public void onSuccess(String message) {
            }
​
            @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

### Stop Trip

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.stopTrip("ROAM-TRIP-ID", object : RoamTripCallback {
      override fun onSuccess(message: String) {

      }
            ​
      override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.stopTrip("ROAM-TRIP-ID", new RoamTripCallback() {
            @Override
            public void onSuccess(String message) {
            }
​
            @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

## Pause and Resume Trip

### Pause Trip

Use the below code to pause the trip with the previously started trip id.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.pauseTrip("ROAM-TRIP-ID", object : RoamTripCallback {
      override fun onSuccess(message: String) {

      }
            ​
      override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.pauseTrip("ROAM-TRIP-ID", new RoamTripCallback() {
            @Override
            public void onSuccess(String message) {
            }
​
            @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
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
Roam.resumeTrip("ROAM-TRIP-ID", object : RoamTripCallback {
      override fun onSuccess(message: String) {

      }
            ​
      override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.resumeTrip("ROAM-TRIP-ID", new RoamTripCallback() {
      @Override
      public void onSuccess(String message) {
      }
​
      @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
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
Roam.subscribeTripStatus("ROAM-TRIP-ID")
```
{% endtab %}

{% tab title="Java" %}
```java
//subscribe to trip status
Roam.subscribeTripStatus("ROAM-TRIP-ID");
```
{% endtab %}
{% endtabs %}

To stop receiving trip status updates, use the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
//unsubscribe to trip status
Roam.unSubscribeTripStatus("ROAM-TRIP-ID")
```
{% endtab %}

{% tab title="Java" %}
```java
//unsubscribe to trip status
Roam.unSubscribeTripStatus("ROAM-TRIP-ID");
```
{% endtab %}
{% endtabs %}

## Get Trip Status

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getTripStatus("ROAM-TRIP-ID", object : RoamTripStatusCallback {
      override fun onSuccess(roamTrip: RoamTripStatus) {
                // do something when get trip details success
                // access roam trip distance with roamTrip.getDistance()
                // access roam trip speed with roamTrip.getSpeed()
      }
            ​
      override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getTripStatus("ROAM-TRIP-ID", new RoamTripStatusCallback() {
            @Override
            public void onSuccess(RoamTripStatus roamTrip) {
                // do something when get trip details success
                // access roam trip distance with roamTrip.getDistance()
                // access roam trip speed with roamTrip.getSpeed()
            }
​
            @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
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
Roam.activeTrips(Boolean, object : RoamActiveTripsCallback {
        override fun onSuccess(roamTrip: RoamTrip) {
                roamTrip.activeTrips
        }

        override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}
{% endtabs %}

## Get Trip Summary.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.getTripSummary("ROAM-TRIP-ID", object : RoamTripSummaryCallback {
        override fun onSuccess(roamTrip: RoamTripSummary) {
                // do something when get trip details success
                // access roam trip distance covered with roamTrip.getDistanceCovered
                // access roam trip route with roamTrip.getRoute
                // access roam trip duration with roamTrip.getDuration
                // access roam trip id with roamTrip.getTripId
        }
            ​
        override fun onFailure(roamError: RoamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
        }
})
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.getTripSummary("ROAM-TRIP-ID", new RoamTripSummaryCallback() {
            @Override
            public void onSuccess(RoamTripSummary roamTrip) {
                // do something when get trip details success
                // access roam trip distance covered with roamTrip.getDistanceCovered
                // access roam trip route with roamTrip.getRoute
                // access roam trip duration with roamTrip.getDuration
                // access roam trip id with roamTrip.getTripId
            }
​
            @Override
            public void onFailure(RoamError roamError) {
                // do something when get trip details error
                // access roam error code with roamError.getCode()
                // access roam error message with roamError.getMessage()
            }
});
```
{% endtab %}
{% endtabs %}

