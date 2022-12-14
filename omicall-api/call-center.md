---
description: Quản lý cấu hình tổng đài , số nội bộ
---

# Tổng đài

{% swagger baseUrl="[URL]" path="/api/call_center/internal_phone/list" method="get" summary="Danh sách SỐ NỘI BỘ " %}
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

{% swagger method="get" path="/api/call_center/internal_group/list" baseUrl="[URL]" summary="Danh sách NHÓM NỘI BỘ" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" %}
Bearer Token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keyword" type="String" %}
Từ khoá tìm kiếm
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="Integer" %}
Trang (Bắt đầu từ 1). Mặc định là 1
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="Integer" %}
Kích thước trang (mặc định là 10)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "items": [
            {
                "_id": "62ff11b208d4bf3ea694a6f3",
                "tenant_id": "6209c98461c1cb163ded25f7",
                "group_name": "Nhóm Tech",
                "group_name_unsigned": "Nhom Tech",
                "group_number": "38011",
                "created_date": 1660883378087,
                "last_updated_date": 1661221667904,
                "create_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "last_update_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "is_deleted": false,
                "note": null,
                "members": [
                    {
                        "agent_id": "62d563113127de2eac6b8cbf",
                        "contact_id": "62d563113127de2eac6b8cbe",
                        "order": 0,
                        "view": null,
                        "timeout": 30,
                        "sip_user": null,
                        "hold_music_id": null
                    },
                    {
                        "agent_id": "6209c98561c1cb163ded25fa",
                        "contact_id": "6209c98c067f745da47367d1",
                        "order": 0,
                        "view": null,
                        "timeout": 30,
                        "sip_user": null,
                        "hold_music_id": null
                    }
                ],
                "is_forward_to_user_owner": null,
                "is_forward_to_outer_group": false,
                "outer_group_id": null,
                "strategy": "enterprise",
                "ring_back_id": "",
                "ring_back_name": null,
                "is_answer": "false",
                "target_timeout_type": "",
                "target_timeout": "",
                "target_timeout_name": null,
                "ring_group_type": 0,
                "ring_group_wait_time": 0,
                "ring_group_wait_time_sequence": 2,
                "ring_group_type_result": null,
                "enable_criteria": false,
                "criterias": []
            },
            {
                "_id": "62ff11a208d4bf3ea694a539",
                "tenant_id": "6209c98461c1cb163ded25f7",
                "group_name": "Nhóm Sales",
                "group_name_unsigned": "Nhom Sales",
                "group_number": "62714",
                "created_date": 1660883362155,
                "last_updated_date": 1667615822209,
                "create_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "last_update_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "is_deleted": false,
                "note": null,
                "members": [
                    {
                        "agent_id": "62d563113127de2eac6b8cbf",
                        "contact_id": "62d563113127de2eac6b8cbe",
                        "order": 0,
                        "view": null,
                        "timeout": 30,
                        "sip_user": null,
                        "hold_music_id": null
                    },
                    {
                        "agent_id": "6209c98561c1cb163ded25fa",
                        "contact_id": "6209c98c067f745da47367d1",
                        "order": 0,
                        "view": null,
                        "timeout": 30,
                        "sip_user": null,
                        "hold_music_id": null
                    }
                ],
                "is_forward_to_user_owner": null,
                "is_forward_to_outer_group": false,
                "outer_group_id": null,
                "strategy": "enterprise",
                "ring_back_id": "",
                "ring_back_name": null,
                "is_answer": "false",
                "target_timeout_type": "",
                "target_timeout": "",
                "target_timeout_name": null,
                "ring_group_type": 0,
                "ring_group_wait_time": 0,
                "ring_group_wait_time_sequence": 0,
                "ring_group_type_result": null,
                "enable_criteria": false,
                "criterias": []
            },
            {
                "_id": "62ff119508d4bf3ea694a44a",
                "tenant_id": "6209c98461c1cb163ded25f7",
                "group_name": "Nhóm CSKH",
                "group_name_unsigned": "Nhom CSKH",
                "group_number": "54807",
                "created_date": 1660883349783,
                "last_updated_date": 1660883349783,
                "create_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "last_update_by": null,
                "is_deleted": false,
                "note": null,
                "members": [
                    {
                        "agent_id": "6209c98561c1cb163ded25fa",
                        "contact_id": "6209c98c067f745da47367d1",
                        "order": 0,
                        "view": null,
                        "timeout": 30,
                        "sip_user": null,
                        "hold_music_id": null
                    }
                ],
                "is_forward_to_user_owner": null,
                "is_forward_to_outer_group": false,
                "outer_group_id": null,
                "strategy": "enterprise",
                "ring_back_id": "",
                "ring_back_name": null,
                "is_answer": "false",
                "target_timeout_type": "",
                "target_timeout": "",
                "target_timeout_name": null,
                "ring_group_type": 0,
                "ring_group_wait_time": 0,
                "ring_group_wait_time_sequence": 2,
                "ring_group_type_result": null,
                "enable_criteria": false,
                "criterias": []
            },
            {
                "_id": "6209c99b067f745da47367f4",
                "tenant_id": "6209c98461c1cb163ded25f7",
                "group_name": "Nhóm nhân viên mặc định",
                "group_name_unsigned": "Nhom nhan vien mac dinh",
                "group_number": "54919",
                "created_date": 1644808603212,
                "last_updated_date": 1662705652281,
                "create_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "last_update_by": {
                    "id": "6209c98561c1cb163ded25fa",
                    "name": "OMI Hotline"
                },
                "is_deleted": false,
                "note": null,
                "members": [
                    {
                        "agent_id": "6209c98561c1cb163ded25fa",
                        "contact_id": "6209c98c067f745da47367d1",
                        "order": 0,
                        "view": null,
                        "timeout": 30,
                        "sip_user": null,
                        "hold_music_id": null
                    }
                ],
                "is_forward_to_user_owner": null,
                "is_forward_to_outer_group": false,
                "outer_group_id": null,
                "strategy": "enterprise",
                "ring_back_id": "",
                "ring_back_name": null,
                "is_answer": "false",
                "target_timeout_type": "Voice_mail",
                "target_timeout": "62da34652a310904dfbbf13b",
                "target_timeout_name": null,
                "ring_group_type": 0,
                "ring_group_wait_time": 0,
                "ring_group_wait_time_sequence": 0,
                "ring_group_type_result": null,
                "enable_criteria": false,
                "criterias": []
            }
        ],
        "page_number": 1,
        "page_size": 10,
        "total_items": 4,
        "total_pages": 1,
        "has_next": false,
        "next_page": 1,
        "has_previous": false,
        "previous_page": 1,
        "extension": null
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/internal_group/add" baseUrl="[URL]" summary="Tạo NHÓM NỘI BỘ" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="group_name" required="true" type="String" %}
Tên nhóm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="strategy" required="true" type="String" %}
Hình thức đổ chuông của nhóm, Một trong các giá trị dưới

