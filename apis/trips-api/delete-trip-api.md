---
description: This API helps you to delete an existing trip.
---

# Delete Trip API

{% api-method method="delete" host="https://api.roam.ai/v1" path="/api/trips/" %}
{% api-method-summary %}
Delete Trip API
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
{% api-method-parameter name="trip\_id" type="string" required=true %}
Trip id which needs to be deleted.  
**E.g.**- 5cd0299d77aebe2d78758d32
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
    "msg": "Trip deleted successfully.",
    "code": 200,
    "data": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="TripsAPI-SampleRequest.2"></a>

```text
curl --location --request DELETE 'https://api.roam.ai/v1/api/trips/?trip_id=<TRIP-ID>' \
--header 'Content-Type: application/json' \
--header 'Api-key: <API-KEY>'
```

