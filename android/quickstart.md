---
description: Integrate our SDK in your android app.
---

# Quickstart

## Step 1 : Install SDK

Install the SDK to your project via `Gradle` in Android Studio and add the dependencies below in your `app build.gradle` file.

```groovy
 dependencies {
   implementation'com.geospark.android:geospark:2.2.5' 
 }
```

## Step 2: Initialize SDK

Initialize the SDK with your `PublishKey`.

{% tabs %}
{% tab title="Java" %}
```java
//In onCreate method of your Application class include the code below.
public void onCreate() {
    super.onCreate();
    GeoSpark.initialize(this, "PUBLISH_KEY");
    ...
}    
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
override fun onCreate() {
  super.onCreate()
  GeoSpark.initialize(this, "PUBLISH_KEY")
  ...
}
```
{% endtab %}
{% endtabs %}

## Step 3: Create user

GeoSpark SDK needs a User ID object to identify the device.

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

## Step 4: **Start Location Tracking**

 To start tracking the location.

{% tabs %}
{% tab title="Java" %}
```java
//To enable location, call the requestLocationPermissions and 
//requestLocationServices method.
if(!GeoSpark.checkLocationPermission(this)) {
  	GeoSpark.requestLocationPermission(this);
} else if (!GeoSpark.checkLocationServices(this)) {
  	GeoSpark.requestLocationServices(this);
} else{
  	//Call this method to start tracking the location.  
  	GeoSpark.startTracking(this);
}      

```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
//To enable location, call the requestLocationPermissions and 
//requestLocationServices method.
if(!GeoSpark.checkLocationPermission(this)) {
  	GeoSpark.requestLocationPermission(this)
} else if (!GeoSpark.checkLocationServices(this)) {
  	GeoSpark.requestLocationServices(this)
} else{
  	//Call this method to start tracking the location.  
  	GeoSpark.startTracking(this)
}   
```
{% endtab %}
{% endtabs %}

To start tracking the location above Android 10

{% tabs %}
{% tab title="Java" %}
```java
if (!GeoSpark.checkActivityPermission(this)) {
    GeoSpark.requestActivityPermission(this);
} else if (!GeoSpark.checkLocationPermission(this)) {
    GeoSpark.requestLocationPermission(this);
} else if (!GeoSpark.checkBackgroundLocationPermission(this)) {
    GeoSpark.requestBackgroundLocationPermission(this);
} else if (!GeoSpark.checkLocationServices(this)) {    
GeoSpark.requestLocationServices(this);
} else {    
    GeoSpark.startTracking(this);
}
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
if (!GeoSpark.checkActivityPermission(this)) {
    GeoSpark.requestActivityPermission(this)
} else if (!GeoSpark.checkLocationPermission(this)) {
    GeoSpark.requestLocationPermission(this)
} else if (!GeoSpark.checkBackgroundLocationPermission(this)) {
    GeoSpark.requestBackgroundLocationPermission(this)
} else if (!GeoSpark.checkLocationServices(this)) {    
GeoSpark.requestLocationServices(this)
} else {    
    GeoSpark.startTracking(this)
}
```
{% endtab %}
{% endtabs %}



