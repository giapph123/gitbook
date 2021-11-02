---
description: Thông tin đối tác
---

# Thông tin đối tác

{% swagger baseUrl="[URL]" path="/api/partner/me" method="get" summary="Thông tin đối tác" %}
{% swagger-description %}
Thông tin đối tác
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Acces token : Bearer 'partner token'
{% endswagger-parameter %}

{% swagger-response status="200" description="Thông tin đối tác" %}
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
{% endswagger-response %}
{% endswagger %}

