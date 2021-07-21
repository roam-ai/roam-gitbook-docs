# Webhook

* First login to GeoSpark dashboard, select a project or create one and add apps in it.
* Add geofences for that project from the GeoSpark geofence page accessible via top navigation tabs. Enable the geofence status for triggering events, whenever the user using your app enters or exits the geofence.
* Go to the settings tab in the dashboard, where you will see options for webhook and slack integration. This again has an option that lets you choose which one you want to enable and actively use for the subscription.

![](../.gitbook/assets/webhook-integration.png)

* Now you can enable this feature by entering the respective URLs and please configure the same URL at your end for getting in your webhook or slack notifications.
* **NOTE:** These are the URLs you create from your slack and put them in the GeoSpark dashboard.
* After integration, you can monitor the users and geofence events.

Each POST request will consist of any one of the three objects.

1. Event - To notify geofence entry and exit events.
2. User - To notify user movement updates with respect to user activity. ie. Stop “S”, Moving “M”.
3. Trip - To notify trip start and end. 

{% hint style="info" %}
You can also receive real-time location events client-side via the SDK with _**`didUpdateLocation()`**_ which has less latency.
{% endhint %}

### **Sample webhook URL for notifications:**

```http
https://www.example.com/< YOUR-WEBHOOK-ENDPOINT >
```

#### **Response as input:**

```javascript
  {
  "event":  [
    {
      "user_id": "60b08d4f51efb00609f9afb1",
      "location_id": "60b08d5f1b9e3900007afb07",
      "geofence_id": "60af36958ce7db2395eb7a87",
      "recorded_at": "2021-05-28T06:27:43.080Z",
      "event_source": "geospark:geofence",
      "event_version": "1.0",
      "event_type": "geospark:geofence:Exit",
      "location": {
        "type": "Point",
        "coordinates": [
          85.06905784228388,
          25.605483727570086
        ]
      },
      "speed": 0,
      "course": 83.14997873855464,
      "altitude": 56.562080901085935,
      "activity": "M",
      "vertical_accuracy": null,
      "horizontal_accuracy": 88.64567615715366
    }
  ]
},
   {
  "coordinates":
   {
    "type": "Point",
    "coordinates": [
      85.06905784228388,
      25.605483727570086
    ]
  },
  "location_id": "60b08d5f1b9e3900007afb07",
  "recorded_at": "2021-05-28T06:27:43.080Z",
  "user_id": "60b08d4f51efb00609f9afb1",
  "event_version": "1.0",
  "event_source": "geospark:location",
  "event_type": "geospark:location:point",
  "speed": 0,
  "course": 83.14997873855464,
  "altitude": 56.562080901085935,
  "activity": "M",
  "vertical_accuracy": 71.87669804650587,
  "horizontal_accuracy": 88.64567615715366
},
 {
  "events": [
    {
      "user_id": "60b08d4f51efb00609f9afb1",
      "location_id": "60b08de376886500001e6827",
      "trip_id": "60b08da506f8a07362ca08bd",
      "trip_location_id": "60b08da506f8a07362ca08be",
      "recorded_at": "2021-05-28T06:29:55.729Z",
      "event_source": "geospark:trip",
      "event_version": "1.0",
      "event_type": "geospark:trip:reached_origin",
      "location": {
        "type": "Point",
        "coordinates": [
          85.0692907329729,
          25.605278502615263
        ]
      },
      "speed": 0,
      "course": -1,
      "altitude": 55.64597914647311,
      "activity": "S",
      "vertical_accuracy": null,
      "horizontal_accuracy": 5.027652817850262
    }
  ]
}
```

### \*\*\*\*

### **Sample slack URL for notifications:**

Slack can be added in a similar fashion as we are integrating webhooks.

```http
https://hooks.slack.com/services/T00000000/B00000000/XXXXXXXXXXXXXXXXXXXXXXXX
```

#### **Message format:**

```http
  Event Triggered:
  Type: entry
  User ID:  5bdad5f7eec1a507afa2fece
  User Description: John Doe
  Geofence ID: 5bc89a4feec1a44e738db309
  Geofence Description: John Office
  Recorded At: 2018-11-23T10:27:32.000
  Event ID: 5bed5a6e878b1b00012xaec5
```

