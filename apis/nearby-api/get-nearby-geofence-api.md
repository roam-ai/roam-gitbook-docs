---
description: >-
  The Get Nearby Geofence API provides the list of geofences that are within the
  specified radius.
---

# Get Nearby Geofence API

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/search/geofences/" %}
{% api-method-summary %}
Get Nearby Geofence API
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

{% api-method-query-parameters %}
{% api-method-parameter name="user\_id" type="string" required=false %}
Filters nearby geofence data for the given user\_id’s last known location.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
Used to go through all the pages of data.  
**E.g.**- 1
{% endapi-method-parameter %}

{% api-method-parameter name="radius" type="integer" required=false %}
Search in the radius provided.  
**E.g**.- 10000
{% endapi-method-parameter %}

{% api-method-parameter name="location" type="string" required=false %}
Origin location in \[long, lat\] format.  
**E.g**.- 12.98046,80.16492
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
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
        "next_page": 2,
        "pages": 4,
        "prev_page": null,
        "geofences": [
            {
                "id": "5eecc7481e621663c83ba278",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.09729,
                        12.92341
                    ]
                },
                "is_enabled": true,
                "description": "33",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:16.226",
                "updated_at": "2020-06-19T14:10:16.226"
            },
            {
                "id": "5eecc7471e621663c93ba2fc",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.1016,
                        12.92553
                    ]
                },
                "is_enabled": true,
                "description": "32",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:15.737",
                "updated_at": "2020-06-19T14:10:15.737"
            },
            {
                "id": "5eecc7471e621663c83ba277",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.10564,
                        12.92575
                    ]
                },
                "is_enabled": true,
                "description": "31",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:15.257",
                "updated_at": "2020-06-19T14:10:15.257"
            },
            {
                "id": "5eecc7461e621663c93ba2fb",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.10889,
                        12.92715
                    ]
                },
                "is_enabled": true,
                "description": "30",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:14.762",
                "updated_at": "2020-06-19T14:10:14.762"
            },
            {
                "id": "5eecc7461e621663c83ba276",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.11459,
                        12.93019
                    ]
                },
                "is_enabled": true,
                "description": "29",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:14.281",
                "updated_at": "2020-06-19T14:10:14.281"
            },
            {
                "id": "5eecc7451e621663c93ba2fa",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.11818,
                        12.93041
                    ]
                },
                "is_enabled": true,
                "description": "28",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:13.799",
                "updated_at": "2020-06-19T14:10:13.799"
            },
            {
                "id": "5eecc7451e621663c83ba275",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.12156,
                        12.93033
                    ]
                },
                "is_enabled": true,
                "description": "27",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:13.305",
                "updated_at": "2020-06-19T14:10:13.305"
            },
            {
                "id": "5eecc7441e621663c93ba2f9",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.12624,
                        12.93508
                    ]
                },
                "is_enabled": true,
                "description": "26",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:12.759",
                "updated_at": "2020-06-19T14:10:12.759"
            },
            {
                "id": "5eecc7441e621663c83ba274",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.12778,
                        12.93681
                    ]
                },
                "is_enabled": true,
                "description": "25",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:12.127",
                "updated_at": "2020-06-19T14:10:12.127"
            },
            {
                "id": "5eecc7431e621663c93ba2f8",
                "account_id": "5c0179df6f994031158a5646",
                "project_id": "5e95cbe83722794cf72ea0af",
                "geometry_type": "circle",
                "geometry_radius": 75,
                "geometry_center": {
                    "type": "Point",
                    "coordinates": [
                        80.13224,
                        12.94162
                    ]
                },
                "is_enabled": true,
                "description": "24",
                "is_deleted": false,
                "created_at": "2020-06-19T14:10:11.643",
                "updated_at": "2020-06-19T14:10:11.644"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="NearbyAPI-SampleRequest"></a>

```text
curl --location --request GET 'https://api.roam.ai/v1/api/search/geofences/?radius=10000&location=12.98046,80.16492' \
--header 'Api-key: 50ccfe35a1ee409f9791cdee340e5864'
```

