---
description: >-
  API dùng để lấy access token thông qua API KEY được cung cấp. AcessToken là
  chuỗi mã hóa chứa thông tin của doanh nghiệp, có thời gian hết hạn là 24 giờ
---

# Xác thực

{% swagger baseUrl="[URL]" path="/api/auth?apiKey=" method="get" summary="Get AccessToken" %}
{% swagger-description %}
Lấy Access Token thông qua API KEY
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="apiKey" type="string" %}
API key của doanh nghiệp được cung cấp
{% endswagger-parameter %}

{% swagger-response status="200" description="Khi yêu cầu API thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "cloud-vihat-saas-sync-public-api-77689c7b9c",
    "payload": {
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9 ...",
        "access_type" : "normal",
        "token_type": "Bearer"
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

**Thông tin kết quả trả về payload**

| Tham số       | Mô tả                                                                                                                                                              |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| access\_token | Access token truy cập                                                                                                                                              |
| access\_type  | <p>Có 2 loại </p><ul><li><strong>normal </strong>: Doanh nghiệp người dùng cuối</li><li><strong>bussiness </strong>: Doanh nghiệp là đối tác của OMICALL</li></ul> |
| token\_type   | Bearer                                                                                                                                                             |
