---
description: >-
  Use this API to update details for an existing geofence of any specific
  project using Update Geofence API.
---

# UPDATE Geofence API

{% api-method method="put" host="https://api.roam.ai" path="/v1/api/geofence/" %}
{% api-method-summary %}
Update Geofence API
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
{% api-method-parameter name="geofence\_id" type="string" required=true %}
geofence\_id which needs to be updated  
**E.g.-** 6dba14deda01857c3c418265
{% endapi-method-parameter %}

{% api-method-parameter name="group\_ids" type="array" required=false %}
Enables geofence for the list of users. If group\_ids and user\_ids are empty then geofence is enabled for all users of the project.  
**E.g.-** \["group1","group2"\]
{% endapi-method-parameter %}

{% api-method-parameter name="user\_ids" type="array" required=false %}
Enables geofence for the list of users. If group\_ids and user\_ids are empty then geofence is enabled for all users of the project.  
**E.g.**-\["user1","user2"\]
{% endapi-method-parameter %}

{% api-method-parameter name="coordinates" type="array" required=false %}
Mandatory for creating the geofence.  
**E.g.**- \[ -72.28122, 42.926042 \]
{% endapi-method-parameter %}

{% api-method-parameter name="metadata" type="object" required=false %}
An optional set of custom key-value pairs for the geofence.
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_type" type="string" required=false %}
Defines the type of geometry.  
**E.g.**- circle
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_radius" type="integer" required=false %}
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
Tag the Geofences for future reference and filtering.  
**E.g.**- hotel
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Optional description for the geofence.  
**E.g.**- This is just a 5 star cool hotel where you can stay.
{% endapi-method-parameter %}

{% api-method-parameter name="is\_enabled" type="array" required=false %}
Array with first index depicting whether the geofence is enabled or disabled, second index depicting the start\_time and last index depicting the end\_time between which the geofence should be active.  
**E.g.**- \[true,"2021-06-10T20:45:44", "2021-06-15T22:45:33"\]
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
    "msg": "Geofence updated successfully.",
    "code": 200,
    "data": {
        "geofence_id": "6dba14deda01857c3c418265",
        "geometry_radius": 177,
        "geometry_center": {
            "type": "Point",
            "coordinates": [
                -72.28122,
                42.926042
            ]
        },
    "is_enabled": [true, "2021-06-10T18:45:00", "2021-06-10T19:29:00"],
    "user_ids": ["6bda16edea01848b3b419163"],
    "group_ids": ["5cda16edea00845b3b419173"],
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
curl --location --request PUT 'https://api.roam.ai/v1/api/geofence/' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88' \
--header 'Content-Type: application/json' \
--data-raw '{
	"geofence_id": "6dba14deda01857c3c418265",
	"coordinates": [ -72.28122, 42.926042 ] ,
	"geometry_radius": 177,
	"description": "Roam Amsterdam HQ",
	"tag": "Office",
	"metadata": {},
  "user_ids": ["6bda16edea01848b3b419163"],
  "group_ids": ["5cda16edea00845b3b419173"],
	"is_enabled": [true, "2021-06-10T18:45:00", "2021-06-10T19:29:00"]
}'
```

