---
description: Danh sách kho đầu số
---

# Kho đầu số

{% swagger baseUrl="[URL]" path="/api/partner/public_number/list" method="get" summary="Danh sách kho đầu số" %}
{% swagger-description %}
Danh sách kho đầu số
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token : Bearer 'partner token'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="number" %}
Trang (Bắt đầu từ 1)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="boolean" %}
Kích thước trang (Mặc định là 50)
{% endswagger-parameter %}

{% swagger-response status="200" description="Danh sách đầu số" %}
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
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL" path="/api/partner/public_number/buy" method="post" summary="Mua đầu số " %}
{% swagger-description %}
Mua số hotline
{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Access token : Bearer 'partner token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="number_count" type="number" %}
Số tháng sử dụng (Tối thiểu 6 tháng)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="note" type="string" %}
Mô tả
{% endswagger-parameter %}

{% swagger-parameter in="body" name="number" type="string" %}
Số hotline
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Email chủ doanh nghiệp
{% endswagger-parameter %}

{% swagger-response status="200" description="Mua đầu số thành công" %}
```
```
{% endswagger-response %}
{% endswagger %}