**enterprise** : Đồng thời&#x20;

**rollover** : Tuần tự

**random** : Ngẫu nhiên
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sip_members" type="Array" required="true" %}
Danh sách số máy lẻ nhân viên cần thêm vào nhóm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="timeout" type="Integer" required="true" %}
Thời gian chờ TỪNG NHÂN VIÊN
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
````javascript
```json
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "_id": "6391f5be232ce4664531e0cc",
        "tenant_id": "6209c98461c1cb163ded25f7",
        "group_name": "tientv11",
        "group_name_unsigned": "tientv11",
        "group_number": "22412",
        "created_date": 1670510011881,
        "last_updated_date": 1670510011881,
        "create_by": {
            "id": "6209c98561c1cb163ded25fa",
            "name": "OMI Hotline"
        },
        "last_update_by": null,
        "is_deleted": false,
        "note": null,
        "members": [
            {
                "agent_id": "6209c98561c1cb163ded25fa",
                "contact_id": "6209c98c067f745da47367d1",
                "order": 0,
                "view": null,
                "timeout": 30,
                "sip_user": null,
                "hold_music_id": null
            }
        ],
        "is_forward_to_user_owner": null,
        "is_forward_to_outer_group": false,
        "outer_group_id": null,
        "strategy": "random",
        "ring_back_id": null,
        "ring_back_name": null,
        "is_answer": null,
        "target_timeout_type": null,
        "target_timeout": null,
        "target_timeout_name": null,
        "ring_group_type": null,
        "ring_group_wait_time": null,
        "ring_group_wait_time_sequence": null,
        "ring_group_type_result": null,
        "enable_criteria": null,
        "criterias": null,
        "sip_members": [
            "100"
        ],
        "timeout": 30
    },
    "key_enabled": false
}
```
````
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/internal_group/update/:id" baseUrl="[URL]" summary="Cập nhật NHÓM NỘI BỘ" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="group_name" required="true" type="String" %}
Tên nhóm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="strategy" required="true" type="String" %}
Hình thức đổ chuông của nhóm, Một trong các giá trị dưới

