---
description: '- Báo cáo sản lượng tổng nhà cung cấp'
---

# Báo cáo sản lượng nhà cung cấp

{% swagger baseUrl="[URL]" path="/supplier/report" method="get" summary="Báo cáo tổng sản lượng" %}
{% swagger-description %}
\- Lấy sản lượng tổng nội và ngoại mạng

\


\- Sản lượng nhận được sẽ bằng 

**20% sản lượng thực tế**

\


\- API sẽ cập nhật số liệu sau 60 phút. Nếu request sau cách request trước chưa tới 60 phút, thì sẽ nhận sản lượng trước đó
{% endswagger-description %}

{% swagger-parameter in="query" name="provider_key" type="string" %}
KEY cung cấp nhà Supplier
{% endswagger-parameter %}

{% swagger-parameter in="query" name="from_date_str" type="string" %}
Từ ngày (dd/MM/yyyy HH:mm:ss) 

\


Mặc định là ngày đầu tháng
{% endswagger-parameter %}

{% swagger-parameter in="query" name="to_date_str" type="boolean" %}
Đến ngày (dd/MM/yyyy HH:mm:ss)

\


Mặc định là ngày hiện tại 
{% endswagger-parameter %}

{% swagger-response status="200" description="Sản lượng nội và ngoại mạng" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": [
        {
            "provider": "MOBIFONE",
            "type": "in",
            "total_seconds": 672989.0
        },
        {
            "provider": "MOBIFONE",
            "type": "out",
            "total_seconds": 52036.0
        },
        {
            "provider": "VIETTEL",
            "type": "in",
            "total_seconds": 6519827.0
        },
        {
            "provider": "VINAPHONE",
            "type": "in",
            "total_seconds": 1699815.0
        },
        {
            "provider": "VIETTEL",
            "type": "out",
            "total_seconds": 372792.0
        },
        {
            "provider": "VINAPHONE",
            "type": "out",
            "total_seconds": 300446.0
        }
    ],
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

