---
description: Quản lý khách hàng
---

# Khách hàng

{% swagger baseUrl="[URL]" path="/api/contacts/list" method="post" summary="Tìm kiếm khách hàng" %}
{% swagger-description %}
Tìm kiếm khách hàng
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Bearer Access: Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="number" %}
Trang. Bắt đầu từ 1. Mặc định là 1
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="number" %}
Kích thước trang. Mặc định là 50
{% endswagger-parameter %}

{% swagger-parameter in="body" name="keyword" type="String" %}
Từ khóa tìm kiếm. Có thể một trong các giá trị

\


\- Số điện thoại

\


\- Email

\


\- Họ và tên
{% endswagger-parameter %}

{% swagger-parameter in="body" name="filters" type="Array" %}
Lọc \
"filters": \[ \
{ \
&#x20;  "field\_code" : "contact\_owner", // Người phụ trách\
&#x20;   "value":\[

&#x20;          "unassigned",  // chưa gán&#x20;

&#x20;           "agent1@gmail.com" // Email nhân nhân viên&#x20;

&#x20;     ]&#x20;

} ]
{% endswagger-parameter %}

{% swagger-response status="200" description="Dữ liệu trả về thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": {
        "next_page": 1,
        "page_number": 1,
        "has_previous": false,
        "has_next": false,
        "total_pages": 1,
        "previous_page": 1,
        "total_items": 1,
        "page_size": 50
        "items": [
            {
                "public_id": "", // Id
                "create_by": {
                    "name": "TestBoss 123"
                },
                "last_update_by": {
                    "name": "TestBoss 123"
                },
                "created_date": 1576229754881,
                "last_updated_date": 1580807004410,
                "contact_type": "contact",
                "tags_view": null,
                "is_deleted": false, // Trạng thái
                "tags": [], // Thẻ tags khách hàng
                "attribute_structure": [
                    {
                        "identify": false,
                        "field_code": "full_name",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "Trần Văn Tiến 1",
                                "data_type": null,
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "job_title",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "Giám đốc",
                                "data_type": null,
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "gender",
                        "field_type": "radio",
                        "value": [
                            {
                                "display_value": "male",
                                "data_type": null,
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "phone_number",
                        "field_type": "phone",
                        "value": [
                            {
                                "display_value": "0395187319",
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "mail",
                        "field_type": "email",
                        "value": [
                            {
                                "display_value": "tientv1212@gmail.com",
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "address",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "Số 6 , đường 16, Hiệp Bình Chánh, Thủ Đức, HCM",
                                "data_type": null,
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "passport",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "",
                                "data_type": null,
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "note",
                        "field_type": "multi_text",
                        "value": [
                            {
                                "display_value": "Khách hàng VIP, cần được chăm sóc kĩ",
                                "data_type": null,
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "more_infomation",
                        "field_type": "customize",
                        "value": [
                            {
                                "display_value": "Nguyễn Văn B",
                                "data_type": "value1",
                                "value_type": "Người thân"
                            },
                            {
                                "display_value": "Vàng",
                                "data_type": "label2",
                                "value_type": "Màu sắc yêu thích"
                            }
                        ]
                    }
                ]
            }
        ]
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/contacts/add" method="post" summary="Tạo mới khách hàng" %}
{% swagger-description %}
Tạo mới khách hàng
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Bearer Access: Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="array" %}
Danh sách thẻ tags

\


Ví dụ : 

`"tags" : ["Khách lẻ", "Khách có nhu cầu"]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="more_infomation" type="array" %}
Thông tin trường tùy chỉnh

\


Ví dụ

\




`[`

\


`{value_type : "Cao",  display_value: "1.75m"},`

\


`{value_type:"Nặng", display_value : "75kg"}`

\


`{value_type:"Điểm", display_value: "90"}`

\


`]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user_owner_email" type="string" %}
Email nhân viên phụ trách 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refId" type="string" %}
Id của khách hàng bên đối tác
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refCode" type="string" %}
Mã của khách hàng bên đối tác
{% endswagger-parameter %}

{% swagger-parameter in="body" name="job_title" type="string" %}
Công việc / chức vụ của khách hàng
{% endswagger-parameter %}

{% swagger-parameter in="body" name="note" type="string" %}
Ghi chú về khách hàng
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birthday" type="string" %}
Ngày tháng năm sinh, định dạng : (dd/MM/yyyy)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" type="string" %}
Giới tính gồm ( '

**other**

' : Giới tính khác; '

**male**

' : Nam; '

**female**

' : Nữ)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fullName" type="string" %}
Họ và tên
{% endswagger-parameter %}

{% swagger-parameter in="body" name="passport" type="string" %}
Hộ chiếu hoặc Id card
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="string" %}
Địa chỉ
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emails" type="array" %}
Danh sách đối tượng EMAIL

\


Ví dụ :

\




`[{`

\


 

`data: "tientv@demo.com.nv",`

 

\


 

`value: "home", // home, personal, office`

\


 

`valueType: "Nhà" // Nhà, Cá nhân, Công ty`

\


`}]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phones" type="array" %}
Danh sách đối tượng PHONE

\


Ví dụ :

\




`[{`

\


 

`data: "02525485xxx",`

\


 

`value : "home", // home, personal, office`

\


 

`valueType : "Nhà" // Nhà, Cá nhân, Công ty`

\


`}]`
{% endswagger-parameter %}

{% swagger-response status="200" description="Dữ liệu trả về khi yêu cầu thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": {
        {
                "create_by": {
                    "name": "TRẦN VĂN, Tiến"
                },
                "last_update_by": null,
                "created_date": 1587023890765,
                "last_updated_date": 1588826965324,
                "public_id": "ad1a7e78d80b94544ab92456",
                "contact_type": "contact",
                "tags_view": [],
                "is_deleted": false,
                "tags": [],
                "attribute_structure": [
                    {
                        "identify": false,
                        "field_code": "full_name",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "Trần Văn Tiến",
                                "data_type": "",
                                "value_type": ""
                            }
                        ]
                    },
                    {
                        "identify": false,
                        "field_code": "job_title",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "Trần Văn Tiến",
                                "data_type": "",
                                "value_type": ""
                            }
                        ]
                    },
                    .....
                ]
            }
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL" path="/api/contacts/add-more" method="post" summary="Tạo nhiều khách hàng" %}
{% swagger-description %}
Tạo danh nhiều khách hàng, Request Body là array Object đối tượng khách hàng lúc tạo mới. 

\


API xử lý bất đồng bộ
{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Access token: Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="path" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200" description="Tạo danh sách thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "payload": true,
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/contacts/update" method="post" summary="Sửa thông tin khách hàng" %}
{% swagger-description %}
Sửa thông tin khách hàng
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token : Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="array" %}
Danh sách thẻ tags

\


Ví dụ : 

`"tags":["Khách lẻ","Khách có nhu cầu"]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refId" type="string" %}
Id khách hàng
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birthday" type="string" %}
Ngày tháng năm sinh: định dạng (dd/MM/yyyy)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="more_infomation" type="array" %}
Thông tin trường tùy chỉnh

\




`[`

\


`{"value_type":"Điểm","display_value":"20"},`

\


`{"value_type":"Đơn","display_value":"10"},`

\


`{"value_type":"Tiền","display_value":"500000"}`

\


`]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user_owner_email" type="string" %}
Email người phụ trách
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fullName" type="string" %}
Họ và tên
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" type="string" %}
Giới tính ('

**other**

' : Giới tính khác; '

**male**

' : Nam; '

**female**

' : Nữ)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="passport" type="string" %}
Hộ chiếu hoặc id card
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="string" %}
Địa chỉ
{% endswagger-parameter %}

{% swagger-parameter in="body" name="note" type="string" %}
Ghi chú
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emails" type="array" %}
Danh sách đối tượng EMAILS 

\


Ví dụ : 

\




`[{`

\


 

`data : "tientv@demo.com.vn",`

\


 

`type: "home", // home, personal, office`

\


 

`valueType: "Nhà" // Nhà, Cá nhân, Công ty`

\


`}]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phones" type="array" %}
Danh sách đối tượng PHONES

\


Ví dụ :

\




`[{`

\


 

`data : "03256521XXX",`

 

\


 

`type : "home", //home, personal/ office`

\


 

`valueType : "Nhà" // Nhà, Cá nhân, Công ty`

\


`}]`
{% endswagger-parameter %}

{% swagger-response status="200" description="Dữ liệu thông tin khách hàng trả về, khi sửa thông tin thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": {
        "publicId": "7e879ce7ca3870dfbd9...",
        "fullName": "TRAN VAN TIEN",
        "displayName": "Tien",
        "gender": "male",
        "passport": "125441225",
        "address": "Ba le chan, Phuong Tan Dinh, Quan 1",
        "note": "Ghi chu o day",
        "emails": [
            {
                "data": "tientv_xx@yahoo.com.vn",
                "type": "home",
                "valueType": "Nhà"
            }
        ],
        "phones": [
            {
                "data": "0236552xxx",
                "type": "home",
                "valueType": "Nhà"
            }
        ],
        "contactType": "contact"
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="{URL}" path="/api/contacts/delete/:public_id" method="delete" summary="Xóa khách hàng" %}
{% swagger-description %}
Xóa khách hàng thông qua publicId
{% endswagger-description %}

{% swagger-parameter in="path" name="public_id" type="string" %}
Id khách hàng
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
AccessToken. Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200" description="Xóa khách hàng thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": true,
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}