**enterprise** : Đồng thời&#x20;

**rollover** : Tuần tự

**random** : Ngẫu nhiên
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sip_members" required="true" type="String" %}
Danh sách số máy lẻ nhân viên cần thêm vào nhóm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="timeout" type="Integer" required="true" %}
Thời gian chờ từng nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="path" name="id" required="true" type="String" %}
Id của NHÓM NỘI BỘ
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
````javascript
```json
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "_id": "6391f5be232ce4664531e0cc",
        "tenant_id": "6209c98461c1cb163ded25f7",
        "group_name": "tientv11",
        "group_name_unsigned": "tientv11",
        "group_number": "22412",
        "created_date": 1670510011881,
        "last_updated_date": 1670510241349,
        "create_by": {
            "id": "6209c98561c1cb163ded25fa",
            "name": "OMI Hotline"
        },
        "last_update_by": {
            "id": "6209c98561c1cb163ded25fa",
            "name": "OMI Hotline"
        },
        "is_deleted": false,
        "note": null,
        "members": [
            {
                "agent_id": "6209c98561c1cb163ded25fa",
                "contact_id": "6209c98c067f745da47367d1",
                "order": 0,
                "view": null,
                "timeout": 30,
                "sip_user": null,
                "hold_music_id": null
            }
        ],
        "is_forward_to_user_owner": null,
        "is_forward_to_outer_group": false,
        "outer_group_id": null,
        "strategy": "enterprise",
        "ring_back_id": "",
        "ring_back_name": null,
        "is_answer": "false",
        "target_timeout_type": "",
        "target_timeout": "",
        "target_timeout_name": null,
        "ring_group_type": 0,
        "ring_group_wait_time": 0,
        "ring_group_wait_time_sequence": 0,
        "ring_group_type_result": null,
        "enable_criteria": false,
        "criterias": [],
        "sip_members": [
            "100"
        ],
        "timeout": 30
    },
    "key_enabled": false
}
```
````
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/internal_group/add-members" baseUrl="[URL]" summary="THÊM nhân viên vào NHÓM NỘI BỘ" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="group_id" type="String" required="true" %}
Id của nhóm nội bộ
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sip_users" type="Array" required="true" %}
Danh sách các số máy lẻ , thêm vào nhóm
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/internal_group/remove-members" baseUrl="[URL]" summary="XOÁ nhân viên khỏi NHÓM NỘI BỘ" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="group_id" type="String" required="true" %}
Id của nhóm nội bộ
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sip_users" type="Array" required="true" %}
Danh sách số máy lẻ nhân viên cần xoá 
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="get" path="/api/call_center/key-interaction/list" baseUrl="[URL]" summary="Danh sách KỊCH BẢN BẤM PHÍM" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="keyword" type="String" %}
Từ khoá tìm kiếm
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="Integer" required="true" %}
Trang
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="Integer" required="true" %}
Kích thước trang
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
            "_id":"632969ce7534d97b0933d51d",
            "tenant_id":"6209c98461c1cb163ded25f7",
            "script_name":"KỊCH BẢN BẤM PHÍM",
            "script_name_unsigned":"KICH BAN BAM PHIM",
            "script_number":"166780",
            "greeting_id":"6209c99b067f745da47367f3",
            "greeting_name":null,
            "greeting_short_id":"",
            "greeting_short_name":null,
            "note":null,
            "created_date":1663658446348,
            "created_by":{
               "id":"6209c98561c1cb163ded25fa",
               "name":"OMI Hotline"
            },
            "last_updated_date":1663658542212,
            "last_updated_by":{
               "id":"6209c98561c1cb163ded25fa",
               "name":"OMI Hotline"
            },
            "is_deleted":false,
            "scripts":[
               {
                  "key":null,
                  "action_type":"Ring_group",
                  "action":"62ff119508d4bf3ea694a44a",
                  "action_name":null,
                  "ivr":"1"
               },
               {
                  "key":null,
                  "action_type":"Ring_group",
                  "action":"62ff119508d4bf3ea694a44a",
                  "action_name":null,
                  "ivr":"2"
               },
               {
                  "key":null,
                  "action_type":"",
                  "action":"",
                  "action_name":null,
                  "ivr":"3"
               },
               {
                  "key":null,
                  "action_type":"",
                  "action":"",
                  "action_name":null,
                  "ivr":"4"
               },
               {
                  "key":null,
                  "action_type":"",
                  "action":"",
                  "action_name":null,
                  "ivr":"5"
               }
            ],
            "time_out":3,
            "action_type":"",
            "action":"",
            "action_name":null,
            "invalid_sound_id":"",
            "invalid_sound_name":null,
            "max_failure":1,
            "ivr_direct_menu_dial":null
         }
      ],
      "page_number":1,
      "page_size":10,
      "total_items":1,
      "total_pages":1,
      "has_next":false,
      "next_page":1,
      "has_previous":false,
      "previous_page":1,
      "extension":null
   },
   "key_enabled":false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/key-interaction/add" baseUrl="[URL]" summary="Tạo mới KỊCH BẢN BẤM PHÍM" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="script_name" type="String" required="true" %}
