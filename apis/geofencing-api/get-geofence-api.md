---
description: This API gives you the filtered list of geofences.
---

# GET Geofence API

{% api-method method="get" host="https://api.roam.ai" path="/v1/api/geofence/" %}
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
{% api-method-parameter name="user\_id" type="string" required=false %}
Filter the geofence which is enabled for this user\_id  
**E.g.-** 6073325bcf3e4eba5a1123a
{% endapi-method-parameter %}

{% api-method-parameter name="group\_id" type="string" required=false %}
Filter the geofences which is enabled for this group\_id  
**E.g.-** 6073325bc3fe343ab6c1324b
{% endapi-method-parameter %}

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
    "geofences": [
      
      {
        "geofence_id": "60ee8ea4ffb3fb728c120d8b",
        "geometry_type": "circle",
        "geometry_radius": 177,
        "geometry_center": {
          "type": "Point",
          "coordinates": [
            -72.28122,
            42.926042
          ]
        },
        "is_enabled": [
          true,
          "2021-06-10T18:45:00.000",
          "2021-06-10T19:29:00.000"
        ],
        "user_ids": [
          "6bda16edea01848b3b419163"
        ],
        "is_deleted": false,
        "created_at": "2021-07-14T07:13:40.765",
        "updated_at": "2021-07-14T07:13:40.765"
      },
      {
        "geofence_id": "60ee8e6effb3fb728c120d8a",
        "geometry": {
          "type": "Polygon",
          "coordinates": [
            [
              [
                -0.08789347686767579,
                51.50619618452938
              ],
              [
                -0.0905934768676758,
                51.50619618452938
              ],
              [
                -0.0905934768676758,
                51.503796184529385
              ],
              [
                -0.08789347686767579,
                51.50619618452938
              ]
            ]
          ]
        },
        "geometry_type": "polygon",
        "geometry_center": {
          "type": "Point",
          "coordinates": [
            -0.08969347686882724,
            51.505396185373506
          ]
        },
        "is_enabled": [
          true,
          "2021-06-10T18:45:00.000",
          "2021-06-10T19:29:00.000"
        ],
        "is_deleted": false,
        "created_at": "2021-07-14T07:12:46.811",
        "updated_at": "2021-07-14T07:12:46.811"
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
curl --location --request GET 'https://api.roam.ai/v1/api/geofence/?start_date=2020-09-28&end_date=2020-09-29' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88'
```

