---
description: Quản lý doanh nghiệp
---

# Doanh nghiệp

{% swagger baseUrl="[URL]" path="/api/tenant/detail" method="get" summary="Thông tin chi tiết" %}
{% swagger-description %}
Thông tin chi tiết doanh nghiệp
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Bearer Access Token
{% endswagger-parameter %}

{% swagger-response status="200" description="Thông tin chi tiết doanh nghiệp" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-1OB3SFM",
    "payload": {
        "full_name": "Omi Team",
        "email": "support@omicrm.com",
        "description": "Nâng cao trải nghiệm khách hàng, lấy sự hài lòng của khách hàng làm tiêu chí phấn đấu của doanh nghiệp",
        "enabled": true, //Đang hoạt động hoặc ngưng hoạt động
        "domain": "omiteam", // Tên miền truy cập OMI
        "domain_fusion": "omiteam", // Tên miền tổng đài
        "domain_expire": 1584606068154, // Ngày hết hạn domain
        "effective_date": 1583396482840, // Ngày kích hoạt
        "expire_date": 1614936981790, // Ngày hết hạn
        "phone": "0844441900", // SĐT chủ doanh nghiệp
        "status": "activated", // Trạng thái: Đã kích hoạt / Chưa kích hoạt
        "paid_type": "prepaid", // Hình thức thanh toán : prepaid : Trả trước, postpaid : Trả sau
        "nation": "vn", // Quốc gia
        "currency": "VND", // Tiền tệ
        "language": "vi", // Ngôn ngữ
        "balance": 3007855, // Số dư tài khoản
        "public_numbers": [
            {
                "number": "842877788056", // Số hotline
                "provider": "itel", // Nhà mạng
                "expire_date": 1602731734809, //Ngày hết hạn số
                "status": "active" // Tình trạng số
            }
        ],
        "service_package": {
            "code_name": "trial", // Mã gói
            "service_name": "Trial", // Tên gói
            "staff_num": 5, // Số lượng nhân viên
            "customer_num": 100, // Số lượng khách hàng
            "expiry_date": 1606300035002 // Ngày gói hết hạn
        }
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