Tên kịch bản bấm phím (Chú ý không được trùng)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="greeting_id" type="String" required="true" %}
Id của file ghi âm (API upload file ghi âm)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="max_failure" type="Integer" required="true" %}
Số lần nhấn sai phím
{% endswagger-parameter %}

{% swagger-parameter in="body" name="time_out" type="Integer" required="true" %}
Thời gian chờ KH bấm phím,  hoặc Khi  kết thúc file ghi âm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scripts" type="Array" required="true" %}
Danh sách mảng đối tượng phím

Cách loại kịch bản đi kèm với phím bấm.\
**Thành phần là nhóm nội bộ**

{

&#x20;  "ivr" : "", //Tên phím 1,2,3..

&#x20;   "action": "xxxxxxxx" // Id của nhóm nội bộ

&#x20; "action\_type":"_Ring\_group_"

}

**Thành phần là kịch bản bấm phím**&#x20;

{

&#x20;  "ivr" : "", //Tên phím 1,2,3..

&#x20;   "action": "xxxxxxxx" // Id Kịch bản bấm phím.

&#x20; "action\_type":"_Ivr\_menu_"

}


{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "status_code":9999,
   "instance_id":"stg",
   "instance_version":"1.2.163",
   "payload":{
      "_id":"632969ce7534d97b0933d51d",
      "tenant_id":"6209c98461c1cb163ded25f7",
      "script_name":"KỊCH BẢN BẤM PHÍM",
      "script_name_unsigned":"KICH BAN BAM PHIM",
      "script_number":"166780",
      "greeting_id":"62da34652a310904dfbbf13b",
      "greeting_name":null,
      "greeting_short_id":"",
      "greeting_short_name":null,
      "note":null,
      "created_date":1663658446348,
      "created_by":{
         "id":"6209c98561c1cb163ded25fa",
         "name":"OMI Hotline"
      },
      "last_updated_date":1670644627322,
      "last_updated_by":{
         "id":"6209c98561c1cb163ded25fa",
         "name":"OMI Hotline"
      },
      "is_deleted":false,
      "scripts":[
         {
            "key":null,
            "action_type":"Ivr_menu",
            "action":"6391fa5f44b0fb4429b580c0",
            "action_name":null,
            "ivr":"1"
         },
         {
            "key":null,
            "action_type":"",
            "action":"",
            "action_name":null,
            "ivr":"5"
         }
      ],
      "time_out":3,
      "action_type":"",
      "action":"",
      "action_name":null,
      "invalid_sound_id":"6209c99b067f745da47367f3",
      "invalid_sound_name":null,
      "max_failure":1,
      "ivr_direct_menu_dial":"false"
   },
   "key_enabled":false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/key-interaction/update" baseUrl="[URL]" summary="Cập nhật KỊCH BẢN BẤM PHÍM" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="script_name" type="String" required="true" %}
Tên kịch bản bấm phím
{% endswagger-parameter %}

{% swagger-parameter in="body" name="greeting_id" type="String" required="true" %}
Id file ghi âm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="max_failure" type="Integer" required="true" %}
Số lần nhấn sai phím
{% endswagger-parameter %}

