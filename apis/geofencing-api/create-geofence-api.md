---
description: >-
  The create Geofence API is responsible for creating geofences for project,
  users or groups.
---

# Create Geofence API

{% api-method method="post" host="https://api.geospark.co/v3/" path="api/geofence/" %}
{% api-method-summary %}
Create Geofence API
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
{% api-method-parameter name="group\_ids" type="array" required=false %}
Enables geofence for the list of users. If group\_ids and user\_ids are empty then geofence is enabled for all users of the project.  
**E.g.-** \["group1","group2"\]
{% endapi-method-parameter %}

{% api-method-parameter name="enable\_at" type="string" required=false %}
Time from when the geofence should be active.  
**Note:-** Required if `disable_at` field is present.  
**E.g.-** 2021-06-11T19:45:34
{% endapi-method-parameter %}

{% api-method-parameter name="disable\_at" type="string" required=false %}
Time till when the geofence should be active.  
**Note:-** Required if `enable_at` field is present  
**E.g.-** 2021-06-10T18:00:05
{% endapi-method-parameter %}

{% api-method-parameter name="user\_ids" type="array" required=false %}
Enables geofence for the list of users. If group\_ids and user\_ids are empty then geofence is enabled for all users of the project.  
**E.g.**-\["user1","user2"\]
{% endapi-method-parameter %}

{% api-method-parameter name="coordinates" type="array" required=true %}
Mandatory for creating the geofence.  
**E.g.**- \[ -72.28122, 42.926042 \]
{% endapi-method-parameter %}

{% api-method-parameter name="metadata" type="array" required=false %}
An optional set of custom key-value pairs for the geofence.
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_type" type="string" required=true %}
Defines the type of geometry.  
**E.g.**- circle
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_radius" type="integer" required=true %}
Defines the radius of circular geofence in meters. Range 50m to 1000m.  
\(Required only for geometry\_type circle. Field value ignored if sent when geometry\_type is a polygon.\)  
**E.g.**- 50m to 1000m max
{% endapi-method-parameter %}

{% api-method-parameter name="color\_code" type="string" required=false %}
Defines the color of Geofence and how it is displayed on the dashboard. Type: Hex Code for CSS colors.   
**Note:** Pass the code without '\#'.  
**E.g.**- ffffff
{% endapi-method-parameter %}

{% api-method-parameter name="tag" type="string" required=false %}
Tag the GeoFences for future reference and filtering.  
**E.g.**- hotel
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Optional description for the geofence.  
**E.g.**- This is just a 5 star cool hotel where you can stay.
{% endapi-method-parameter %}

{% api-method-parameter name="is\_enabled" type="boolean" required=false %}
Enable/Disable 'event\_trigger' for Geofences. By default event trigger are disabled.  
**E.g.**- true or false
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
    "msg": "Geofence Added successfully.",
    "code": 201,
    "data": {
        "id": "5f73326ce5fc231ba4b253eb",
        "account_id": "5bda16a2ea00845b3b419160",
        "project_id": "5bda16edea00845b3b419163",
        "geometry_type": "circle",
        "geometry_radius": 177,
        "geometry_center": {
            "type": "Point",
            "coordinates": [
                -72.28122,
                42.926042
            ]
        },
        "is_enabled": true,
        "is_deleted": false,
        "group_ids": ["5cda16edea00845b3b419173", "5f74326ce5fc231ba4b257eb"],
        "user_ids": ["6bda16edea01848b3b419163", "6373326ce5fc231ba4e253ea"],
        "enable_at": "2021-06-10T18:45:00",
        "disable_at": "2021-06-10T19:29:00"
        "created_at": "2020-09-29T13:11:08.702",
        "updated_at": "2020-09-29T13:11:08.702"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="GeofencingAPI-SampleRequest"></a>

```text
curl --location --request POST 'https://api.geospark.co/v3/api/geofence/' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88' \
--header 'Content-Type: application/json' \
--data-raw '{
	"geometry_type": "circle",
	"coordinates": [ -72.28122, 42.926042 ] ,
	"geometry_radius": 177,
	"group_ids": ["5cda16edea00845b3b419173", "5f74326ce5fc231ba4b257eb"],
  "user_ids": ["6bda16edea01848b3b419163", "6373326ce5fc231ba4e253ea"],
  "enable_at": "2021-06-10T18:45:00",
  "disable_at": "2021-06-10T19:29:00"
	"is_enabled": true
}'
```

