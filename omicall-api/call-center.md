---
description: Quản lý cấu hình tổng đài , số nội bộ
---

# Tổng đài

{% swagger baseUrl="[URL]" path="/api/call_center/internal_phone/list" method="get" summary="Danh sách số nội bộ" %}
{% swagger-description %}
\- Lấy danh sách cấu hình số nội bộ

\


\- 

**Cấu hình**

 \> 

**Tổng đài**

 \>

** Số nội bộ**

\



{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
Access Token : Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" required="true" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keyword" type="string" %}
Số nội bộ
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="number" %}
Trang, bắt đầu từ 1 (Mặc định 1)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="number" %}
Kích thước trang, mặc định là 50
{% endswagger-parameter %}

{% swagger-response status="200" description="Lấy danh sách số nội bộ thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": {
        "items": [
            {
                "domain": "omiteam", // Domain tổng đài
                "outbound_proxy": "wss://wssvn.omicrm.com", // Outboud Proxy
                "sip_user": "147", // Số nội bộ
                "password": "XXXXXX", // Mật khẩu truy cập
                "full_name": "Đỗ Thị Hồng Vy", // Họ và tên
                "email": "dohongvyzyt@gmail.com", // Email
                "public_number":"84256336xxxx", // Đầu số đang sử dụng
                "last_updated_date": 1575269373331, //Cập nhật lần cuối
                "created_date": 1575251355778 // Ngày tạo
            },
            {
                "domain": "omiteam", // Domain tổng đài
                "outbound_proxy": "wss://wssvn.omicrm.com", // Outboud Proxy
                "sip_user": "145",
                "password": "kiyyzsefxx",
                "full_name": "Hồng Ngọc",
                "email": "vykh252tn1998@gmail.com",
                "public_number":"84256336xxxx",
                "last_updated_date": 1574999296765,
                "created_date": 1574133910912
            }
        ],
        "page_number": 1,
        "page_size": 2,
        "total_items": 30,
        "total_pages": 15,
        "has_next": true,
        "next_page": 2,
        "has_previous": false,
        "previous_page": 1
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/call_center/internal_phone/status?enabled=&sip_user=" method="put" summary="Cập nhật trạng thái số máy lẻ" %}
{% swagger-description %}
Thay đổi trạng thái số máy lẻ : Hoạt đồng hoặc / Ngưng hoạt động
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sip_user" type="string" required="true" %}
Số máy lẻ nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="query" name="enabled" type="string" required="true" %}
true : Hoạt động

\


false : Ngưng hoạt động
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/call_center/hotline/list?extension=" method="get" summary="Danh sách đầu số đang hoạt động và cho phép gọi ra" %}
{% swagger-description %}
Lấy danh sách đầu số đang hoạt động và cho phép gọi ra của một số nội bộ
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="extension" type="string" %}
Số máy lẻ nhân viên
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": [
        "024********",
        "842*********"
    ],
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}
