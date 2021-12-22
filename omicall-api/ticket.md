---
description: Quản lý ticket
---

# Ticket

{% swagger method="post" path="/api/ticket/list" baseUrl="[URL]" summary="Lấy danh sách ticket" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="keyword" %}
Từ khóa tìm kiếm, Id ticket, nhân viên tiếp nhận hoặc nhân viên liên quan
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="Integer" required="true" %}
Chỉ số trang, bắt đầu bằng 1
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="Integer" required="true" %}
Kích thước trang, mặc định là 50
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "status_code":9999,
   "instance_id":"stg",
   "instance_version":"1.2.163",
   "payload":{
      "items":[
         {
            "_id":"61c04292530c6a0efa4fa171",
            "created_date":1639989906385,
            "last_updated_date":1640101239690,
            "create_by":{ // Người tạo
               
            },
            "last_updated_by":null,
            "priority":"medium", // Độ ưu tiên (low,medium,high)
            "name":"", // Tựa đề
            "description":"", // Mô tả
            "current_status":1,  // Trạng thái
            "is_expired":false, // hết hạn
            "unique_id":"2188", // Id ticket
         },
         .....
      ],
      "page_number":1,
      "page_size":15,
      "total_items":165,
      "total_pages":11,
      "has_next":true,
      "next_page":2,
      "has_previous":false,
      "previous_page":1,
      "extension":null
   },
   "key_enabled":false
}
            
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/ticket/create" baseUrl="[URL]" summary="Tạo ticket" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="name" type="String" required="true" %}
Tên ticket
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" required="true" %}
Mô tả ticket
{% endswagger-parameter %}

{% swagger-parameter in="body" name="priority" type="String" required="true" %}
Độ ưu tiên (mặc định là medium)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="assignee" type="String" required="true" %}
Email nhân viên được gán
{% endswagger-parameter %}

{% swagger-parameter in="body" name="created_by" type="String" %}
Email nhân viên tạo ticket, nếu rỗng thì là Admin 
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Thông tin chi tiết 1 ticket
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}
