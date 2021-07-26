---
description: >-
  This page describes Roam authentication model, API endpoints, and error
  handling while using Roam APIs.
---

# Authorization

## Base URL

All URLs referenced in the API documentation will have the following base:

```http
https://api.roam.ai/v1/
```

REST APIs are served over HTTPS. To ensure data privacy, Roam discourages using unencrypted HTTP requests.

## API Use Cases <a id="API-Use-Cases"></a>

Here are some popular use cases with Roam APIs:

* **Can be used to view and do much more with your user data.**
  * Enables you to view user count per project.
  * Enables you to determine the device\(iOS/Android\) and application from which the hits are coming.
* **Can create, update, and delete Geofences, and trigger events on the fly**
  * Use geofences to create virtual for your structural properties on maps.
  * Track your users as they enter and exit geofences.
  * Understand user behavior and usage, as well as visit patterns.
* **Locations APIs for tracking your users' movement and activities.**
  * Know the users' location in real-time by just calling Roam APIs.
* **Trips APIs can be used to view your user trips and routes**
  * Track the trip of the user.
  * Fetch path of the trips along with the routes, mode of transportation, stop points, and offline status.

## Authentication

Roam uses an API Key based authentication passed using a custom header`Api-Key`for the APIs taking into consideration the safety of your API secret keys. We provide APIs on a per-project basis so that the projects are independent of each other's APIs.

## API Endpoints

Once your application is integrated with Roam SDK, an account for each user using your app will be created. Information about these users can be tracked through Roam APIs.

Here are the API endpoints available to interact with the user profile data:

{% page-ref page="users-api/" %}

{% page-ref page="locations-api/" %}

{% page-ref page="insights-api/" %}

{% page-ref page="trips-api/" %}

{% page-ref page="../geofencing/" %}

{% page-ref page="events-api/" %}

{% page-ref page="nearby-api/" %}

{% page-ref page="moving-geofence-api/" %}

{% page-ref page="group-api/" %}



