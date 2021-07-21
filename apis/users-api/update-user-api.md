---
description: This API lets you update the details of a user_id.
---

# Update User API

{% api-method method="put" host="https://api.geospark.co/v3" path="/api/user/" %}
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
        "id": "60058ad6ffb3fb21c905a0b4",
        "account_id": "5ede06d73722791c17f27272",
        "app_id": "5ef070ce1e621663c53bb3c6_2",
        "device_token": "devicetoken",
        "device_uuid": null,
        "description": "POPOPOPO",
        "brand": "Samsung",
        "model": "S8",
        "group_id": null,
        "os_version": "8.1",
        "sdk_version": "2.1",
        "device_arn": null,
        "geofence_events": true,
        "motion_events": false,
        "location_events": false,
        "trips_events": true,
        "nearby_events": false,
        "location_listener": false,
        "event_listener": false,
        "metadata": {
            "name": "rahul"
        },
        "is_deleted": false,
        "created_at": "2021-01-18T13:19:18.181",
        "updated_at": "2021-01-18T13:28:28.132"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="UsersAPI-SampleRequest.1"></a>

```text
curl --location --request PUT 'https://api.geospark.co/v3/api/user/' \
--header 'Content-Type: application/json' \
--header 'APi-Key: f4441682ed03441eb906693a3bde8979' \
--data-raw '{
	"user_id": "60058ad6ffb3fb21c905a0b4",
	"description": "POPOPOPO",
    "metadata" :{"name": "rahul" }
}'
```

