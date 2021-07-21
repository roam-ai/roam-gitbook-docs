---
description: >-
  GeoSpark provides a set of REST API's which will help you to do more with our
  product.
---

# Quickstart

This page describes GeoSpark authentication model, API endpoints and error handling while using GeoSpark APIs.

## Base URL

All URLs referenced in the API documentation will have the following base:

```http
https://api.geospark.co/v1
```

REST APIs are served over HTTPS. To ensure data privacy, GeoSpark discourage using unencrypted HTTP requests.

## API Use Cases

Here are some popular use cases with GeoSpark APIs:

* **Can be used to view and do much more with your user data.**
  * Enables you to view user count per project.
  * Enables you to determine the device\(iOS/Android\) and application from which the hits are coming from.
* **Can create, update, and delete Geofences, and trigger events on the fly**
  * Use geofences to create virtual for your structural properties on maps.
  * Track your users as they enter and exit geofences.
  * Understand user behaviour and usage, as well as visit patterns.
* **Locations APIs for tracking your users movement and activities.**
  * Know the users location in real time by just calling GeoSpark APIs.
* **Trips APIs can be used to view your user trips and routes**
  * Track the trip of the user.
  * Fetch path of the trips along with the routes,mode of transportation, stop points and offline status.

## Authentication

GeoSpark use a basic authentication for the APIs taking into consideration the safety of your API secret keys. We provide APIs on a per project basis so that the projects are independent of each other's APIs.

## API Endpoints

Once your application is integrated with GeoSpark SDK, account for each user using your app will be created. Information about these users can be tracked through GeoSpark APIs.

Here are the API endpoints available to interact with the user profile data:

{% page-ref page="users.md" %}

{% page-ref page="events.md" %}

{% page-ref page="trips.md" %}

{% page-ref page="geofences.md" %}

