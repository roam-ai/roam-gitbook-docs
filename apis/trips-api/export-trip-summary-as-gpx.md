---
description: The API helps you to export Trip data to gpx format
---

# Export Trip Summary as GPX

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/trips/export/" %}
{% api-method-summary %}
Export Trip Summary as GPX
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.-** 083591a3392c483e838f66ac788126eb
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="trip\_id" type="string" required=true %}
trip\_id required to export its data in gpx format.  
**E.g.-** 5fdc5470203bda0000abacc0
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
format to be given in which data need to be exported.  
**E.g.-** gpx
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
        "download_url": "https://geospark-gpx-files.s3.amazonaws.com/5fdc5470203bda0000abacc0.gpx"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="Sample-Request"></a>

```text
curl --location --request GET 'https://api.roam.ai/v1/api/trips/export/?trip_id=5f44a2fce289b825457e5497&type=gpx' \
--header 'Api-key: <API-KEY>'
```

