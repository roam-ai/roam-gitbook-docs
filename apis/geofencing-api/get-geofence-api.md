---
description: This API gives you the filtered list of geofences.
---

# GET Geofence API

{% api-method method="get" host="https://api.geospark.co/v3/" path="api/geofence/" %}
{% api-method-summary %}
GET Geofence API
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
{% api-method-parameter name="page\_number" type="integer" required=false %}
This field can be used for getting 10 entries at a time. If the response returns an empty list in the data field, it is safe to assume the pages are exhausted.  
**E.g.**-1
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=true %}
Date from when the geofences created to be fetched.  
**E.g**.- 2020-09-28
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=true %}
Date till when the data need to be returned.  
**E.g.**- 2020-09-29
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_id" type="string" required=false %}
Get the details of one geofence.  
**E.g.**- 5f73326ce5fc231ba4b253eb
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
        "next_page": null,
        "pages": 1,
        "prev_page": null,
        "account_id": "5bda16a2ea00845b3b419160",
        "project_id": "5bda16edea00845b3b419163",
        "geofences": [
            {
                "counts": {
                    "events": 0,
                    "users": 0
                },
                "id": "5f73326ce5fc231ba4b253eb",
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
                "description": "testing geofence",
                "color_code": "ffff",
                "tag": "border code",
                "is_deleted": false,
                "group_ids": ["5cda16edea00845b3b419173", "5f74326ce5fc231ba4b257eb"],
                "user_ids": ["6bda16edea01848b3b419163", "6373326ce5fc231ba4e253ea"],
                "enable_at": "2021-06-10T18:45:00",
                "disable_at": "2021-06-10T19:29:00"
                "created_at": "2020-09-29T13:11:08.702",
                "updated_at": "2020-09-29T13:13:43.890"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="GeofencingAPI-SampleRequest.2"></a>

```javascript
curl --location --request GET 'https://test.api.geospark.co/v3/api/geofence/?start_date=2020-09-28&end_date=2020-09-29&count=True' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88'
```

