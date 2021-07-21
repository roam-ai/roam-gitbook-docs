---
description: >-
  Delete Geofence API allows you to delete already existing geofences for a
  project
---

# Delete Geofence API

{% api-method method="delete" host="https://api.roam.ai/v1/" path="api/geofence" %}
{% api-method-summary %}
Delete Geofence API
{% endapi-method-summary %}

{% api-method-description %}
 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.**-33223kjhdcscijhb5sdbsdmjsdcbj5f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="geofence\_id" type="string" required=true %}
Delete geofence for this id.  
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
    "msg": "Geofence deleted successfully.",
    "code": 200,
    "data": {}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="GeofencingAPI-SampleRequest.3"></a>

```text
curl --location --request DELETE 'https://api.roam.ai/v1/api/geofence/?geofence_id=5f73326ce5fc231ba4b253eb' \
--header 'Api-Key: e566c098cc6b441a9c3453b6fcf76e88' \
--header 'Content-Type: application/json'
```

