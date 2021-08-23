---
description: Quản lý doanh nghiệp thuộc đối tác hoặc đại lý
---

# Quản lý doanh nghiệp

{% api-method method="post" host="\[URL\]" path="/api/partner/tenant/add" %}
{% api-method-summary %}
Tạo doanh nghiệp
{% endapi-method-summary %}

{% api-method-description %}
Tạo doanh nghiệp đối tác  
Sau khi tạo doanh nghiệp xong, sẽ mất khoảng **3 - 10s** để kích hoạt xong doanh nghiệp và khởi tạo dữ liệu ban đầu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer Access Token : Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email chủ doanh nghiệp
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Mật khẩu. Bao gồm 8 ký tự \(In hoa, thường, số và ký tự đặc biệt\)
{% endapi-method-parameter %}

{% api-method-parameter name="fullName" type="string" required=true %}
Tên doanh nghiệp \(Nhỏ hơn 255 ký tự\)
{% endapi-method-parameter %}

{% api-method-parameter name="ownerName" type="string" required=true %}
Tên chủ doanh nghiệp \(Nhỏ hơn 255 ký tự\)
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=true %}
Số điện thoại chủ doanh nghiệp
{% endapi-method-parameter %}

{% api-method-parameter name="isAutoActive" type="boolean" required=false %}
Tự động kích hoạt tài khoản hoặc không
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Tạo doanh nghiệp thành công
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-1OB3SFM",
    "payload": {
        "id": "5f59784273227343222243" // ID doanh nghiệp
    },
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**Mã lỗi khi tạo doanh nghiệp**

<table>
  <thead>
    <tr>
      <th style="text-align:left">M&#xE3; l&#x1ED7;i</th>
      <th style="text-align:left">M&#xF4; t&#x1EA3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">partner_invalid</td>
      <td style="text-align:left">Access token kh&#xF4;ng ph&#x1EA3;i c&#x1EE7;a &#x111;&#x1ED1;i t&#xE1;c</td>
    </tr>
    <tr>
      <td style="text-align:left">tenant_invalid</td>
      <td style="text-align:left">Access token kh&#xF4;ng ph&#x1EA3;i c&#x1EE7;a &#x111;&#x1ED1;i t&#xE1;c</td>
    </tr>
    <tr>
      <td style="text-align:left">body_request_is_required</td>
      <td style="text-align:left">Thi&#x1EBF;u request body</td>
    </tr>
    <tr>
      <td style="text-align:left">request_invalid</td>
      <td style="text-align:left">C&#xE1;c d&#x1EEF; li&#x1EC7;u b&#x1EAF;t bu&#x1ED9;c kh&#xF4;ng &#x111;&#x1B0;&#x1EE3;c
        nh&#x1EAD;p ho&#x1EB7;c nh&#x1EAD;p kh&#xF4;ng h&#x1EE3;p l&#x1EC7;</td>
    </tr>
    <tr>
      <td style="text-align:left">email_invalid</td>
      <td style="text-align:left">Email kh&#xF4;ng h&#x1EE3;p l&#x1EC7;</td>
    </tr>
    <tr>
      <td style="text-align:left">password_invalid</td>
      <td style="text-align:left">
        <p>M&#x1EAD;t kh&#x1EA9;u kh&#xF4;ng h&#x1EE3;p l&#x1EC7;</p>
        <p>M&#x1EAD;t kh&#x1EA9;u bao g&#x1ED3;m (In hoa, th&#x1B0;&#x1EDD;ng, s&#x1ED1;
          , k&#xFD; t&#x1EF1; &#x111;&#x1EB7;c bi&#x1EC7;t)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">email_registered</td>
      <td style="text-align:left">Email n&#xE0;y &#x111;&#xE3; &#x111;&#x1B0;&#x1EE3;c &#x111;&#x103;ng
        k&#xFD; v&#x1EDB;i 1 ch&#x1EE7; doanh nghi&#x1EC7;p tr&#x1B0;&#x1EDB;c
        &#x111;&#xF3;</td>
    </tr>
    <tr>
      <td style="text-align:left">create_tenant_error</td>
      <td style="text-align:left">T&#x1EA1;o doanh nghi&#x1EC7;p b&#x1ECB; l&#x1ED7;i</td>
    </tr>
  </tbody>
