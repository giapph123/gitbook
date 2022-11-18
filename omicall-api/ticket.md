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

{% swagger method="post" path="/api/ticket/update_status/:id_status" baseUrl="[URL]" summary="Cập nhật trạng thái ticket" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id_status" type="String" %}
Id
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Thông tin chi tiết ticket được update
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/api/ticket/category/get_all" baseUrl="[URL]" summary="Lấy danh sách chủ đề phiếu ghi" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": [
        {
            "_id": "6209c98561c1cb163ded2600",
            "created_date": 1644808581632,
            "last_updated_date": 1644808581632,
            "create_by": {
                "user_name": "OMI Hotline",
                "user_id": "6209c98561c1cb163ded25fa",
                "contact_id": null
            },
            "last_update_by": {
                "user_name": "OMI Hotline",
                "user_id": "6209c98561c1cb163ded25fa",
                "contact_id": null
            },
            "is_deleted": false,
            "status_set_id": "6209c98561c1cb163ded25fd",
            "dynamic_attribute_id": "6209c98561c1cb163ded25fe",
            "default_status": 0,
            "tenant_id": "6209c98461c1cb163ded25f7",
            "name": "Công việc",
            "name_unsigned": "Cong viec",
            "is_not_default": true,
            "type_config": null,
            "has_type_config": false,
            "types": [
                {
                    "uuid": "0",
                    "name": "Cá nhân",
                    "name_unsigned": "Ca nhan",
                    "index": 0,
                    "color": null,
                    "is_default": false,
                    "default_data": null,
                    "unit_price": null
                },
                {
                    "uuid": "1",
                    "name": "Tư vấn",
                    "name_unsigned": "Tu van",
                    "index": 1,
                    "color": null,
                    "is_default": false,
                    "default_data": null,
                    "unit_price": null
                },
                {
                    "uuid": "2",
                    "name": "Báo giá",
                    "name_unsigned": "Bao gia",
                    "index": 2,
                    "color": null,
                    "is_default": false,
                    "default_data": null,
                    "unit_price": null
                },
                {
                    "uuid": "3",
                    "name": "Chăm sóc",
                    "name_unsigned": "Cham soc",
                    "index": 3,
                    "color": null,
                    "is_default": false,
                    "default_data": null,
                    "unit_price": null
                }
            ],
            "contact_ids": null,
            "contact_category_ids": null,
            "role_enable": false,
            "has_default_value": true,
            "priority": "medium",
            "modify_priority_allowed": true,
            "modify_assignee_allowed": true,
            "modify_reporter_allowed": true,
            "modify_expire_allowed": true,
            "reopen": null,
            "assignee_contact_id": null,
            "assignee_contact_ids": null,
            "reporter_contact_ids": null,
            "assignee": null,
            "reporters": null,
            "notify_before": 15,
            "notify_before_unit": "minute",
            "notify_type": "web_email",
            "notify_at": null,
            "limit_days": 30,
            "processing_term": 7,
            "duration": null,
            "maximum_time": {
                "unit": "day",
                "value": 30
            },
            "minimum_time": {
                "unit": "hour",
                "value": 6
            },
            "description": null,
            "work_list": [],
            "has_hide_option": false,
            "hide_option": {
                "hide_after": null,
                "hide_after_unit": "day",
                "apply_for_assignee": false,
                "apply_for_reporter": false,
                "apply_for_creator": false,
                "apply_for_other_agent": false
            },
            "payment": null,
            "ticketStatusSet": {
                "_id": "6209c98561c1cb163ded25fd",
                "created_date": 1644808581573,
                "last_updated_date": 1644808581573,
                "create_by": {
                    "user_name": "OMI Hotline",
                    "user_id": "6209c98561c1cb163ded25fa",
                    "contact_id": null
                },
                "last_update_by": null,
                "is_deleted": false,
                "name": "Công việc",
                "name_unsigned": null,
                "tenant_id": "6209c98461c1cb163ded25f7",
                "status": [
                    {
                        "uuid": null,
                        "index": 0,
                        "sort_index": 0,
                        "color": "#4ca750",
                        "name": "Mới tạo",
                        "finish": false
                    },
                    {
                        "uuid": null,
                        "index": 1,
                        "sort_index": 1,
                        "color": "#267aff",
                        "name": "Đang xử lý",
                        "finish": false
                    },
                    {
                        "uuid": null,
                        "index": 2,
                        "sort_index": 2,
                        "color": "#57bfdb",
                        "name": "Từ chối",
                        "finish": false
                    },
                    {
                        "uuid": null,
                        "index": 3,
                        "sort_index": 3,
                        "color": "#2d4563",
                        "name": "Đã hoàn thành",
                        "finish": false
                    },
                    {
                        "uuid": null,
                        "index": 4,
                        "sort_index": 4,
                        "color": "#fea220",
                        "name": "Đóng",
                        "finish": true
                    }
                ],
                "is_not_default": true
            },
            "total": 4
        }
    ],
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}
