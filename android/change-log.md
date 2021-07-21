---
description: Keep yourself updated.
---

# Changelog

## v2.2.5 - \(March 24, 2020\)

**Modified**

* Changed GeoSparkEventsCallback to GeoSparkCallback in toggleEvents and getEventsStatus ****methods.
* Changed GeoSparkTripsCallBack to GeoSparkTripCallBack in activeTrips method.

#### Fixed

* Bug fixes and preformation updates.

## v2.2.4 - \(March 04, 2020\)

#### Fixed

* Bug fixes and preformation updates.

## v2.2.3 - \(Dec 03, 2019\)

#### Fixed

* Minor bug fixes and preformation updates.

## v2.2.1 - \(Oct 10, 2019\)

#### Added

* New utility method to enable activity and background location permission for Android 10.

## v2.1.1 - \(Sep 05, 2019\)

**Added**

* New utility method to toggle user events and get user events status.

**Modified**

* Minor bug fixes and preformation updates.

## v2.0.0 - \(June 28, 2019\)

**Added**

* New utility method Notification Opened Handler.

**Modified**

* Redesigns the SDK under the hood to maximize reliability, efficiency, and making integration simple.

## v1.11 - \(May 06, 2019\)

**Added**

* Update SDK Method for Trips V2.

## v1.9 - \(March 29, 2019\)

#### Added

* New utility method to update user's current location. 
* New utility method to check if location tracking is started.

## v1.8 - \(March 22, 2019\)

**Added**

Added a new method **`onError`** under GeoSparkReceiver which will receive all the error codes with description.

**Removed**

Removed the method **`isMockEnabledinDevice`** which was used to check if mock application is enabled in the device. This method is replace with receiver for errors.

## v1.7 - \(February 27, 2019\)

**Added**

* New utility method to disable battery optimization.
* New utility method to check battery optimization.
* New utility method to check mock enabled.

## v1.5 - \(January 31, 2019\)

**Added**

* New utility method to get user’s current location.

**Modified**

* To customize the service notification.

**Fixed**

* Improved location tracking.

## v1.4 - \(January 22, 2019\)

Improvement in location tracking with better crash log support.

## v1.3 - \(December 27, 2018\)

Major and minor bug fixes.

## v1.2 - \(November 29, 2018\)

Added DeleteGeofence method.

Added Logout method.

Added SetDescription method.

Major and minor bug fixes.

## v1.1 - \(November 21, 2018\)

Major and minor bug fixes.

## v1.0 - \(October 31, 2018\)

### **Offline Location Updates Method**

We reliably track location offline and upload to server whenever connection is established back to internet. This feature helps to provide seamless tracking irrespective of internet connectivity issues

### **Trips**

Manage trips through SDK using 'Start Trip' & 'End Trip'.

Also track your trips as well using trip routes.

### **Geofence**

Using SDK can create personalised geofence & get those geofence list.



