# Trip Events

{% api-method method="get" host="https://api.roam.ai/v1/" path="api/event/trips/" %}
{% api-method-summary %}
GET Trip Events
{% endapi-method-summary %}

{% api-method-description %}
The Get Trip Events API lets you fetch the events of the users triggered during a trip.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.**- ****33223kjhdcscijhb5sdbsdmjsdcbj5f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="page\_number" type="integer" required=false %}
Used to go through all the pages of data.  
**E.g.**- 1
{% endapi-method-parameter %}

{% api-method-parameter name="user\_id" type="string" required=true %}
Filters events data for the given user\_id.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="trip\_id" type="string" required=false %}
Filters events data for the given trip\_id.  
**E.g.**- 5cd024aa9533a30eb6147132
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=true %}
Date to define the start of date\_range of data to be returned.  
**E.g.**- 2020-09-01
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=true %}
Date to define the end of date\_range.  
**E.g.**- 2020-10-02
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
        "pages": 2,
        "prev_page": null,
        "events": [
            {
                "trip_id": "5f7dac74ffb3fb58435309e7",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:ended",
                "created_at": "2020-10-07T11:54:47.547000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac87bd4165ae1751b49d"
            },
            {
                "trip_id": "5f7dac74ffb3fb58435309e7",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:started",
                "created_at": "2020-10-07T11:54:36.747000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac7cbd4165ae1751b49c"
            },
            {
                "trip_id": "5f7dac74ffb3fb58435309e7",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:created",
                "created_at": "2020-10-07T11:54:31.620000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac77bd4165ae1751b49b"
            },
            {
                "trip_id": "5f7dac3de5fc233612297d5d",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:created",
                "created_at": "2020-10-07T11:53:35.464000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac3fbd4165ae1751b49a"
            },
            {
                "trip_id": "5f7dac37ffb3fb583d5309e2",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:ended",
                "created_at": "2020-10-07T11:53:33.149000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac3dbd4165ae1751b499"
            },
            {
                "trip_id": "5f7dac37ffb3fb583d5309e2",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:started",
                "created_at": "2020-10-07T11:53:31.780000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac3bbd4165ae1751b498"
            },
            {
                "trip_id": "5f7dac37ffb3fb583d5309e2",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:created",
                "created_at": "2020-10-07T11:53:29.718000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dac39bd4165ae1751b497"
            },
            {
                "trip_id": "5f7dab4ee5fc233611297c78",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:ended",
                "created_at": "2020-10-07T11:50:21.457000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dab7dbd4165ae1751b496"
            },
            {
                "trip_id": "5f7dab4ee5fc233611297c78",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:reached_origin",
                "location": {
                    "type": "Point",
                    "coordinates": [
                        77.622977,
                        12.918705611879671
                    ]
                },
                "created_at": "2020-10-07T11:50:19.279000",
                "speed": 0,
                "course": 0,
                "altitude": 505.20001220703125,
                "activity": "S",
                "horizontal_accuracy": 20,
                "user_id": "5f7daae0e5fc233612297d5a",
                "location_id": "5f2ba9edb3611421f252e019",
                "trip_location_id": "5f7dab4ee5fc233611297c79",
                "recorded_at": "2020-10-07T11:50:16.158000",
                "id": "5f7dab7bbd4165ae1751b495"
            },
            {
                "trip_id": "5f7dab4ee5fc233611297c78",
                "event_source": "geospark:trip",
                "event_version": "1.0",
                "event_type": "geospark:trip:started",
                "created_at": "2020-10-07T11:50:12.378000",
                "user_id": "5f7daae0e5fc233612297d5a",
                "id": "5f7dab7447cd80500a7f7e49"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="EventsAPI-SampleRequest.1"></a>

```text
curl --location --request GET 'https://api.roam.ai/v1/api/event/trips/?user_id=5f71ad9a5c3a0f059acebb39' \
--header 'Api-Key: 50ccfe35a1ee409f9791cdee340e5864'
```

