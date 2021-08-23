---
description: Danh sách kho đầu số
---

# Kho đầu số

{% api-method method="get" host="\[URL\]" path="/api/partner/public\_number/list" %}
{% api-method-summary %}
Danh sách kho đầu số
{% endapi-method-summary %}

{% api-method-description %}
Danh sách kho đầu số
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token : Bearer 'partner token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="page" type="number" required=true %}
Trang \(Bắt đầu từ 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="boolean" required=true %}
Kích thước trang \(Mặc định là 50\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Danh sách đầu số
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "payload": {
        "next_page": 2,
        "page_number": 1,
        "has_previous": false,
        "has_next": true,
        "total_pages": 3,
        "previous_page": 1,
        "items": [
            {
                "created_date": 1583725991806, // Ngày tạo
                "last_updated_date": 1601005495717, // Cập nhật lần cuối
                "number": "842477778823", // Số hotline
                "provider": "Itelecom", // Nhà mạng
                "provider_type": "itel", // Tên ngắn
                "number_type": "fixed", // Loại đầu số (Cố định, di động, 1900, 1800, ... )
                "nation": "vn" // Quốc gia,
                "maintaining_prices": [ // Phí duy trì đầu số
                    {
                        "currency": "VND",
                        "price": 22000
                    },
                    {
                        "currency": "USD",
                        "price": 0.977
                    }
                ],
                call_pricing { // Giá thoại
                }
            },
            {
                "created_date": 1583725991806,
                "last_updated_date": 1601092490032,
                "number": "842477778814",
                "provider": "Itelecom",
                "provider_type": "itel",
                "number_type": "fixed",
                "nation": "vn"
            },
            ......
        ],
        "total_items": 140,
        "page_size": 50
    },
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL" path="/api/partner/public\_number/buy" %}
{% api-method-summary %}
Mua đầu số 
{% endapi-method-summary %}

{% api-method-description %}
Mua số hotline
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token : Bearer 'partner token'
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="number\_count" type="number" required=true %}
Số tháng sử dụng \(Tối thiểu 6 tháng\)
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=true %}
Mô tả
{% endapi-method-parameter %}

{% api-method-parameter name="number" type="string" required=true %}
Số hotline
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email chủ doanh nghiệp
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Mua đầu số thành công
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



