---
description: Quản lý Webhook
---

# Webhooks

{% swagger baseUrl="[URL" path="/api/webhooks/list" method="get" summary="Danh sách webhook" %}
{% swagger-description %}
Danh sách webhook
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token
{% endswagger-parameter %}

{% swagger-response status="200" description="Danh sách Webhook" %}
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
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/webhooks/register" method="post" summary="Đăng ký Webhook" %}
{% swagger-description %}
Ghi danh Webhook
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="webhook" type="object" %}
Đối tượng :

\


\- 

**type**

 : 

_Loại Webhook_

 

\


\- 

**url **

: 

_Đường dẫn Webhook_

\




`{`

\


`    "type" : "call",  `

\


`   "url" : "https://...... "`

\


`}`
{% endswagger-parameter %}

{% swagger-response status="200" description="Ghi danh Webhook thành công" %}
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
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/webhooks/destroy?hook_type=" method="post" summary="Hủy Webhook" %}
{% swagger-description %}
Hủy đăng ký Webhook
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hook_type" type="string" %}
Một trong các giá trị sau

\


\- 

**call **

: Lịch sử cuộc gọi
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}
