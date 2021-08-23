---
description: Quản lý Webhook
---

# Webhooks

{% api-method method="get" host="\[URL" path="/api/webhooks/list" %}
{% api-method-summary %}
Danh sách webhook
{% endapi-method-summary %}

{% api-method-description %}
Danh sách webhook
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Danh sách Webhook
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "payload": [
        {
            "url": "https://demo.omicall.com/omicall/updatecall",
            "type": "call",
            "status": "actived"
        }
    ],
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/webhooks/register" %}
{% api-method-summary %}
Đăng ký Webhook
{% endapi-method-summary %}

{% api-method-description %}
Ghi danh Webhook
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="webhook" type="object" required=true %}
Đối tượng :  
- **type** : _Loại Webhook_   
- **url** : _Đường dẫn Webhook_  
`{  
   "type" : "call",   
   "url" : "https://...... "  
}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Ghi danh Webhook thành công
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "payload": [
        {
            "url": "https://demo.omicall.com/omicall/updatecall",
            "type": "call",
            "status": "actived"
        }
    ],
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/webhooks/destroy?hook\_type=" %}
{% api-method-summary %}
Hủy Webhook
{% endapi-method-summary %}

{% api-method-description %}
Hủy đăng ký Webhook
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="hook\_type" type="string" required=true %}
Một trong các giá trị sau  
- **call** : Lịch sử cuộc gọi
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

