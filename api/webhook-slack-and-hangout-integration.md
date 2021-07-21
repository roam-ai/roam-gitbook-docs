# Webhook and Slack Integration

Slack can be added in a similar fashion as we are integrating webhooks.

Below are the steps:

* First login to GeoSpark dashboard, select a project or create one and add apps in it.
* Add geofences for that project from GeoSpark geofence page accessible via top navigation tabs. Enable the geofences status for triggering events, whenever the user using your app enters or exits the geofence.
* Go to settings tab in dashboard, where you will see options for webhook and slack integration. This again has an option which lets you choose which one you want to enable and actively use for subscription.
* Now you can enable this feature by entering the respective URLs and please configure the same URL at your end for getting in your webhook or slack notifications.
* **NOTE :** These are the URL's you create from your slack and put it in GeoSpark dashboard.
* After integration you can monitor the users and geofence events.

Each POST request will consist of any one of the three objects.

1. Event - To notify geofence entry and exit events.
2. User - To notify user movement updates with respect to user activity. ie. Stop, Walking, Running and Driving.
3. Trip - To notify trip start and end.

{% hint style="info" %}
You can also receive real time location events client-side via the SDK with _**`didUpdateLocation()`**_ which has less latency.
{% endhint %}

### **Sample webhook url for notifications:**

```http
https://www.example.com/< YOUR-WEBHOOK-ENDPOINT >
```

#### **Response as input:**

{% code title="JSON" %}
```javascript
 {
  "event": {
    "id": "56db1f4613012711002229f6",
    "recorded_at": "2018-06-12T13:44:10.535Z",
    "type": "entry",
    "user": {
      "id": "56db1f4613012711002229f4",
      "description": "Jane Doe"
    },
    "geofence": {
      "id": "5bc89a4feec1a44e738db309",
      "tag": "neighborhood",
      "description": "Jane's Home"
    },
    "location": {
      "type": "Point",
      "coordinates": [
        -73.977797,
        40.783826
      ]
    },
    "accuracy": 5
  },
  "user": {
    "id": "5bdad5f7eec1a507afa2fece",
    "description": "Jane Doe",
    "recorded_at": "2018-06-12T13:44:10.535Z",
    "created_at": "2018-06-10T11:23:58.741Z",
    "location": {
      "type": "Point",
      "coordinates": [
        -73.977797,
        40.783826
      ]
    },
    "speed": 6,
    "accuracy": 65,
    "battery_remaining": 45,
    "altitude": 234,
    "motion_state": "walk",
    "app_state": false,
    "device_type": "iOS"
  },
  "trip": {
    "id": "5bd8db1cea008447a0e2b5a8",
    "description": "Jane Trip",
    "started_at": "2018-06-12T13:44:10.535Z",
    "ended_at": "2018-06-12T13:44:10.535Z",
    "type": "start",
    "user": {
      "id": "56db1f4613012711002229f4",
      "description": "Jane Doe"
    },
    "location": {
      "type": "Point",
      "coordinates": [
        -73.977797,
        40.783826
      ]
    },
    "accuracy": 5
  }
}
```
{% endcode %}

### **Sample slack url for notifications:**

```http
https://hooks.slack.com/services/T00000000/B00000000/XXXXXXXXXXXXXXXXXXXXXXXX
```

#### **Message format:**

{% code title="Text" %}
```text
  Event Triggered:
  Type: entry
  User ID:  5bdad5f7eec1a507afa2fece
  User Description: John Doe
  Geofence ID: 5bc89a4feec1a44e738db309
  Geofence Description: John Office
  Recorded At: 2018-11-23T10:27:32.000
  Event ID: 5bed5a6e878b1b00012xaec5
```
{% endcode %}

