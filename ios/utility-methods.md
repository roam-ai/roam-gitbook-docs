---
description: An archive of our SDK methods.
---

# Utility Methods

## **Initialize SDK**

Initialize the SDK in your `AppDelegate`

{% tabs %}
{% tab title="Swift" %}
```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
    GeoSpark.intialize("PUBLISHABLEKEY")
        return true
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [GeoSpark intialize:@"PUBLISHABLEKEY"];
    return YES;
}
```
{% endtab %}
{% endtabs %}

## **Set DeviceToken**

GeoSpark SDK is capable of sending push notifications to your users. ****[Check here](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/index.html#//apple_ref/doc/uid/TP40008194-CH3-SW1) to get device token.

{% tabs %}
{% tab title="Swift" %}
```swift
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
     GeoSpark.setDeviceToken(deviceToken)
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken{
    [GeoSpark didRegisterForRemoteNotificationsWithDeviceToken:deviceToken];
  }
```
{% endtab %}
{% endtabs %}

## **Create User**

GeoSpark SDK needs an User ID object to identify the device. Before creating user you should have device token as you cannot create user without device token.

{% tabs %}
{% tab title="Swift" %}
```swift
  GeoSpark.createUser("User Description",{ (user) in
      // user.userId
    },onFailure: { (error) in
      // error.errorCode
      // error.errorMessage
  })
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
  [GeoSpark createUser:@"User Description" :^(GeoSparkUser * user) {
      // user.userId
    } onFailure:^(GeoSparkError * error) {
      // error.errorCode
      // error.errorMessage
  }];
```
{% endtab %}
{% endtabs %}

## **Get User**

If you already have an User ID, then SDK has a convenience method `getUser()` to start the session for the existing user.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getUser("USER_ID", { (user) in
     // user.userId
      },onFailure: { (error) in  
         // error.errorCode
         // error.errorMessage
  })
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark getUser:@"USER_ID" :^(GeoSparkUser * user) {
      // user.userId
    } onFailure:^(GeoSparkError * error) {
          // error.errorCode
         // error.errorMessage
   }];
```
{% endtab %}
{% endtabs %}

## **User Description**

You can set Description for user by using `setDescription` method.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.setDescription("Description", { (user) in
        // user 
    }, onFailure:  { (erorr) in
         // error.errorCode
        // error.errorMessage
})
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark setDescription:@"Description" :^(GeoSparkUser * user) {
        // user
    } onFailure:^(GeoSparkError * error) {
        // error.errorCode
        // error.errorMessage
}];
```
{% endtab %}
{% endtabs %}

## Set Events

Use this method after user creation to enable user events for geofence, activity and trips. By default, all user events will be disabled post user creation.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.toggleEvents(Geofence: Bool, Trip: Bool, Activity: Bool, { (events)
in
         // events.geofenceEvents
        // events.activityEvents
       // events.tripsEvents
       }) { (error) in
        //error.errorCode
       //error.errorMessage
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [GeoSpark toggleEventsWithGeofence:true Trip:true Activity:true
 :^(GeoSparkEvents * events) {
         // events.geofenceEvents
        // events.activityEvents
       // events.tripsEvents
      } onFailure:^(GeoSparkError * error) {
             //error.errorCode
            //error.errorMessage
 }];
```
{% endtab %}
{% endtabs %}

## Get Events

Use this method after user creation to get the current status of user events for geofence, activity and trips.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getEventsStatus({ (events) in
        // events.geofenceEvents
       // events.activityEvents
      // events.tripsEvents
 }) { (error) in
         //error.errorCode
         //error.errorMessage
 }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark getEventsStatus:^(GeoSparkEvents * events) {
        // events.geofenceEvents
       // events.activityEvents
      // events.tripsEvents

  } onFailure:^(GeoSparkError * error) {
         //error.errorCode
         //error.errorMessage
 }];
```
{% endtab %}
{% endtabs %}

## **Check Location Permission**

Check whether your App has location permission.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.isLocationEnabled()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark isLocationEnabled];
```
{% endtab %}
{% endtabs %}

## **Check Motion Permission**

Check whether your App has motion permission.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.isMotionEnabled()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark isMotionEnabled];
```
{% endtab %}
{% endtabs %}

