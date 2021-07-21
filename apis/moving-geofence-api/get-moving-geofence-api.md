---
description: GET Moving-Geofence API gives you the filtered list of moving-geofences.
---

# GET Moving-Geofence API

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/moving-geofence/" %}
{% api-method-summary %}
GET Moving-Geofence API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g**.- 33223kjhdcscijhb5sdbsdmjsdcbj5f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="start\_date" type="string" required=true %}
Date from when the geofences created to be fetched.  
**E.g.**- 2020-09-28
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=true %}
Date till when the data need to be returned.  
**E.g.**- 2020-09-29
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_id" type="string" required=false %}
Get the details of one geofence.  
**E.g.**- 5f73326ce5fc231ba4b253eb
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field can be used for getting 10 entries at a time. If the response returns an empty list in the data field, it is safe to assume the pages are exhausted.  
**E.g.**- 1
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
        "users": [
            "5f520949e3872b0341bcf3e7",
            "5f520955e3872b0341bcf3e8"
        ],
        "geofences": [
            {
                "counts": {
                    "events": 0,
                    "users": 0
                },
                "id": "5f9801aeffb3fb0de55e863d",
                "geometry_type": "circle",
                "geometry_radius": 500,
                "is_enabled": true,
                "description": "testing geofence",
                "color_code": "ggggg",
                "tag": "border code",
                "is_deleted": false,
                "created_at": "2020-10-27T11:17:02.956",
                "updated_at": "2020-10-27T11:20:33.050",
                "only_once": true
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="Sample-Request.2"></a>

```text
curl --location --request GET 'https://api.roam.ai/v1/api/moving-geofence/?start_date=2020-10-27&end_date=2020-10-27&count=True' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88'
```

