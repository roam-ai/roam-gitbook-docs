---
description: An archive of our SDK methods.
---

# Utility Methods

## **Initialize SDK**

Initialize the SDK with your `PublishKey`.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.initialize(this, "PUBLISH_KEY");
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.initialize(this, "PUBLISH_KEY")
```
{% endtab %}
{% endtabs %}

## Set DeviceToken  

GeoSpark SDK is capable of sending push notifications to your users. ****[Add Firebase to your Android project](https://firebase.google.com/docs/android/setup) to get device token. 

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.setDeviceToken(this, "FCM DeviceToken");
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.setDeviceToken(this, "FCM DeviceToken")
```
{% endtab %}
{% endtabs %}

## Get DeviceToken

To get `FCM DeviceToken` from SDK.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.getDeviceToken(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.getDeviceToken(this)
```
{% endtab %}
{% endtabs %}

## **Create user**

GeoSpark SDK needs a User ID object to identify the device. The SDK has a convenience method `createUser()` to create a user which returns User ID.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.createUser(this,"User Description", new GeoSparkCallBack() {
       @Override
       public void onSuccess(GeoSparkUser geoSparkUser) {
                   geoSparkUser.getUserId();
       }
       @Override
       public void onFailure(GeoSparkError geoSparkError) {
                   geoSparkError.getErrorCode();
                   geoSparkError.getErrorMessage();
       }
});
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.createUser(this, "User Description", object : GeoSparkCallBack {
    override fun onSuccess(geoSparkUser: GeoSparkUser) {
       geoSparkUser.userId
    }
    
    override fun onFailure(geoSparkError: GeoSparkError) {
       geoSparkError.errorCode
       geoSparkError.errorMessage
    }
})
```
{% endtab %}
{% endtabs %}

## **Get User**

If you already have a User ID object. The SDK has a convenience method `getUser()` to start the session for the existing user.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.getUser(this, "userId", new GeoSparkCallBack() {
     @Override
     public void onSuccess(GeoSparkUser geoSparkUser) {
                 geoSparkUser.getUserId();
     }
     @Override
     public void onFailure(GeoSparkError geoSparkError) {
                 geoSparkError.getErrorCode();
                 geoSparkError.getErrorMessage();
     }
});    
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.getUser(this, "userId", object : GeoSparkCallBack {
     override fun onSuccess(geoSparkUser: GeoSparkUser) {
         geoSparkUser.userId
     }
     
     override fun onFailure(geoSparkError: GeoSparkError) {
         geoSparkError.errorCode
         geoSparkError.errorMessage
     }  
})
```
{% endtab %}
{% endtabs %}

## **User description**

Adding description for the user makes it easier for you to identify your users, while tracking them in SDK. GeoSpark SDKs provide you with the option to modify the description any time for a user. This can also help you in easily identifying users on dashboard simply via the description.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.setDescription(this, "User Description", new GeoSparkCallBack() {
      @Override
      public void onSuccess(GeoSparkUser geoSparkUser) {
           geoSparkUser.getUserId();
      }
      @Override
      public void onFailure(GeoSparkError geoSparkError) {
          geoSparkError.getErrorCode();
          geoSparkError.getErrorMessage();
      }
});    
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.setDescription(this, "User Description", object : GeoSparkCallBack {
     override fun onSuccess(geoSparkUser: GeoSparkUser) {
         geoSparkUser.userId
     }
     
     override fun onFailure(geoSparkError: GeoSparkError) {
         geoSparkError.errorCode
         geoSparkError.errorMessage
     }
})
```
{% endtab %}
{% endtabs %}

## Toggle User Events

Use this method after user creation to enable user events for geofence, activity and trips. By default, all user events will be disabled post user creation.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.toggleEvents(this, geofence, trip, activity, newGeoSparkCallBack() {
    @Override 
    public void onSuccess(GeoSparkUser geoSparkUser) {
            geoSparkUser.isActivityEventsActive();
            geoSparkUser.isGeofenceEventsActive();
            geoSparkUser.isTripEventsActive();     
    }
    @Override
    public void onFailure(GeoSparkErrorgeoSparkError) {
            geoSparkError.getErrorCode();
            geoSparkError.getErrorMessage();     
    }
});
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.toggleEvents(this, geofence, trip, activity, object: GeoSparkCallBack
{
    override fun onSuccess(geoSparkUser: GeoSparkUser) {
        geoSparkUser.isActivityEventsActive
        geoSparkUser.isGeofenceEventsActive
        geoSparkUser.isTripEventsActive     
    }
    override fun onFailure(geoSparkError: GeoSparkError) {
        geoSparkError.errorCode
        geoSparkError.errorMessage     
    }
})
```
{% endtab %}
{% endtabs %}

## Get User Event Status

Use this method after user creation to get the current status of user events for geofence, activity and trips

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.getEventsStatus(this, newGeoSparkCallBack() {
    @Override 
    public void onSuccess(GeoSparkUsergeoSparkUser) {
        geoSparkUser.isActivityEventsActive();
        geoSparkUser.isGeofenceEventsActive();
        geoSparkUser.isTripEventsActive();  
    }
    @Override
    public void onFailure(GeoSparkErrorgeoSparkError) {
        geoSparkError.getErrorCode();
        geoSparkError.getErrorMessage();  
    }
});
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.getEventsStatus(this, object: GeoSparkCallBack {
        override fun onSuccess(geoSparkUser: GeoSparkUser) {
                geoSparkUser.isActivityEventsActive
                geoSparkUser.isGeofenceEventsActive
                geoSparkUser.isTripEventsActive    
        } 
        override fun onFailure(geoSparkError: GeoSparkError) {
                geoSparkError.errorCode
                geoSparkError.errorMessage    
        }
})
```
{% endtab %}
{% endtabs %}

## **Check location permission**

Check whether your App has location permission. Returns a boolean, which is `true` if the location permission has been granted, and `false` otherwise.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.checkLocationPermission(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```
GeoSpark.checkLocationPermission(this)
```
{% endtab %}
{% endtabs %}

## **Check location services**

Check whether the device has location services enabled. Returns a boolean, which is `true` if the location location services is ON, and `false` otherwise.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.checkLocationServices(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.checkLocationServices(this)
```
{% endtab %}
{% endtabs %}

## Check Activity Permission

Check whether your App has activity permission. Returns a boolean, which is `true` if the activity permission has been granted, and `false` otherwise.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.checkActivityPermission(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.checkActivityPermission(this)
```
{% endtab %}
{% endtabs %}

## Check Background Location Permission

Check whether your App has background location permission. Returns a boolean, whichis `true` if the background location permission has been granted, and `false` otherwise.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.checkBackgroundLocationPermission(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.checkBackgroundLocationPermission(this)
```
{% endtab %}
{% endtabs %}

## **Request location permissions**

Call this method to request user to enable location permissions.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.requestLocationPermission(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.requestLocationPermission(this)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Java" %}
```java
//Callback from request location permission method.
@Override
public void onRequestPermissionsResult(int requestCode, String permissions[], int[] grantResults) {
   switch (requestCode) {
      case GeoSpark.REQUEST_CODE_LOCATION_PERMISSION:
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            ...
         } else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {
            ...   
         }
      break;
   }
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onRequestPermissionsResult(requestCode: Int, permissions:
    Array<String>, grantResults:IntArray) {
        when (requestCode) {
            GeoSpark.REQUEST_CODE_LOCATION_PERMISSION->
            if (grantResults[0] ==PackageManager.PERMISSION_GRANTED) {
            ....
            } else if (grantResults[0] ==PackageManager.PERMISSION_DENIED) {
            ....
            }
        }
}
```
{% endtab %}
{% endtabs %}

\*\*\*\*

## **Request location services**

Call this method to enable location services.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.requestLocationServices(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.requestLocationServices(this)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Java" %}
```java
//Callback from request location services method.
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
   super.onActivityResult(requestCode, resultCode, data);
   if (requestCode == GeoSpark.REQUEST_CODE_LOCATION_ENABLED) {
   }
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?)
{
     super.onActivityResult(requestCode, resultCode, data)
     if (requestCode == GeoSpark.REQUEST_CODE_LOCATION_ENABLED) {
           ....
     }
}
```
{% endtab %}
{% endtabs %}

## Request Activity Permission

Call this method to request user to enable activity permissions.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.requestActivityPermission(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.requestActivityPermission(this)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Java" %}
```java
//Callback from request activity permission method.
@Override
public void onRequestPermissionsResult(intrequestCode, Stringpermissions[],
int[] grantResults) {
    switch (requestCode) {
        case GeoSpark.REQUEST_CODE_ACTIVITY_PERMISSION:
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) { 
            ...      
        } 
        else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {
             ...        
        }
        break;   
    }
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onRequestPermissionsResult(requestCode: Int, permissions:
Array<String>, grantResults: IntArray) {
    when (requestCode) {
        GeoSpark.REQUEST_CODE_ACTIVITY_PERMISSION->
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            ....
        } 
        else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {
            ....
        }
    }
}
```
{% endtab %}
{% endtabs %}

## Request Background Location Permission

Call this method to request user to enable background location permissions.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.requestBackgroundLocationPermission(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.requestBackgroundLocationPermission(this)
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Java" %}
```java
//Callback from request background location permission method.
@Override
public void onRequestPermissionsResult(intrequestCode, Stringpermissions[],
int[] grantResults) {
    switch (requestCode) {
        case GeoSpark.REQUEST_CODE_BACKGROUND_LOCATION_PERMISSION:
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {  
               ...      
        } 
        else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {         
                ...        
        }
        break;   
    }
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onRequestPermissionsResult(requestCode: Int, permissions:
Array<String>, grantResults: IntArray) {
    when (requestCode) {
    GeoSpark.REQUEST_CODE_BACKGROUND_LOCATION_PERMISSION->
        if (grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            ...
        } 
        else if (grantResults[0] == PackageManager.PERMISSION_DENIED) {
            ...
        }
    }
}
```
{% endtab %}
{% endtabs %}

## **Start location tracking**

To start tracking the user location.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.startTracking(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.startTracking(this)
```
{% endtab %}
{% endtabs %}

## Check Location Tracking

Check whether location tracking is started or not. This method returns boolean value.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.isLocationTracking(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.isLocationTracking(this)
```
{% endtab %}
{% endtabs %}

## **Stop location tracking**

You can stop tracking the user location.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.stopTracking(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.stopTracking(this)
```
{% endtab %}
{% endtabs %}

## **Location listener**

To listen for location in the background, create a class that extends `GeoSparkReceiver`. Then, register the `receiver` by adding a receiver element to the `application` element in your manifest.

{% tabs %}
{% tab title="Java" %}
```java
public class MyGeoSparkReceiver extends GeoSparkReceiver {
    @Override
    public void onLocationUpdated(Context context, Location location,
                GeoSparkUser geoSparkUser, String activity){
         // do something with context, location, userId, activity
    }
    @Override
    public void onError(Context context, GeoSparkError geoSparkError) { 
            geoSparkError.getErrorCode();
            geoSparkError.getErrorMessage();
    }
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
class MyGeoSparkReceiver : GeoSparkReceiver() {
    override fun onLocationUpdated(context: Context, location: Location,
                geoSparkUser: GeoSparkUser, activity:String) 
    {
             // do something with context, location, userId, activity
    }

    override fun onError(context: Context, geoSparkError: GeoSparkError) 
    {
             geoSparkError.errorCode
             geoSparkError.errorMessage
    }
}
```
{% endtab %}
{% endtabs %}

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

## **Current Location**

Get current location of the user. You can set the accuracy from 20 to 100 meters \(default is 20\).

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.getCurrentLocation(this, accuracy, 
                            new GeoSparkLocationCallback(){
    @Override
    public void location(double latitude, double longitude, double accuracy) {
       
    }
    @Override
    public void onFailure(GeoSparkError geoSparkError) {
        geoSparkError.getErrorCode();
        geoSparkError.getErrorMessage();
    }
});
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.getCurrentLocation(this, accuracy, object : GeoSparkLocationCallback {
     override fun location(latitude: Double, longitude: Double, accuracy:
         Double) 
     {
     }
     
     override fun onFailure(geoSparkError: GeoSparkError) 
     {
         geoSparkError.errorCode
         geoSparkError.errorMessage
     }
})
```
{% endtab %}
{% endtabs %}

## Update Current Location

Using `updateCurrentLocation` method, one can update user current location, you can set the accuracy from 15 to 100 meters \(default is 15\).

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.updateCurrentLocation(this, accuracy);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.updateCurrentLocation(this, accuracy)
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
This method should be used only if you need to update the current location of the device with better accuracy. Using this method often might consume battery.
{% endhint %}

## **Start Trip**

Start trips in Geospark SDK, using `startTrip()` method.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.startTrip(this, "tripId", "Description", new GeoSparkTripCallBack() {
    @Override public void onSuccess(GeoSparkTrip geoSparkTrip) {
        geoSparkTrip.getMsg();
    }
    @Override public void onFailure(GeoSparkError geoSparkError) {
        geoSparkError.getErrorCode();
        geoSparkError.getErrorMessage();
    }
});
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.startTrip(this, "tripId", "Description", object : GeoSparkTripCallBack
{
    override fun onSuccess(geoSparkTrip: GeoSparkTrip) 
    {
        geoSparkTrip.msg
    }
    
    override fun onFailure(geoSparkError: GeoSparkError) 
    {
         geoSparkError.errorCode
         geoSparkError.errorMessage
    }
})
```
{% endtab %}
{% endtabs %}

## **End Trip**

End trips in Geospark SDK, using `endTrip()` method.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.endTrip(this, "tripId", new GeoSparkTripCallBack() {
     @Override
     public void onSuccess(GeoSparkTrip geoSparkTrip) {
                 geoSparkTrip.getMsg();
     }
     @Override
     public void onFailure(GeoSparkError geoSparkError) {
                 geoSparkError.getErrorCode();
                 geoSparkError.getErrorMessage();
     }
});        
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.endTrip(this, "tripId", object : GeoSparkTripCallBack {
    override fun onSuccess(geoSparkTrip: GeoSparkTrip) {
        geoSparkTrip.msg
    }
    
    override fun onFailure(geoSparkError: GeoSparkError) {
         geoSparkError.errorCode
         geoSparkError.errorMessage
    }
})
```
{% endtab %}
{% endtabs %}

## **Active Trips**

Get active trips in GeoSpark SDK, using `activeTrips()` method.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.activeTrips(this, new GeoSparkTripCallBack() {
    @Override 
    public void onSuccess(GeoSparkTrip geoSparkTrip) {
        geoSparkTrip.getGeoSparkActiveTrips();    
    }
    @Override
    public void onFailure(GeoSparkErrorgeoSparkError) {
        geoSparkError.getErrorCode();
        geoSparkError.getErrorMessage();    
    }
});      
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.activeTrips(this, object : GeoSparkTripCallBack {
    override fun onSuccess(geoSparkTrip: GeoSparkTrip) {
        geoSparkTrip.geoSparkActiveTrips     
    }
    override fun onFailure(geoSparkError: GeoSparkError) {
        geoSparkError.errorCode 
        geoSparkError.errorMessage     
    }
})
```
{% endtab %}
{% endtabs %}

## **setTrackingInAppState**

Call this method to configure GeoSpark SDK settings for enabling location tracking during given app states.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.setTrackingInAppState(this, new GeoSpark.Type[]{Settings}); 
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.setTrackingInAppState(this, arrayOf(Settings))
```
{% endtab %}
{% endtabs %}

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Parameter</b>
      </th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SETTINGS</td>
      <td style="text-align:left">
        <p>Option 1 : GeoSpark.Type.FOREGROUND (OR) GeoSpark.Type.BACKGROUND</p>
        <p>Option 2 : GeoSpark.Type.ALWAYS_ON</p>
      </td>
    </tr>
  </tbody>
</table>

## **setTrackingInMotion**

Call this method to configure GeoSpark SDK settings for enabling location tracking during given motion tracking.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.setTrackingInMotion(this, new GeoSpark.Type[]{Settings});
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.setTrackingInMotion(this, arrayOf(Settings))
```
{% endtab %}
{% endtabs %}

| **Parameter** | Description |
| :--- | :--- |
| SETTINGS | Option 1 - GeoSpark.Type.STOP \(OR\) GeoSpark.Type.WALK \(OR\) GeoSpark.Type.RUNNING \(OR\) GeoSpark.Type.BICYCLE \(OR\) GeoSpark.Type.DRIVE Option 2 - GeoSpark.Type.ALL |

## Notification Opened Handler

By using this method inside FirebaseMessagingService class, track the campaigns impressions and counts.

{% tabs %}
{% tab title="Java" %}
```java
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
   super.onMessageReceived(remoteMessage);
   NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
   ...
   intent.putExtra(GeoSpark.EXTRA, GeoSpark.notificationReceiveHandler(remoteMessage.getData()));
   ...
   notificationManager.notify(NotificationID, builder.build());
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onMessageReceived(RemoteMessage remoteMessage) {
     super.onMessageReceived(remoteMessage)
        val notificationManager =
        getSystemService(Context.NOTIFICATION_SERVICE) as
        NotificationManager
        
           ....
           
          intent.putExtra(GeoSpark.EXTRA,

GeoSpark.notificationReceiveHandler(remoteMessage.getData()))
 ....
}
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Java" %}
{% code title="MainActivity.java" %}
```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    ...
    GeoSpark.notificationOpenedHandler(this, getIntent());
}
```
{% endcode %}
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
      ....
    GeoSpark.notificationOpenedHandler(this, intent)
)
```
{% endtab %}
{% endtabs %}

## **Logout**

Logout from GeoSpark SDK, using `logout()` method.

**NOTE :** You need to reinitialize the SDK in case you want to login again.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.logout(this, new GeoSparkLogoutCallBack() {
      @Override
      public void onSuccess(String message) {
                ...
      }
      @Override
      public void onFailure(GeoSparkError geoSparkError) {
           geoSparkError.getErrorCode();
           geoSparkError.getErrorMessage();
      }
});     
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.logout(this, object : GeoSparkLogoutCallBack {
        override fun onSuccess(message: String) {
            ....
        }
        
         override fun onFailure(geoSparkError: GeoSparkError) {
             geoSparkError.errorCode
             geoSparkError.errorMessage
     }
})
```
{% endtab %}
{% endtabs %}

## **Disable Battery Optimization \(android 6+\)**

When running the SDK on Android 6 \(and higher\), it is recommended to ask the user to disable battery optimization for your application. This makes sure that detections continue to work properly when the device is in Doze mode. Moreover, on Android Pie, it prevents Adaptive Battery from [bucketing](https://developer.android.com/about/versions/pie/power#buckets) your app based on usage and [restricting background processing](https://developer.android.com/reference/android/app/ActivityManager#isBackgroundRestricted), all of which that can impact the detection quality of the SDK.

After explaining to the user about the benefits of disabling battery optimization, call the `disableBatteryOptimization()` method of the GeoSpark class.

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.disableBatteryOptimization(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.disableBatteryOptimization(this)
```
{% endtab %}
{% endtabs %}

This will trigger a system dialog asking the user to allow disabling battery optimization for your app.

## **Check Battery Optimization**

{% tabs %}
{% tab title="Java" %}
```java
GeoSpark.isBatteryOptimizationEnabled(this);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
GeoSpark.isBatteryOptimizationEnabled(this)
```
{% endtab %}
{% endtabs %}