{% swagger-parameter in="body" name="time_out" type="Integer" required="true" %}
Thời gian chờ KH nhấn phím hoặc lời chào kết thúc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scripts" type="Array" required="true" %}
Danh sách mảng đối tượng phím

Cách loại kịch bản đi kèm với phím bấm.\
**Thành phần là nhóm nội bộ**

{

&#x20;  "ivr" : "", //Tên phím 1,2,3..

&#x20;   "action": "xxxxxxxx" // Id của nhóm nội bộ

&#x20; "action\_type":"_Ring\_group_"

}

**Thành phần là kịch bản bấm phím**&#x20;

{

&#x20;  "ivr" : "", //Tên phím 1,2,3..

&#x20;   "action": "xxxxxxxx" // Id Kịch bản bấm phím.

&#x20; "action\_type":"_Ivr\_menu_"

}


{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "status_code":9999,
   "instance_id":"stg",
   "instance_version":"1.2.163",
   "payload":{
      "_id":"632969ce7534d97b0933d51d",
      "tenant_id":"6209c98461c1cb163ded25f7",
      "script_name":"KỊCH BẢN BẤM PHÍM",
      "script_name_unsigned":"KICH BAN BAM PHIM",
      "script_number":"166780",
      "greeting_id":"62da34652a310904dfbbf13b",
      "greeting_name":null,
      "greeting_short_id":"",
      "greeting_short_name":null,
      "note":null,
      "created_date":1663658446348,
      "created_by":{
         "id":"6209c98561c1cb163ded25fa",
         "name":"OMI Hotline"
      },
      "last_updated_date":1670644627322,
      "last_updated_by":{
         "id":"6209c98561c1cb163ded25fa",
         "name":"OMI Hotline"
      },
      "is_deleted":false,
      "scripts":[
         {
            "key":null,
            "action_type":"Ivr_menu",
            "action":"6391fa5f44b0fb4429b580c0",
            "action_name":null,
            "ivr":"1"
         },
         {
            "key":null,
            "action_type":"",
            "action":"",
            "action_name":null,
            "ivr":"5"
         }
      ],
      "time_out":3,
      "action_type":"",
      "action":"",
      "action_name":null,
      "invalid_sound_id":"6209c99b067f745da47367f3",
      "invalid_sound_name":null,
      "max_failure":1,
      "ivr_direct_menu_dial":"false"
   },
   "key_enabled":false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/api/call_center/greeting/list" baseUrl="[URL]" summary="Danh sách file ghi âm" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="page" type="Integer" required="true" %}
Trang (bắt đầu từ 1)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="Integer" required="true" %}
Kích thước trang (mặc định 10)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
````javascript

