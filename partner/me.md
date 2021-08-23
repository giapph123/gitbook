---
description: Thông tin đối tác
---

# Thông tin đối tác

{% api-method method="get" host="\[URL\]" path="/api/partner/me" %}
{% api-method-summary %}
Thông tin đối tác
{% endapi-method-summary %}

{% api-method-description %}
Thông tin đối tác
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Acces token : Bearer 'partner token'
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Thông tin đối tác
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-1OB3SFM",
    "payload": {
        "full_name": "Đối tác OMI",
        "email": "support@omicrm.com",
        "description": "Nâng cao trải nghiệm khách hàng, lấy sự hài lòng của khách hàng làm tiêu chí phấn đấu của doanh nghiệp",
        "enabled": true, //Đang hoạt động hoặc ngưng hoạt động
        "status": "activated", // Trạng thái: Đã kích hoạt / Chưa kích hoạt
        "paid_type": "prepaid", // Hình thức thanh toán : prepaid : Trả trước, postpaid : Trả sau
        "nation": "vn", // Quốc gia
        "currency": "VND", // Tiền tệ
        "language": "vi", // Ngôn ngữ
        "balance": 3007855, // Số dư tài khoản
    },
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



