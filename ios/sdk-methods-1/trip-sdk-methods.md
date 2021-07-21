# Trip SDK Methods

## Create Trip

Use the below code to create a trip directly from the SDK. Set **Boolean** value `true` to create **offline trip** and `false` to create **online trip**.

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.createTrip(Bool, nil) { (roamTrip, roamError) in
          //   access roam trip created timestamp with roamTrip?.createdAt
          //   access roam trip user id with roamTrip?.userId
          //   access roam trip id with roamTrip?.tripId
          //   access roam error code with roamError?.code
         //   access roam error message with roamError?.message            
}
```
{% endtab %}

{% tab title="Objective-C" %}
```swift
[Roam createTrip:true :nil handler:^(RoamCreateTrip * roamTrip, RoamError * roamError) {
             //   access roam trip created timestamp with roamTrip?.createdAt
             //   access roam trip user id with roamTrip?.userId
             //   access roam trip id with roamTrip?.tripId
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message       
}];
```
{% endtab %}
{% endtabs %}

## Get Trip Details

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.getTripDetails("ROAM-TRIP-ID") { (roamTrip, roamError) in
            //   access roam trip created timestamp with roamTrip?.createdAt
            //   access roam trip user id with roamTrip?.userId
            //   access roam trip id with roamTrip?.tripId
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [Roam getTripDetails:@"ROAM-TRIP-ID" handler:^(RoamGetTrip * roamTrip, RoamError * roamError) {
            //   access roam trip created timestamp with roamTrip?.createdAt
            //   access roam trip user id with roamTrip?.userId
            //   access roam trip id with roamTrip?.tripId
            //   access roam error code with roamTrip?.code
            //   access roam error message with roamError?.message  
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
Roam.startTrip("ROAM-TRIP-ID") { (status, roamError) in
             //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
}
```
{% endtab %}

{% tab title="Objective C" %}
```objectivec
[Roam startTrip:@"ROAM-TRIP-ID" :@"ROAM-TRIP-DESC" handler:^(NSString * status, RoamError * roamError) {
            //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message  
}];
```
{% endtab %}
{% endtabs %}

### Stop Trip

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.stopTrip("ROAM-TRIP-ID") { (status, roamError) in
             //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
}
```
{% endtab %}

{% tab title="Objective C" %}
```objectivec
[Roam stopTrip:@"ROAM-TRIP-ID" handler:^(NSString * status, RoamError * roamError) {
             //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message  
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
Roam.pauseTrip("ROAM-TRIP-ID") { (status, error) in
            //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
}
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [Roam pauseTrip:@"ROAM-TRIP-ID" handler:^(NSString * status, RoamError * roamError) {
                    //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message  
  }];
```
{% endtab %}
{% endtabs %}

### Resume Trip

To resume the trip.

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.resumeTrip("ROAM-TRIP-ID") { (status, roamError) in
            //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
}
```
{% endtab %}

{% tab title="Objective C" %}
```objectivec
[Roam resumeTrip:@"ROAM-TRIP-ID" handler:^(NSString * status, RoamError * roamError) {
             //   access roam trip status with status
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message   
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
Roam.subscribeTripStatus("ROAM-TRIP-ID")
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
//subscribe to trip status
[Roam subscribeTripStatus:@"ROAM-TRIP-ID")
```
{% endtab %}
{% endtabs %}

To stop receiving trip status updates, use the below method.

{% tabs %}
{% tab title="Swift" %}
```swift
//unsubscribe to trip status
Roam.unSubscribeTripStatus("ROAM-TRIP-ID")
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
//unsubscribe to trip status
[Roam unSubscribeTripStatus:@"ROAM-TRIP-ID")
```
{% endtab %}
{% endtabs %}

## Get Trip Status

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.getTripStatus("ROAM-TRIP-ID") { (roamTrip, roamError) in
            //   access roam trip distance covered with roamTrip?.distance
            //   access roam trip speed with roamTrip?.speed
            //   access roam trip duration with roamTrip?.duration
            //   access roam trip id with roamTrip?.tripId
            //   access roam trip started timestamp with roamTrip?.startedAt
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```swift
  [Roam getTripStatus:@"ROAM-TRIP-ID" handler:^(RoamTripListener * roamTrip, RoamError * roamError) {
            //   access roam trip distance covered with roamTrip?.distance
            //   access roam trip speed with roamTrip?.speed
            //   access roam trip duration with roamTrip?.duration
            //   access roam trip id with roamTrip?.tripId
            //   access roam trip started timestamp with roamTrip?.startedAt
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
  }];
```
{% endtab %}
{% endtabs %}

## Get Trip Summary

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.getTripSummary("ROAM-TRIP-ID") { (roamTrip, roamError) in
            //   access roam trip distance covered with roamTrip?.distanceCovered
            //   access roam trip route with roamTrip?.route
            //   access roam trip duration with roamTrip?.duration
            //   access roam trip id with roamTrip?.tripId
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[Roam getTripSummary:@"ROAM-TRIP-ID" handler:^(RoamTripSummary * roamTrip, RoamError * roamError) {
            //   access roam trip distance covered with roamTrip?.distanceCovered
            //   access roam trip route with roamTrip?.route
            //   access roam trip duration with roamTrip?.duration
            //   access roam trip id with roamTrip?.tripId
            //   access roam error code with roamError?.code
            //   access roam error message with roamError?.message 
}];
```
{% endtab %}
{% endtabs %}





## 

