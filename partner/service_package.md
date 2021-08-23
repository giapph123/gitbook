---
description: Danh sách gói dịch vụ
---

# Gói dịch vụ

{% api-method method="get" host="\[URL\]" path="/api/partner/service\_package/list" %}
{% api-method-summary %}
Danh sách gói dịch vụ
{% endapi-method-summary %}

{% api-method-description %}
Danh sách gói dịch vụ
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token: Bearer 'partner token'
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Danh sách gói dịch vụ
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/partner/service\_package/upgrade" %}
{% api-method-summary %}
Nâng cấp gói dịch vụ
{% endapi-method-summary %}

{% api-method-description %}
Nâng cấp gói dịch vụ  
**Số tiền nâng cấp** = **Phí thiết lập** + **Phí duy trì \* số tháng**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token : Bearer 'partner token'
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email chủ doanh nghiệp
{% endapi-method-parameter %}

{% api-method-parameter name="code\_name" type="string" required=true %}
Mã gói dịch vụ
{% endapi-method-parameter %}

{% api-method-parameter name="month\_num" type="number" required=true %}
Số tháng \(Ít nhất là 6 tháng\)
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=true %}
Ghi chú \(Lớn hơn 10 ký tự\)
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Nâng cấp gói dịch vụ thành công
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/partner/service\_package/extend" %}
{% api-method-summary %}
Gia hạn gói dịch vụ
{% endapi-method-summary %}

{% api-method-description %}
Gia hạn gói dịch vụ  
**Số tiền gia hạn = Phí duy trì \* Số tháng**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token : Bearer 'partner token'.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="month\_num" type="integer" required=true %}
Số tháng gia hạn \(Tối thiểu 6 tháng\)
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=true %}
Ghi chú \(Tối thiểu 10 ký tự\)
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email chủ doanh nghiệp
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Gia hạn gói dịch vụ
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