{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "items": [
            {
                "_id": "6391f975b4c5c92743725fa3",
                "created_date": 1670510965969,
                "last_updated_date": 1670510965977,
                "create_by": null,
                "last_update_by": null,
                "tenant_id": "6209c98461c1cb163ded25f7",
                "greeting_name": "Name 1",
                "greeting_name_unsigned": "name 1",
                "formality": "Robot đọc",
                "recording_file": "6c0d4c55-d837-4ae5-835e-c16180b09e51.mp3",
                "content": "Name 1",
                "voice": "banmai",
                "speed": 0,
                "is_deleted": false,
                "is_hidden_in_list": null
            },
            {
                "_id": "634944c8df71333e7787e03d",
                "created_date": 1665746120033,
                "last_updated_date": 1665746120033,
                "create_by": null,
                "last_update_by": null,
                "tenant_id": "6209c98461c1cb163ded25f7",
                "greeting_name": "Thêm mới thành công",
                "greeting_name_unsigned": "them moi thanh cong",
                "formality": "Robot đọc",
                "recording_file": "d1969275-e403-438f-935c-6425d1550692.mp3",
                "content": "Thêm mới thành công",
                "voice": "banmai",
                "speed": 0,
                "is_deleted": false,
                "is_hidden_in_list": null
            },
            {
                "_id": "634944a5823f5332401ec9c3",
                "created_date": 1665746085884,
                "last_updated_date": 1665746085884,
                "create_by": null,
                "last_update_by": null,
                "tenant_id": "6209c98461c1cb163ded25f7",
                "greeting_name": "Thêm mới",
                "greeting_name_unsigned": "them moi",
                "formality": "Robot đọc",
                "recording_file": "d8bc922b-cabf-4e28-8198-6021f5b82c14.mp3",
                "content": "Thêm mới thành công hay thất bại",
                "voice": "banmai",
                "speed": 0,
                "is_deleted": false,
                "is_hidden_in_list": null
            }
        ],
        "page_number": 1,
        "page_size": 3,
        "total_items": 13,
        "total_pages": 5,
        "has_next": true,
        "next_page": 2,
        "has_previous": false,
        "previous_page": 1,
        "extension": null
    },
    "key_enabled": false
}
```
````
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/greeting/upload" baseUrl="[URL]" summary="Upload file ghi âm" %}
{% swagger-description %}
Chú ý : 

**Request là form-data và chỉ hỗ trợ mp3**
{% endswagger-description %}

{% swagger-parameter in="query" name="greeting_name" type="String" required="false" %}
Tên file
{% endswagger-parameter %}

{% swagger-parameter in="body" name="file" type="Binary" required="true" %}
Dữ liệu của file
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="post" path="/api/call_center/greeting/upload-text-to-speech" baseUrl="[URL]" summary="Upload file ghi âm : Robot đọc (Text To Speech)" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="text" type="String" required="true" %}
Nội dung cần đọc 

**<= 300 ký tự**

 
{% endswagger-parameter %}

{% swagger-parameter in="query" name="greeting_name" type="String" required="true" %}
Tên file ghi âm
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speed" type="String" required="true" %}
Tốc độ đọc, Giá trị từ  -3 - 3\
\- 3 : Cực kì chậm\
\-2 : Rất chậm\
\-1 : Chậm\
0 : Bình thường\
1 : Nhanh\
...


{% endswagger-parameter %}

{% swagger-parameter in="body" name="voice" type="String" required="true" %}
Giọng đọc, có thể một trong các giá trị sau

\




**banmai**

 : Giọng nữ miền Bắc

\




**leminh**

 : Giọng nam miền Bắc

\




**lannhi**

 : Giọng nữ miền Nam
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
````javascript
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "file": {
            "_id": "639981151ee2ed6f5bbeea90",
            "created_date": 1671004437213,
            "last_updated_date": 1671004437213,
            "create_by": null,
            "last_update_by": null,
            "tenant_id": "6209c98461c1cb163ded25f7",
            "greeting_name": "Nhắc lịch đào tạo",
            "greeting_name_unsigned": "Nhac lich dao tao",
            "formality": "Robot đọc",
            "recording_file": "a6c2edd9-9af1-4e71-98a7-657c3c1e0466.mp3",
            "content": "Bạn có một lịch họp sắp đến giờ, bạn vui lòng chú ý thời gian để đến đúng giờ",
            "voice": "banmai",
            "speed": 0,
            "is_deleted": false,
            "is_hidden_in_list": null
        }
    },
    "key_enabled": false
}
```
````
{% endswagger-response %}
{% endswagger %}

