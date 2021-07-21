---
description: This API lets you create a group which will return group_id
---

# Create Group API

{% api-method method="post" host="https://api.geospark.co" path="/v3/api/group/" %}
{% api-method-summary %}
Create Group API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
 Auth-key  
**E.g**.**-** a88d1dddd5ec4be18d7009e0ed4ad59f  
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="description" type="string" required=false %}
Naming group\_id  
**E.g.-** test user
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
    "data": {
        "group_id": "600959fdffb3fb11b5c66b58",
        "project_id": "60094dd8ffb3fb482ec5cdc3",
        "description": "handy",
        "updated_at": "2021-01-21T10:39:57.462",
        "created_at": "2021-01-21T10:39:57.462"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request

```text
curl --location --request POST 'https://api.geospark.co/v3/api/group/' \
--header 'Api-Key: a88d1dddd5ec4be18d7009e0ed4ad59f' \
--header 'Content-Type: application/json' \
--data-raw '{
	"description": "test user"
}
'
```

