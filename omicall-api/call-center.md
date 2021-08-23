---
description: 'Quản lý cấu hình tổng đài , số nội bộ'
---

# Tổng đài

{% api-method method="get" host="\[URL\]" path="/api/call\_center/internal\_phone/list" %}
{% api-method-summary %}
Danh sách số nội bộ
{% endapi-method-summary %}

{% api-method-description %}
- Lấy danh sách cấu hình số nội bộ  
- **Cấu hình** &gt; **Tổng đài** &gt; **Số nội bộ**  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token : Bearer 'token'
{% endapi-method-parameter %}

{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="keyword" type="string" required=false %}
Số nội bộ
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="number" %}
Trang, bắt đầu từ 1 \(Mặc định 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" %}
Kích thước trang, mặc định là 50
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Lấy danh sách số nội bộ thành công
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="\[URL\]" path="/api/call\_center/internal\_phone/status?enabled=&sip\_user=" %}
{% api-method-summary %}
Cập nhật trạng thái số máy lẻ
{% endapi-method-summary %}

{% api-method-description %}
Thay đổi trạng thái số máy lẻ : Hoạt đồng hoặc / Ngưng hoạt động
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="sip\_user" type="string" required=true %}
Số máy lẻ nhân viên
{% endapi-method-parameter %}

{% api-method-parameter name="enabled" type="string" required=true %}
true : Hoạt động  
false : Ngưng hoạt động
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



