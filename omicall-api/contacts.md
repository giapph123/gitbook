---
description: Quản lý khách hàng
---

# Khách hàng

{% api-method method="post" host="\[URL\]" path="/api/contacts/list" %}
{% api-method-summary %}
Tìm kiếm khách hàng
{% endapi-method-summary %}

{% api-method-description %}
Tìm kiếm khách hàng
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer Access: Bearer 'token'
{% endapi-method-parameter %}

{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="page" type="number" required=false %}
Trang. Bắt đầu từ 1. Mặc định là 1
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" required=false %}
Kích thước trang. Mặc định là 50
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="keyword" type="string" required=false %}
Từ khóa tìm kiếm. Có thể một trong các giá trị  
- Số điện thoại  
- Email  
- Họ và tên
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Dữ liệu trả về thành công
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/contacts/add" %}
{% api-method-summary %}
Tạo mới khách hàng
{% endapi-method-summary %}

{% api-method-description %}
Tạo mới khách hàng
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer Access: Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="tags" type="array" required=false %}
Danh sách thẻ tags  
Ví dụ : `"tags" : ["Khách lẻ", "Khách có nhu cầu"]`
{% endapi-method-parameter %}

{% api-method-parameter name="more\_infomation" type="array" required=false %}
Thông tin trường tùy chỉnh  
Ví dụ  
`[  
{value_type : "Cao",  display_value: "1.75m"},  
{value_type:"Nặng", display_value : "75kg"}  
{value_type:"Điểm", display_value: "90"}  
]`
{% endapi-method-parameter %}

{% api-method-parameter name="user\_owner\_email" type="string" required=false %}
Email nhân viên phụ trách 
{% endapi-method-parameter %}

{% api-method-parameter name="refId" type="string" required=false %}
Id của khách hàng bên đối tác
{% endapi-method-parameter %}

{% api-method-parameter name="refCode" type="string" required=false %}
Mã của khách hàng bên đối tác
{% endapi-method-parameter %}

{% api-method-parameter name="job\_title" type="string" required=false %}
Công việc / chức vụ của khách hàng
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
Ghi chú về khách hàng
{% endapi-method-parameter %}

{% api-method-parameter name="birthday" type="string" required=false %}
Ngày tháng năm sinh, định dạng : \(dd/MM/yyyy\)
{% endapi-method-parameter %}

{% api-method-parameter name="gender" type="string" required=false %}
Giới tính gồm \( '**other**' : Giới tính khác; '**male**' : Nam; '**female**' : Nữ\)
{% endapi-method-parameter %}

{% api-method-parameter name="fullName" type="string" required=true %}
Họ và tên
{% endapi-method-parameter %}

{% api-method-parameter name="passport" type="string" required=false %}
Hộ chiếu hoặc Id card
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=false %}
Địa chỉ
{% endapi-method-parameter %}

{% api-method-parameter name="emails" type="array" required=false %}
Danh sách đối tượng EMAIL  
Ví dụ :  
`[{  
 data: "tientv@demo.com.nv",   
 value: "home", // home, personal, office  
 valueType: "Nhà" // Nhà, Cá nhân, Công ty  
}]`
{% endapi-method-parameter %}

{% api-method-parameter name="phones" type="array" required=true %}
Danh sách đối tượng PHONE  
Ví dụ :  
`[{  
 data: "02525485xxx",  
 value : "home", // home, personal, office  
 valueType : "Nhà" // Nhà, Cá nhân, Công ty  
}]`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Dữ liệu trả về khi yêu cầu thành công
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL" path="/api/contacts/add-more" %}
{% api-method-summary %}
Tạo nhiều khách hàng
{% endapi-method-summary %}

{% api-method-description %}
Tạo danh nhiều khách hàng, Request Body là array Object đối tượng khách hàng lúc tạo mới.   
API xử lý bất đồng bộ
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token: Bearer 'token'
{% endapi-method-parameter %}

{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Tạo danh sách thành công
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "payload": true,
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/contacts/update" %}
{% api-method-summary %}
Sửa thông tin khách hàng
{% endapi-method-summary %}

{% api-method-description %}
Sửa thông tin khách hàng
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token : Bearer 'token'
{% endapi-method-parameter %}

{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="tags" type="array" required=false %}
Danh sách thẻ tags  
Ví dụ : `"tags":["Khách lẻ","Khách có nhu cầu"]`
{% endapi-method-parameter %}

{% api-method-parameter name="refId" type="string" required=true %}
Id khách hàng
{% endapi-method-parameter %}

{% api-method-parameter name="birthday" type="string" required=false %}
Ngày tháng năm sinh: định dạng \(dd/MM/yyyy\)
{% endapi-method-parameter %}

{% api-method-parameter name="more\_infomation" type="array" required=false %}
Thông tin trường tùy chỉnh  
`[  
{"value_type":"Điểm","display_value":"20"},  
{"value_type":"Đơn","display_value":"10"},  
{"value_type":"Tiền","display_value":"500000"}  
]`
{% endapi-method-parameter %}

{% api-method-parameter name="user\_owner\_email" type="string" required=false %}
Email người phụ trách
{% endapi-method-parameter %}

{% api-method-parameter name="fullName" type="string" required=true %}
Họ và tên
{% endapi-method-parameter %}

{% api-method-parameter name="gender" type="string" required=false %}
Giới tính \('**other**' : Giới tính khác; '**male**' : Nam; '**female**' : Nữ\)
{% endapi-method-parameter %}

{% api-method-parameter name="passport" type="string" required=false %}
Hộ chiếu hoặc id card
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=false %}
Địa chỉ
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
Ghi chú
{% endapi-method-parameter %}

{% api-method-parameter name="emails" type="array" required=false %}
Danh sách đối tượng EMAILS   
Ví dụ :   
`[{  
 data : "tientv@demo.com.vn",  
 type: "home", // home, personal, office  
 valueType: "Nhà" // Nhà, Cá nhân, Công ty  
}]`
{% endapi-method-parameter %}

{% api-method-parameter name="phones" type="array" required=true %}
Danh sách đối tượng PHONES  
Ví dụ :  
`[{  
 data : "03256521XXX",   
 type : "home", //home, personal/ office  
 valueType : "Nhà" // Nhà, Cá nhân, Công ty  
}]`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Dữ liệu thông tin khách hàng trả về, khi sửa thông tin thành công
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="{URL}" path="/api/contacts/delete/:public\_id" %}
{% api-method-summary %}
Xóa khách hàng
{% endapi-method-summary %}

{% api-method-description %}
Xóa khách hàng thông qua publicId
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="public\_id" type="string" required=true %}
Id khách hàng
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
AccessToken. Bearer 'token'
{% endapi-method-parameter %}

{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Xóa khách hàng thành công
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": true,
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

