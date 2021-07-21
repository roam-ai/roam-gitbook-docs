# Trip SDK Methods

## Create Trip

Use the below code to create a trip directly from the SDK. Set **Boolean** value `true` to create **offline trip** and `false` to create **online trip**.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.createTrip(Bool, nil) { (trip, error) in
          //   access geospark trip created timestamp with geosparkTrip?.createdAt
          //   access geospark trip user id with geosparkTrip?.userId
          //   access geospark trip id with geosparkTrip?.tripId
          //   access geospark error code with error?.code
         //   access geospark error message with error?.message            
}
```
{% endtab %}

{% tab title="Objective-C" %}
```swift
[GeoSpark createTrip:true :nil handler:^(GeoSparkCreateTrip * trip, GeoSparkError * error) {
             //   access geospark trip created timestamp with geosparkTrip?.createdAt
             //   access geospark trip user id with geosparkTrip?.userId
             //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message       
}];
```
{% endtab %}
{% endtabs %}

## Get Trip Details

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getTripDetails("GEOSPARK-TRIP-ID") { (geosparkTrip, error) in
            //   access geospark trip created timestamp with geosparkTrip?.createdAt
            //   access geospark trip user id with geosparkTrip?.userId
            //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [GeoSpark getTripDetails:@"GEOSPARK-TRIP-ID" handler:^(GeoSparkGetTrip * trip, GeoSparkError * error) {
            //   access geospark trip created timestamp with geosparkTrip?.createdAt
            //   access geospark trip user id with geosparkTrip?.userId
            //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message  
  }];
```
{% endtab %}
{% endtabs %}

## Start and Stop Trip

### Start Trip

To start the trip with the previously created trip id.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.startTrip("GEOSPARK-TRIP-ID") { (status, error) in
            //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
}
```
{% endtab %}

{% tab title="Objective C" %}
```objectivec
[GeoSpark startTrip:@"GEOSPARK-TRIP-ID" :@"GEOSPARK-TRIP-DESC" handler:^(NSString * status, GeoSparkError * error) {
            //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message        
}];
```
{% endtab %}
{% endtabs %}

### Stop Trip

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.stopTrip("GEOSPARK-TRIP-ID") { (status, error) in
            //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
}
```
{% endtab %}

{% tab title="Objective C" %}
```objectivec
[GeoSpark stopTrip:@"GEOSPARK-TRIP-ID" handler:^(NSString * status, GeoSparkError * error) {
             //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message   
  }];
```
{% endtab %}
{% endtabs %}

## Pause and Resume Trip

### Pause Trip

To pause the trip with the previously started trip id.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.pauseTrip("GEOSPARK-TRIP-ID") { (status, error) in
            //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
}
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [GeoSpark pauseTrip:@"GEOSPARK-TRIP-ID" handler:^(NSString * status, GeoSparkError * error) {
             //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message   
  }];
```
{% endtab %}
{% endtabs %}

### Resume Trip

To resume the trip.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.resumeTrip("GEOSPARK-TRIP-ID") { (status, error) in
            //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
}
```
{% endtab %}

{% tab title="Objective C" %}
```objectivec
[GeoSpark resumeTrip:@"GEOSPARK-TRIP-ID" handler:^(NSString * status, GeoSparkError * error) {
             //   access geospark trip status with status
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message   
  }];
```
{% endtab %}
{% endtabs %}

## Subscribe Trip Status

Subscribe to `tripStatus` using `tripId` to get realtime trip status.

{% tabs %}
{% tab title="Swift" %}
```swift
//subscribe to trip status
GeoSpark.subscribeTripStatus("GeoSpark Trip ID")
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
//subscribe to trip status
[GeoSpark subscribeTripStatus:@"GeoSpark Trip ID")
```
{% endtab %}
{% endtabs %}

To stop receiving trip status updates, use the below method.

{% tabs %}
{% tab title="Swift" %}
```swift
//unsubscribe to trip status
GeoSpark.unSubscribeTripStatus("GeoSpark Trip ID")
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
//unsubscribe to trip status
[GeoSpark unSubscribeTripStatus:@"GeoSpark Trip ID")
```
{% endtab %}
{% endtabs %}

## Get Trip Status

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getTripStatus("GEOSPARK-TRIP-ID") { (geosparkTrip, error) in
            //   access geospark trip distance covered with geosparkTrip?.distance
            //   access geospark trip speed with geosparkTrip?.speed
            //   access geospark trip duration with geosparkTrip?.duration
            //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark trip started timestamp with geosparkTrip?.startedAt
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```swift
  [GeoSpark getTripStatus:@"GEOSPARK-TRIP-ID" handler:^(GeoSparkTripListener * geosparkTrip, GeoSparkError * error) {
            //   access geospark trip distance covered with geosparkTrip?.distance
            //   access geospark trip speed with geosparkTrip?.speed
            //   access geospark trip duration with geosparkTrip?.duration
            //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark trip started timestamp with geosparkTrip?.startedAt
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
  }];
```
{% endtab %}
{% endtabs %}

## Get Trip Summary

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getTripSummary("GEOSPARK-TRIP-ID") { (geosparkTrip, error) in
            //   access geospark trip distance covered with geosparkTrip?.distanceCovered
            //   access geospark trip route with geosparkTrip?.route
            //   access geospark trip duration with geosparkTrip?.duration
            //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```
[GeoSpark getTripSummary:@"GEOSPARK-TRIP-ID" handler:^(GeoSparkTripSummary * geosparkTrip, GeoSparkError * error) {
            //   access geospark trip distance covered with geosparkTrip?.distanceCovered
            //   access geospark trip route with geosparkTrip?.route
            //   access geospark trip duration with geosparkTrip?.duration
            //   access geospark trip id with geosparkTrip?.tripId
            //   access geospark error code with error?.code
            //   access geospark error message with error?.message 
}];
```
{% endtab %}
{% endtabs %}





## 

