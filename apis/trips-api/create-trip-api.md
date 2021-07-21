---
description: >-
  The Create Trip API helps you to create a new trip with an origin,
  destination, and user.
---

# Create Trip API

{% api-method method="post" host="https://api.roam.ai/v1" path="/api/trips/" %}
{% api-method-summary %}
 Create Trip API
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
{% api-method-parameter name="user\_id" type="string" required=false %}
User-id for which the trip needs to be assigned  
**E.g**.- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="origins" type="array" required=false %}
Single or multiple origin locations in \[long, lat\] format.  
**E.g.**- \[\[77.677270, 12.914131\]\]
{% endapi-method-parameter %}

{% api-method-parameter name="destinations" type="array" required=false %}
Single or multiple destination locations in \[long, lat\] format.  
**E.g**.- \[\[77.700475, 12.957005\]\]
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
    "code": 201,
    "data": [
        {
            "id": "<ID>",
            "origins": [
                {
                    "id": "<ID>",
                    "trip_id": "<TRIP-ID>",
                    "created_at": "2020-09-22T06:00:34.264",
                    "updated_at": "2020-09-22T06:00:34.269",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.622977,
                            12.917042
                        ]
                    },
                    "loc_type": "origin"
                }
            ],
            "destinations": [
                {
                    "id": "<ID>",
                    "trip_id": "<TRIP-ID>",
                    "created_at": "2020-09-22T06:00:34.272",
                    "updated_at": "2020-09-22T06:00:34.275",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.650239,
                            12.924304
                        ]
                    },
                    "loc_type": "destination"
                },
                {
                    "id": "<ID>",
                    "trip_id": "<TRIP-ID>",
                    "created_at": "2020-09-22T06:00:34.278",
                    "updated_at": "2020-09-22T06:00:34.281",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.697418,
                            12.959172
                        ]
                    },
                    "loc_type": "destination"
                }
            ],
            "events": [],
            "user_id": "<USER-ID>",
            "is_started": false,
            "is_ended": false,
            "is_deleted": false,
            "created_at": "2021-06-22T06:00:34.261",
            "updated_at": "2021-06-22T06:00:34.261",
            "trip_tracking_url": "https://trips.gs/NWY2OTkzMDI5NzI0MjIwNThmY2ZjYTFlfHNmZHNnZHNh"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
curl --location --request POST 'https://api.roam.ai/v1/api/trips/' \
--header 'Api-key: <API-KEY>' \
--header 'Content-Type: application/json' \
--data-raw '{
	"user_id": "<USER-ID>",
	"origins": [[77.622977 ,12.917042]],
    "destinations":[[77.650239 ,12.924304], [77.697418 ,12.959172]]
}'
```