</table>



{% api-method method="post" host="\[URL\]" path="/api/partner/tenant/list" %}
{% api-method-summary %}
Danh sách doanh nghiệp
{% endapi-method-summary %}

{% api-method-description %}
Danh sách doanh nghiệp thuộc đối tác
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token : Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="size" type="number" required=true %}
Kích thước trang
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=true %}
Trang tìm kiếm, bắt đầu từ 1
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="keyword" type="string" required=false %}
Từ khóa tìm kiếm  
- Tên doanh nghiệp  
- Email
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="\[URL\]" path="/api/partner/tenant/info?id=" %}
{% api-method-summary %}
Chi tiết doanh nghiệp thuộc đối tác
{% endapi-method-summary %}

{% api-method-description %}
Thông tin chi tiết doanh nghiệp thuộc đối tác
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token : Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
id của doanh nghiệp \(**tenant\_id**\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-1OB3SFM",
    "payload": {
        "full_name": "Omi Team",
        "email": "support@omicrm.com",
        "description": "Nâng cao trải nghiệm khách hàng, lấy sự hài lòng của khách hàng làm tiêu chí phấn đấu của doanh nghiệp",
        "enabled": true, //Đang hoạt động hoặc ngưng hoạt động
        "domain": "omiteam", // Tên miền truy cập OMI
        "domain_fusion": "omiteam", // Tên miền tổng đài
        "domain_expire": 1584606068154, // Ngày hết hạn domain
        "effective_date": 1583396482840, // Ngày kích hoạt
        "expire_date": 1614936981790, // Ngày hết hạn
        "phone": "0844441900", // SĐT chủ doanh nghiệp
        "status": "activated", // Trạng thái: Đã kích hoạt / Chưa kích hoạt
        "paid_type": "prepaid", // Hình thức thanh toán : prepaid : Trả trước, postpaid : Trả sau
        "nation": "vn", // Quốc gia
        "currency": "VND", // Tiền tệ
        "language": "vi", // Ngôn ngữ
        "balance": 3007855, // Số dư tài khoản
        "api_key": "K343KDK9-2I34K3K-3I33K3-2222" // Api key của doanh nghiệp
        "public_numbers": [
            {
                "number": "842877788056", // Số hotline
                "provider": "itel", // Nhà mạng
                "expire_date": 1602731734809, //Ngày hết hạn số
                "status": "active" // Tình trạng số
            }
        ],
        "service_package": {
            "code_name": "trial", // Mã gói
            "service_name": "Trial", // Tên gói
            "staff_num": 5, // Số lượng nhân viên
            "customer_num": 100, // Số lượng khách hàng
            "expiry_date": 1606300035002, // Ngày gói hết hạn
            "cashback" : 2092202 // Số tiền hoàn lại nếu khách hàng lên gói cao hơn
        }
    },
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/partner/tenant/update\_balance" %}
{% api-method-summary %}
Nạp tiền
{% endapi-method-summary %}

{% api-method-description %}
Nạp tiền cho doanh nghiệp thông qua email
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token : Bearer 'partner token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email chủ doanh nghiệp
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=true %}
Số tiền \(lớn hơn 10,000 VNĐ\)
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Nội dung  nạp tiền \(lớn hơn 50 ký tự\)
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Nạp tiền thành công
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### THÔNG BÁO LỖI KHI NẠP TIỀN

| Mã | Mô tả |
| :--- | :--- |
| access\_denied | Nạp tiền bị từ chối |
| amount\_gte\_10.000\_vnd | Số tiền tối thiểu 10,000 VNĐ |
| description\_is\_required | Mô tả là bắt buộc |
| description\_is\_to\_short.gte\_50\_characters | Mô tả phải lớn 50 ký tự  |

