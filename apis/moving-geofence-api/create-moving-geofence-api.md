---
description: >-
  The create Moving Geofence API is responsible for creating moving-geofences
  for projects.
---

# Create Moving-Geofence API

{% api-method method="post" host="https://api.roam.ai/v1" path="/api/moving-geofence/" %}
{% api-method-summary %}
Create Moving-Geofence API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.**- 332223kfhdjahsiebjsb5s
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="users" type="array" required=true %}
Array of user\_ids to create moving-geofences.  
**E.g.**- \["5f520949e3872b0341bcf3e7", "5f520955e3872b0341bcf3e8", "5f083247b3611453c98a726f"\]
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
**E.g**.- This is just a 5-star cool hotel where you can stay.
{% endapi-method-parameter %}

{% api-method-parameter name="is\_enabled" type="boolean" required=false %}
Enable/Disable 'event\_trigger' for Geofences. By default event triggers are disabled.  
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
        "id": "5f9801aeffb3fb0de55e863d",
        "account_id": "5bda16a2ea00845b3b419160",
        "project_id": "5bda16edea00845b3b419163",
        "geometry_type": "circle",
        "geometry_radius": 500,
        "is_enabled": true,
        "is_deleted": false,
        "created_at": "2020-10-27T11:17:02.956",
        "updated_at": "2020-10-27T11:17:02.959",
        "only_once": true,
        "users": [
            "5f520949e3872b0341bcf3e7",
            "5f520955e3872b0341bcf3e8"
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="Sample-Request"></a>

```text
curl --location --request POST 'https://api.roam.ai/v1/api/moving-geofence/' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88' \
--header 'Content-Type: application/json' \
--data-raw '{
	"geometry_type": "circle",
	"geometry_radius": 500,
	"is_enabled": true,
	"only_once": true,
	"users": ["5f520949e3872b0341bcf3e7","5f520955e3872b0341bcf3e8","5f083247b3611453c98a726f"]
}'
```

