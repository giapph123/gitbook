---
description: '- Báo cáo sản lượng tổng nhà cung cấp'
---

# Báo cáo sản lượng nhà cung cấp

{% api-method method="get" host="\[URL\]" path="/supplier/report" %}
{% api-method-summary %}
Báo cáo tổng sản lượng
{% endapi-method-summary %}

{% api-method-description %}
- Lấy sản lượng tổng nội và ngoại mạng  
- Sản lượng nhận được sẽ bằng **20% sản lượng thực tế**  
- API sẽ cập nhật số liệu sau 60 phút. Nếu request sau cách request trước chưa tới 60 phút, thì sẽ nhận sản lượng trước đó
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="provider\_key" type="string" required=true %}
KEY cung cấp nhà Supplier
{% endapi-method-parameter %}

{% api-method-parameter name="from\_date\_str" type="string" %}
Từ ngày \(dd/MM/yyyy HH:mm:ss\)   
Mặc định là ngày đầu tháng
{% endapi-method-parameter %}

{% api-method-parameter name="to\_date\_str" type="boolean" %}
Đến ngày \(dd/MM/yyyy HH:mm:ss\)  
Mặc định là ngày hiện tại 
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Sản lượng nội và ngoại mạng
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



