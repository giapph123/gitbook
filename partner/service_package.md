---
description: Danh sách gói dịch vụ
---

# Gói dịch vụ

{% swagger baseUrl="[URL]" path="/api/partner/service_package/list" method="get" summary="Danh sách gói dịch vụ" %}
{% swagger-description %}
Danh sách gói dịch vụ
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token: Bearer 'partner token'
{% endswagger-parameter %}

{% swagger-response status="200" description="Danh sách gói dịch vụ" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "payload": [
        {
            "code_name": "trial", // Mã
            "service_name": "Trial", // Tên
            "staff_num": 5, // Số lượng nhân viên
            "customer_num": 100, // Số lượng khách hàng
            "note": "5 người dùng \n100 khách hàng \n500MB dữ liệu" // Mô tả
            "fee_setups" [ // Phí cài đặt VND
                
            ],
            "fee_holds" : [ // Phí duy trì VND
                
            ]
        },
        {
            "code_name": "omi_start",
            "service_name": "Omi Start",
            "staff_num": 5, // Số lượng nhân viên
            "customer_num": 0, // Không giới hạn
            "note": "5 người dùng \nKhông giới hạn khách hàng \n10GB dữ liệu"
            "fee_setups" [ // Phí cài đặt VND
                {
                    "currency": "VND",
                    "price": 300000
                }
                ....
            ],
            "fee_holds" : [ // Phí duy trì VND
                {
                    "currency": "VND",
                    "price": 350000
                },
                ....
            ]
        },
        {
            "code_name": "omi_business",
            "service_name": "Omi Business",
            "staff_num": 10,
            "customer_num": 0,
            "note": "5 người dùng \nKhông giới hạn khách hàng \n50GB dữ liệu"
        },
        {
            "code_name": "omi_advance",
            "service_name": "Omi Advance",
            "staff_num": 20,
            "customer_num": 0,
            "note": "20 người dùng \nKhông giới hạn khách hàng \n100GB dữ liệu"
        },
        {
            "code_name": "omi_pro",
            "service_name": "Omi Pro",
            "staff_num": 30,
            "customer_num": 0,
            "note": "30 người dùng \nKhông giới hạn khách hàng \n100GB dữ liệu"
        },
        {
            "code_name": "customize",
            "service_name": "Omi Enterprise",
            "staff_num": 35,
            "customer_num": 0,
            "note": "50 người dùng \nKhông giới hạn khách hàng \n1000GB dữ liệu"
        }
    ],
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/partner/service_package/upgrade" method="post" summary="Nâng cấp gói dịch vụ" %}
{% swagger-description %}
Nâng cấp gói dịch vụ

\




**Số tiền nâng cấp**

 \= 

**Phí thiết lập**

 \+ 

**Phí duy trì * số tháng**
{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Access Token : Bearer 'partner token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Email chủ doanh nghiệp
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code_name" type="string" %}
Mã gói dịch vụ
{% endswagger-parameter %}

{% swagger-parameter in="body" name="month_num" type="number" %}
Số tháng (Ít nhất là 6 tháng)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="note" type="string" %}
Ghi chú (Lớn hơn 10 ký tự)
{% endswagger-parameter %}

{% swagger-response status="200" description="Nâng cấp gói dịch vụ thành công" %}
```
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/partner/service_package/extend" method="post" summary="Gia hạn gói dịch vụ" %}
{% swagger-description %}
Gia hạn gói dịch vụ

\




**Số tiền gia hạn = Phí duy trì * Số tháng**
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token : Bearer 'partner token'.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="month_num" type="integer" %}
Số tháng gia hạn (Tối thiểu 6 tháng)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="note" type="string" %}
Ghi chú (Tối thiểu 10 ký tự)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Email chủ doanh nghiệp
{% endswagger-parameter %}

{% swagger-response status="200" description="Gia hạn gói dịch vụ" %}
```
```
{% endswagger-response %}
{% endswagger %}

