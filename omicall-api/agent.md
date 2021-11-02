---
description: Quản lý nhân viên
---

# Nhân viên

{% swagger baseUrl="[URL]" path="/api/agent/list" method="get" summary="Danh sách nhân viên" %}
{% swagger-description %}
Danh sách nhân viên của doanh nghiệp
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token, Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="number" %}
Page (mặc định là 1)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="number" %}
Size (kích thước trang) : mặc định là 50
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keyword" type="string" %}
Từ khóa tìm kiếm 

\


\- Họ và tên

\


\- Email

\


\- SĐT
{% endswagger-parameter %}

{% swagger-response status="200" description="Danh sách nhân viên" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.1.951",
    "payload": {
        "next_page": 2,
        "page_number": 1,
        "has_previous": false,
        "has_next": true,
        "total_pages": 3,
        "previous_page": 1,
        "items": [
            {
                "create_by": {
                    "name": "Omi Team"
                },
                "last_update_by": {
                    "name": "Omi Team"
                },
                "created_date": 1611889185166,
                "last_updated_date": 1611889185446,
                "public_id": null,
                "contact_type": "agent",
                "tags_view": [],
                "is_deleted": false,
                "tags": [],
                "is_active": true,
                "identify_info": "vietnam1@gmail.com",
                "attribute_structure": [
                    {
                        "identify": null,
                        "field_code": "full_name",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "Tran Van Tien",
                                "data_type": "single_text",
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "mail",
                        "field_type": "email",
                        "value": [
                            {
                                "display_value": "vietnam1@gmail.com",
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "gender",
                        "field_type": "radio",
                        "value": [
                            {
                                "display_value": "male",
                                "data_type": "male",
                                "value_type": "Nam"
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "phone_number",
                        "field_type": "phone",
                        "value": [
                            {
                                "display_value": null,
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    }
                ]
            },
            {
                "create_by": {
                    "name": "Omi Team"
                },
                "last_update_by": {
                    "name": "Omi Team"
                },
                "created_date": 1608024393791,
                "last_updated_date": 1608024393791,
                "public_id": null,
                "contact_type": "agent",
                "tags_view": [],
                "is_deleted": false,
                "tags": [],
                "is_active": false,
                "identify_info": "hanhttm@vihat.vn",
                "attribute_structure": [
                    {
                        "identify": null,
                        "field_code": "full_name",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "hanhttm",
                                "data_type": "single_text",
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "mail",
                        "field_type": "email",
                        "value": [
                            {
                                "display_value": "hanhttm@vihat.vn",
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "gender",
                        "field_type": "radio",
                        "value": [
                            {
                                "display_value": "male",
                                "data_type": "male",
                                "value_type": "Nam"
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "phone_number",
                        "field_type": "phone",
                        "value": [
                            {
                                "display_value": null,
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    }
                ]
            },
            {
                "create_by": {
                    "name": "Omi Team"
                },
                "last_update_by": {
                    "name": "Omi Team"
                },
                "created_date": 1607393421623,
                "last_updated_date": 1607393452508,
                "public_id": null,
                "contact_type": "agent",
                "tags_view": [],
                "is_deleted": false,
                "tags": [],
                "is_active": true,
                "identify_info": "minhnh@vihatgroup.com",
                "attribute_structure": [
                    {
                        "identify": null,
                        "field_code": "full_name",
                        "field_type": "single_text",
                        "value": [
                            {
                                "display_value": "minhnh",
                                "data_type": "single_text",
                                "value_type": null
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "mail",
                        "field_type": "email",
                        "value": [
                            {
                                "display_value": "minhnh@vihatgroup.com",
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "gender",
                        "field_type": "radio",
                        "value": [
                            {
                                "display_value": "male",
                                "data_type": "male",
                                "value_type": "Nam"
                            }
                        ]
                    },
                    {
                        "identify": null,
                        "field_code": "phone_number",
                        "field_type": "phone",
                        "value": [
                            {
                                "display_value": null,
                                "data_type": "personal",
                                "value_type": "Cá nhân"
                            }
                        ]
                    }
                ]
            }
        ],
        "total_items": 9,
        "page_size": 3
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/agent/invite" method="post" summary="Mời nhân viên" %}
{% swagger-description %}
Mời nhân viên sử dụng tổng đài
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token : Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="owner_email" type="string" %}
Email nhân viên phụ trách
{% endswagger-parameter %}

{% swagger-parameter in="body" name="role_name" type="string" %}
Quyền . Mặt định là Sale

\


\-  Sale

\


\-  Trưởng nhóm sale

\


\- Trưởng phòng Kinh Doanh

\


\- Kế toán

\


\- Giám đốc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Mật khẩu đăng nhập, khởi tạo ban đầu
{% endswagger-parameter %}

{% swagger-parameter in="body" name="identify_info" type="string" %}
Email định danh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="full_name" type="string" %}
Họ và tên nhân viên
{% endswagger-parameter %}

{% swagger-response status="200" description="Thông tin nhân viên " %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-1OB3SFM",
    "payload": {
        "agent": { // Thông tin nhân viên
            "full_name": "Tran Van Tien",
            "email": "vietnam12@gmail.com"
        },
        "pbx_account": { // Thông tin tổng đài
            "sip_user": "",
            "password": "",
            "domain": null,
            "outbound_proxy": null,
            "public_number": null,
            "full_name": "Tran Van Tien",
            "email": "vietnam12@gmail.com",
            "last_updated_date": 1597798326714,
            "created_date": 1597798326714
        }
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

| Mã lỗi                   | Mô tả                                                                                                                                          |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| full\_name\_is\_required | Họ và tên là bắt buộc                                                                                                                          |
| identify\_info\_invalid  | Email không hợp lệ                                                                                                                             |
| password\_invalid        | <p>Mật khẩu không hợp lệ , Mật khẩu bao gồm </p><ul><li>Ít nhất 8 ký tự</li><li>Ký tự in hoa, in thường</li><li>Số và ký tự đặc biệt</li></ul> |
| role\_is\_required       | Quyền là bắt buộc                                                                                                                              |
| agent\_exists            | Nhân viên đã tồn tại                                                                                                                           |
| limit\_agent             | Vượt quá giới hạn gói dịch vu                                                                                                                  |
| invite\_error            | Có lỗi xảy ra khi invite                                                                                                                       |

{% swagger baseUrl="[URL]" path="/api/agent/delete?identify_info=" method="delete" summary="Xóa nhân viên" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Access token Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="identify_info" type="string" %}
Email nhân viên
{% endswagger-parameter %}

{% swagger-response status="200" description="Xóa nhân viên thành công" %}
```
```
{% endswagger-response %}
{% endswagger %}
