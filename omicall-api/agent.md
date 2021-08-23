---
description: Quản lý nhân viên
---

# Nhân viên

{% api-method method="get" host="\[URL\]" path="/api/agent/list" %}
{% api-method-summary %}
Danh sách nhân viên
{% endapi-method-summary %}

{% api-method-description %}
Danh sách nhân viên của doanh nghiệp
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token, Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="page" type="number" required=true %}
Page \(mặc định là 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" required=true %}
Size \(kích thước trang\) : mặc định là 50
{% endapi-method-parameter %}

{% api-method-parameter name="keyword" type="string" required=false %}
Từ khóa tìm kiếm   
- Họ và tên  
- Email  
- SĐT
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Danh sách nhân viên
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/agent/invite" %}
{% api-method-summary %}
Mời nhân viên
{% endapi-method-summary %}

{% api-method-description %}
Mời nhân viên sử dụng tổng đài
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token : Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="owner\_email" type="string" required=false %}
Email nhân viên phụ trách
{% endapi-method-parameter %}

{% api-method-parameter name="role\_name" type="string" required=false %}
Quyền . Mặt định là Sale  
-  Sale  
-  Trưởng nhóm sale  
- Trưởng phòng Kinh Doanh  
- Kế toán  
- Giám đốc
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Mật khẩu đăng nhập, khởi tạo ban đầu
{% endapi-method-parameter %}

{% api-method-parameter name="identify\_info" type="string" required=true %}
Email định danh
{% endapi-method-parameter %}

{% api-method-parameter name="full\_name" type="string" required=true %}
Họ và tên nhân viên
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Thông tin nhân viên 
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">M&#xE3; l&#x1ED7;i</th>
      <th style="text-align:left">M&#xF4; t&#x1EA3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">full_name_is_required</td>
      <td style="text-align:left">H&#x1ECD; v&#xE0; t&#xEA;n l&#xE0; b&#x1EAF;t bu&#x1ED9;c</td>
    </tr>
    <tr>
      <td style="text-align:left">identify_info_invalid</td>
      <td style="text-align:left">Email kh&#xF4;ng h&#x1EE3;p l&#x1EC7;</td>
    </tr>
    <tr>
      <td style="text-align:left">password_invalid</td>
      <td style="text-align:left">
        <p>M&#x1EAD;t kh&#x1EA9;u kh&#xF4;ng h&#x1EE3;p l&#x1EC7; , M&#x1EAD;t kh&#x1EA9;u
          bao g&#x1ED3;m</p>
        <ul>
          <li>&#xCD;t nh&#x1EA5;t 8 k&#xFD; t&#x1EF1;</li>
          <li>K&#xFD; t&#x1EF1; in hoa, in th&#x1B0;&#x1EDD;ng</li>
          <li>S&#x1ED1; v&#xE0; k&#xFD; t&#x1EF1; &#x111;&#x1EB7;c bi&#x1EC7;t</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">role_is_required</td>
      <td style="text-align:left">Quy&#x1EC1;n l&#xE0; b&#x1EAF;t bu&#x1ED9;c</td>
    </tr>
    <tr>
      <td style="text-align:left">agent_exists</td>
      <td style="text-align:left">Nh&#xE2;n vi&#xEA;n &#x111;&#xE3; t&#x1ED3;n t&#x1EA1;i</td>
    </tr>
    <tr>
      <td style="text-align:left">limit_agent</td>
      <td style="text-align:left">V&#x1B0;&#x1EE3;t qu&#xE1; gi&#x1EDB;i h&#x1EA1;n g&#xF3;i d&#x1ECB;ch
        vu</td>
    </tr>
    <tr>
      <td style="text-align:left">invite_error</td>
      <td style="text-align:left">C&#xF3; l&#x1ED7;i x&#x1EA3;y ra khi invite</td>
    </tr>
  </tbody>
</table>

{% api-method method="delete" host="\[URL\]" path="/api/agent/delete?identify\_info=" %}
{% api-method-summary %}
Xóa nhân viên
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="identify\_info" type="string" required=true %}
Email nhân viên
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Xóa nhân viên thành công
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

