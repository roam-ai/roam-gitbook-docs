---
description: This API lets you to group users under the group_id
---

# Add Users to Group API

{% api-method method="post" host="https://api.geospark.co" path="/v3/api/group/user/" %}
{% api-method-summary %}
Group users API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.-** a88d1dddd5ec4be18d7009e0ed4ad59f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="group\_id" type="string" required=true %}
Adding users to group\_id  
**E.g.-** 600959fdffb3fb11b5c66b58
{% endapi-method-parameter %}

{% api-method-parameter name="users" type="string" required=true %}
User\_id required to add to group\_id  
**E.g.-** \["60095951ffb3fb11b9c66ba6", "60095980ffb3fb11b2c66b51"\]
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
    "data": "Users grouped successfully."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="Sample-Request.1"></a>

```text
curl --location --request POST 'https://api.geospark.co/v3/api/group/user/' \
--header 'Content-Type: application/json' \
--header 'Api-Key: a88d1dddd5ec4be18d7009e0ed4ad59f' \
--data-raw '{
	"group_id":"600959fdffb3fb11b5c66b58",
	"users": ["60095951ffb3fb11b9c66ba6", "60095980ffb3fb11b2c66b51"]
}'
```