## Location Permission Status

By using `locationPermissionStatus` method you can check location permission status.

{% tabs %}
{% tab title="Swift" %}
```text
GeoSpark.locationPermissionStatus()
```
{% endtab %}

{% tab title="Objective-C" %}
```
[GeoSpark locationPermissionStatus];
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
notDetermined = 0 

restricted = 1 

denied = 2 

authorizedAlways = 3 

authorizedWhenInUse = 4
{% endhint %}

## **Request Location Permission**

Check whether your App has location permission.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.requestLocation()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark requestLocation];
```
{% endtab %}
{% endtabs %}

## **Request Motion Permission**

Check whether your app has motion permission.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.requestMotion()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark requestMotion];
```
{% endtab %}
{% endtabs %}

## **Start Location Tracking**

You can start tracking the user location by using `startTracking()` method.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.startTracking()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark startTracking];
```
{% endtab %}
{% endtabs %}

## Check Location Tracking

Check whether location tracking is started or not. This method returns boolean value.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.isLocationTracking()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark isLocationTracking];
```
{% endtab %}
{% endtabs %}

## **Stop Location Tracking**

You can stop tracking the user location by using `stopTracking()` method.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.stopTracking()
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark stopTracking];
```
{% endtab %}
{% endtabs %}

## **Location listener**

To listen for location client-side in the background, create a class that implements `GeoSparkDelegate` and then call `GeoSpark.delegate` . 

Set your `GeoSparkDelegate` in a codepath that will be initialized and executed in the background. For example, make your `AppDelegate` implement `GeoSparkDelegate` , not a `ViewController`. `AppDelegate` will be initialized in the background, whereas a `ViewController` may not be.

{% tabs %}
{% tab title="Swift" %}
{% code title="AppDelegate.swift" %}
```swift
class AppDelegate: UIResponder,
UIApplicationDelegate,UNUserNotificationCenterDelegate,GeoSparkDelegate{
    var window: UIWindow?
    func application(_ application: UIApplication,
didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey:
Any]?) -> Bool {
        GeoSpark.delegate = self
        return true
    }
....
func didUpdateLocation(_ location: GSLocation) {
    //do something with location, user
    }
....
func didFail(_ error: GeoSparkError) {
    }
....    
}
```
{% endcode %}
{% endtab %}

{% tab title="Objective-C" %}
{% code title="AppDelegate.h" %}
```objectivec
#import <GeoSpark/GeoSpark.h>
@interface AppDelegate : UIResponder <UIApplicationDelegate,GeoSparkDelegate>
```
{% endcode %}

{% code title="AppDelegate.m" %}
```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:
(NSDictionary *)launchOptions {
    GeoSpark.delegate = self;
    return YES;
}
....
- (void)didUpdateLocation:(GSLocation *)location {
   //do something with location, user
}

- (void)didFail:(GeoSparkError *)error{
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

## **Current Location**

Get current location of the user. You can set the accuracy from 10 to 100 meters \(default is 10\).

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.getCurrentLocation(accuracy) { (location) in
        //location.latitude
        //location.longitude
        //location.activity
        //location.accuracy
        //location.userId
}
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark getCurrentLocation:10:^(GSLocation * location) {
        //location.latitude
        //location.longitude
        //location.activity
        //location.accuracy
        //location.userId
}];
```
{% endtab %}
{% endtabs %}

## Update Current Location

Using `updateCurrentLocation` method, one can update user current location, you can set the accuracy from 10 to 100 meters \(default is 10\).

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.updateCurrentLocation(accuracy)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark updateCurrentLocation:accuracy];
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
This method should be used only if you need to update the current location of the device with better accuracy. Using this method often might consume battery.
{% endhint %}

## **Start Trip**

