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

**Số nội bộ**

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

{% swagger method="get" path="/api/call_center/internal_group/get_all" baseUrl="[URL]" summary="Danh sách tất cả nhóm nội bộ" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" %}
Bearer Token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "status_code":9999,
   "instance_id":"stg",
   "instance_version":"1.2.163",
   "payload":[
      {
         "_id":"62ff11b208d4bf3ea694a6f3",
         "tenant_id":"6209c98461c1cb163ded25f7",
         "group_name":"Nhóm Tech",
         "group_name_unsigned":"Nhom Tech",
         "group_number":"38011",
         "created_date":1660883378087,
         "last_updated_date":1661221667904,
         "create_by":{
            "id":"6209c98561c1cb163ded25fa",
            "name":"OMI Hotline"
         },
         "last_update_by":{
            "id":"6209c98561c1cb163ded25fa",
            "name":"OMI Hotline"
         },
         "is_deleted":false,
         "note":null,
         "members":[
            {
               "agent_id":"62d563113127de2eac6b8cbf",
               "contact_id":"62d563113127de2eac6b8cbe",
               "order":0,
               "view":null,
               "timeout":30,
               "sip_user":null,
               "hold_music_id":null
            },
            {
               "agent_id":"6209c98561c1cb163ded25fa",
               "contact_id":"6209c98c067f745da47367d1",
               "order":0,
               "view":null,
               "timeout":30,
               "sip_user":null,
               "hold_music_id":null
            }
         ],
         "is_forward_to_user_owner":null,
         "is_forward_to_outer_group":false,
         "outer_group_id":null,
         "strategy":"enterprise",
         "ring_back_id":"",
         "ring_back_name":null,
         "is_answer":"false",
         "target_timeout_type":"",
         "target_timeout":"",
         "target_timeout_name":null,
         "ring_group_type":0,
         "ring_group_wait_time":0,
         "ring_group_wait_time_sequence":2,
         "ring_group_type_result":null,
         "enable_criteria":false,
         "criterias":[
            
         ]
      },
      {
         "_id":"62ff11a208d4bf3ea694a539",
         "tenant_id":"6209c98461c1cb163ded25f7",
         "group_name":"Nhóm Sales",
         "group_name_unsigned":"Nhom Sales",
         "group_number":"62714",
         "created_date":1660883362155,
         "last_updated_date":1667615822209,
         "create_by":{
            "id":"6209c98561c1cb163ded25fa",
            "name":"OMI Hotline"
         },
         "last_update_by":{
            "id":"6209c98561c1cb163ded25fa",
            "name":"OMI Hotline"
         },
         "is_deleted":false,
         "note":null,
         "members":[
            {
               "agent_id":"62d563113127de2eac6b8cbf",
               "contact_id":"62d563113127de2eac6b8cbe",
               "order":0,
               "view":null,
               "timeout":30,
               "sip_user":null,
               "hold_music_id":null
            },
            {
               "agent_id":"6209c98561c1cb163ded25fa",
               "contact_id":"6209c98c067f745da47367d1",
               "order":0,
               "view":null,
               "timeout":30,
               "sip_user":null,
               "hold_music_id":null
            }
         ],
         "is_forward_to_user_owner":null,
         "is_forward_to_outer_group":false,
         "outer_group_id":null,
         "strategy":"enterprise",
         "ring_back_id":"",
         "ring_back_name":null,
         "is_answer":"false",
         "target_timeout_type":"",
         "target_timeout":"",
         "target_timeout_name":null,
         "ring_group_type":0,
         "ring_group_wait_time":0,
         "ring_group_wait_time_sequence":0,
         "ring_group_type_result":null,
         "enable_criteria":false,
         "criterias":[
            
         ]
      },
      {
         "_id":"62ff119508d4bf3ea694a44a",
         "tenant_id":"6209c98461c1cb163ded25f7",
         "group_name":"Nhóm CSKH",
         "group_name_unsigned":"Nhom CSKH",
         "group_number":"54807",
         "created_date":1660883349783,
         "last_updated_date":1660883349783,
         "create_by":{
            "id":"6209c98561c1cb163ded25fa",
            "name":"OMI Hotline"
         },
         "last_update_by":null,
         "is_deleted":false,
         "note":null,
         "members":[
            {
               "agent_id":"6209c98561c1cb163ded25fa",
               "contact_id":"6209c98c067f745da47367d1",
               "order":0,
               "view":null,
               "timeout":30,
               "sip_user":null,
               "hold_music_id":null
            }
         ],
         "is_forward_to_user_owner":null,
         "is_forward_to_outer_group":false,
         "outer_group_id":null,
         "strategy":"enterprise",
         "ring_back_id":"",
         "ring_back_name":null,
         "is_answer":"false",
         "target_timeout_type":"",
         "target_timeout":"",
         "target_timeout_name":null,
         "ring_group_type":0,
         "ring_group_wait_time":0,
         "ring_group_wait_time_sequence":2,
         "ring_group_type_result":null,
         "enable_criteria":false,
         "criterias":[
            
         ]
      }
   ],
   "key_enabled":false
}
```
{% endswagger-response %}
{% endswagger %}
