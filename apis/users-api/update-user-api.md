---
description: This API lets you update the details of a user_id.
---

# Update User API

{% api-method method="put" host="https://api.roam.ai/v1" path="/api/user/" %}
{% api-method-summary %}
Update User API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.**- 33223kjhdcscijhb5sdbsdmjsdcbj5f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user\_id" type="string" required=true %}
Enable or disable events data for the given user\_id.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Update user description.  
**E.g.**- “test user”
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_events" type="boolean" required=false %}
Enable or disable geofence\_events.  
**E.g.**- true
{% endapi-method-parameter %}

{% api-method-parameter name="trips\_events" type="boolean" required=false %}
Enable or disable trips\_events.  
**E.g.**- true
{% endapi-method-parameter %}

{% api-method-parameter name="location\_events" type="boolean" required=false %}
Enable or disable location\_events.  
**E.g.**- true
{% endapi-method-parameter %}

{% api-method-parameter name="nearby\_events" type="boolean" required=false %}
Enable or disable nearby\_events.  
**E.g.**- true
{% endapi-method-parameter %}

{% api-method-parameter name="event\_listener" type="boolean" required=false %}
Enable or disable event\_listener.  
**E.g.**- true
{% endapi-method-parameter %}

{% api-method-parameter name="location\_listener" type="boolean" required=false %}
Enable or disable location\_listener.  
**E.g.**- true
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "status": true,
    "msg": "Success.",
    "code": 200,
    "data": {
        "id": "60b90dd651efb070950db2e9",
        "account_id": "60af304c51efb03cdde65042",
        "app_id": "60af306a8ce7db2392eb7a75_1",
        "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
        "device_uuid": null,
        "description": "ROAM111",
        "brand": "xiaomi",
        "model": "Redmi Note 7",
        "group_id": null,
        "os_version": "28",
        "sdk_version": "3.1.6",
        "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
        "geofence_events": false,
        "motion_events": false,
        "location_events": false,
        "trips_events": false,
        "nearby_events": false,
        "location_listener": false,
        "event_listener": false,
        "metadata": {
            "name": "ROAM123"
        },
        "is_deleted": false,
        "created_at": "2021-06-03T17:13:58.830",
        "updated_at": "2021-07-02T07:44:38.781"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="UsersAPI-SampleRequest.1"></a>

```text
curl --location --request PUT 'https://api.roam.ai/v1/api/user/' \
--header 'Content-Type: application/json' \
--header 'APi-Key: 63598c5b3aa84f14914013709402bbc9' \
--data-raw '{
  "user_id": "60b90dd651efb070950db2e0",
  "description": "ROAM111",
  "metadata" :{"name": "ROAM123" },
  "geofence_events": false,
  "motion_events": false,
  "location_events": false,
  "trips_events": false,
  "nearby_events": false,
  "location_listener": false,
  "event_listener": false
}'
```