Once user start tracking location, you can use `startTrip` method

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.startTrip("Trip Id","Trip Description", { (trip) in
		// trip.msg
        }, onFailure: { (error) in 
         // error.errorCode
         // error.errorMessage
 })
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark startTrip:@"Trip Id":@"Trip Description" :^(GeoSparkTrip * trip) {
		// trip.msg
} onFailure:^(GeoSparkError * error) {
          // error.errorCode
         // error.errorMessage
}];
```
{% endtab %}
{% endtabs %}

## **End Trip**

Once the trip started, you can stop the trip using `TRIPID`

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.endTrip("TRIPID", { (trip) in
         // trip.msg
        }, onFailure: { (error) in   
          // error.errorCode
         // error.errorMessage
 })
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark endTrip:@"TRIPID" :^(GeoSparkTrip * trip) {
   		// trip.msg
    } onFailure:^(GeoSparkError * error) {
          // error.errorCode
         // error.errorMessage
    }];
```
{% endtab %}
{% endtabs %}

## **Active Trips**

By using `activeTrips` method you can see active trips of the user.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.activeTrips({ (trip) in
            // trip.trips[0].trip_id
            // trip.trips[0].isDeleted
            // trip.trips[0].isEnded
            // trip.trips[0].isStarted
            // trip.trips[0].createdAt
            // trip.trips[0].updatedAt
}) { (error) in
           // error.errorCode
         // error.errorMessage
   }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark activeTrips:^(ActiveTripsV2Response * trip) {
            // trip.trips[0].trip_id
            // trip.trips[0].isDeleted
            // trip.trips[0].isEnded
            // trip.trips[0].isStarted
            // trip.trips[0].createdAt
            // trip.trips[0].updatedAt
} onFailure:^(GeoSparkError * error) {
          // error.errorCode
         // error.errorMessage
   }];
```
{% endtab %}
{% endtabs %}

## **TrackLocationInAppState**

Using `trackLocationInAppState` method, one can configure the SDK settings for enabling location tracking during given App states.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.trackLocationInAppState([SETTINGS])

```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark trackLocationInAppState:@[SETTINGS]];
```
{% endtab %}
{% endtabs %}

| Parameter | Description |
| :--- | :--- |
| SETTINGS | GSAppState.AlwaysOn,GSAppState.Background, GSAppState.Foreground,GSAppState.Terminated |

## **TrackLocationInMotion**

Using `trackLocationInMotion` method, one can configure the SDK settings for enabling motion tracking.

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.trackLocationInMotion([SETTINGS])
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark trackLocationInMotion:@[SETTINGS]];
```
{% endtab %}
{% endtabs %}

| Parameter | Description |
| :--- | :--- |
| SETTINGS | GSMotion.All, GSMotion.Stationary, GSMotion.Running, GSMotion.Walking,GSMotion.AutoMotive |

## setLocationAccuracy

Using `setLocationAccuracy` method, one can set location tracking with accuracy \(5 to 100 meters\).

{% tabs %}
{% tab title="Swift" %}
```text
GeoSpark.setLocationAccuracy(accuracy)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark setLocationAccuracy:accuracy];
```
{% endtab %}
{% endtabs %}

## Notification Opened Handler

By using this method inside Notification delegate method, track the campaigns impressions and counts.

{% tabs %}
{% tab title="Swift" %}
```swift
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void)
        {
                GeoSpark.notificationOpenedHandler(response)
                completionHandler()
        }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
- (void)userNotificationCenter:(UNUserNotificationCenter *)center didReceiveNotificationResponse:(UNNotificationResponse *)response withCompletionHandler:(void (^)(void))completionHandler
    {
        [GeoSpark notificationOpenedHandler:response];
        completionHandler();
    }
```
{% endtab %}
{% endtabs %}

## **Logout User**

You can logout user by using `logoutUser` method.

**NOTE :** You need to reinitialize the SDK in case you want to login again.

{% tabs %}
{% tab title="Swift" %}
```swift
 GeoSpark.logoutUser({ (message) in
        // message
   }) { (error) in
         // error.errorCode
        // error.errorMessage
  }
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
 [GeoSpark logoutUser:^(NSString * message) {
            // message
    } onFailure:^(GeoSparkError * error) {
         // error.errorCode
        // error.errorMessage
    }];
```
{% endtab %}
{% endtabs %}

