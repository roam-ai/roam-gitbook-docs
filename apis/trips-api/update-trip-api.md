---
description: >-
  This API allows you to update the origin, destination or user_id for a given
  trip_id before starting the trip.
---

# Update Trip API

{% api-method method="put" host="https://api.geospark.co/" path="v3/api/trips/" %}
{% api-method-summary %}
Update Trip API
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
user\_id to which the trip is to be reassigned  
**E.g.**- 5d9450ace47bae6d70064a9q
{% endapi-method-parameter %}

{% api-method-parameter name="trip\_id" type="string" required=true %}
Trip id which needs to be modified.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="origins" type="array" required=false %}
Origin location in \[long, lat\] format.  
**E.g**.- \[\[77.677270, 12.914131\]\]
{% endapi-method-parameter %}

{% api-method-parameter name="destinations" type="array" required=false %}
Destination location in \[long, lat\] format.  
**E.g.**- \[\[77.700475, 12.957005\]\]
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
                    "created_at": "2020-09-22T06:01:44.680",
                    "updated_at": "2020-09-22T06:01:44.687",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.700475,
                            12.957005
                        ]
                    },
                    "loc_type": "destination"
                }
            ],
            "events": [
                {
                    "id": "<ID>",
                    "trip_id": "<TRIP-ID>",
                    "user_id": "<USER-ID>",
                    "event_type": "motion:trip:created",
                    "created_at": "2020-09-22T06:00:35.210",
                    "is_deleted": false,
                    "event_source": "motion:trip",
                    "event_version": "1.0"
                },
                {
                    "id": "<ID>",
                    "trip_id": "<TRIP-ID>",
                    "user_id": "<USER-ID>",
                    "event_type": "motion:trip:created",
                    "created_at": "2020-09-22T06:01:42.606",
                    "is_deleted": false,
                    "event_source": "motion:trip",
                    "event_version": "1.0"
                }
            ],
            "user_id": "<USER-ID>",
            "is_started": false,
            "is_ended": false,
            "is_deleted": false,
            "created_at": "2020-09-22T06:00:34.261",
            "updated_at": "2020-09-22T06:01:44.699"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="TripsAPI-SampleRequest.1"></a>

```text
curl --location --request PUT 'https://api.geospark.co/v3/api/trips/' \
--header 'Api-key: <API-KEY>' \
--header 'Content-Type: application/json' \
--data-raw '{
	"trip_id": "<TRIP-ID>",
	"destinations": [[77.700475, 12.957005]]
}'
```

