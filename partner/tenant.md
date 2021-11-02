---
description: Quản lý doanh nghiệp thuộc đối tác hoặc đại lý
---

# Quản lý doanh nghiệp

{% swagger baseUrl="[URL]" path="/api/partner/tenant/add" method="post" summary="Tạo doanh nghiệp" %}
{% swagger-description %}
Tạo doanh nghiệp đối tác

\


Sau khi tạo doanh nghiệp xong, sẽ mất khoảng 

**3 - 10s**

 để kích hoạt xong doanh nghiệp và khởi tạo dữ liệu ban đầu
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Bearer Access Token : Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Email chủ doanh nghiệp
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Mật khẩu. Bao gồm 8 ký tự (In hoa, thường, số và ký tự đặc biệt)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fullName" type="string" %}
Tên doanh nghiệp (Nhỏ hơn 255 ký tự)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerName" type="string" %}
Tên chủ doanh nghiệp (Nhỏ hơn 255 ký tự)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" type="string" %}
Số điện thoại chủ doanh nghiệp
{% endswagger-parameter %}

{% swagger-parameter in="body" name="isAutoActive" type="boolean" %}
Tự động kích hoạt tài khoản hoặc không
{% endswagger-parameter %}

{% swagger-response status="200" description="Tạo doanh nghiệp thành công" %}
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
{% endswagger-response %}
{% endswagger %}

**Mã lỗi khi tạo doanh nghiệp**

| Mã lỗi                      | Mô tả                                                                                     |
| --------------------------- | ----------------------------------------------------------------------------------------- |
| partner\_invalid            | Access token không phải của đối tác                                                       |
| tenant\_invalid             | Access token không phải của đối tác                                                       |
| body\_request\_is\_required | Thiếu request body                                                                        |
| request\_invalid            | Các dữ liệu bắt buộc không được nhập hoặc nhập không hợp lệ                               |
| email\_invalid              | Email không hợp lệ                                                                        |
| password\_invalid           | <p>Mật khẩu không hợp lệ</p><p>Mật khẩu bao gồm (In hoa, thường, số , ký tự đặc biệt)</p> |
| email\_registered           | Email này đã được đăng ký với 1 chủ doanh nghiệp trước đó                                 |
| create\_tenant\_error       | Tạo doanh nghiệp bị lỗi                                                                   |



{% swagger baseUrl="[URL]" path="/api/partner/tenant/list" method="post" summary="Danh sách doanh nghiệp" %}
{% swagger-description %}
Danh sách doanh nghiệp thuộc đối tác
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token : Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="number" %}
Kích thước trang
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="integer" %}
Trang tìm kiếm, bắt đầu từ 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="keyword" type="string" %}
Từ khóa tìm kiếm

\


\- Tên doanh nghiệp

\


\- Email
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/partner/tenant/info?id=" method="get" summary="Chi tiết doanh nghiệp thuộc đối tác" %}
{% swagger-description %}
Thông tin chi tiết doanh nghiệp thuộc đối tác
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token : Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="id" type="string" %}
id của doanh nghiệp (

**tenant_id**

)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
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
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/partner/tenant/update_balance" method="post" summary="Nạp tiền" %}
{% swagger-description %}
Nạp tiền cho doanh nghiệp thông qua email
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token : Bearer 'partner token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Email chủ doanh nghiệp
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="number" %}
Số tiền (lớn hơn 10,000 VNĐ)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="string" %}
Nội dung  nạp tiền (lớn hơn 50 ký tự)
{% endswagger-parameter %}

{% swagger-response status="200" description="Nạp tiền thành công" %}
```
```
{% endswagger-response %}
{% endswagger %}

#### THÔNG BÁO LỖI KHI NẠP TIỀN

| Mã                                             | Mô tả                        |
| ---------------------------------------------- | ---------------------------- |
| access\_denied                                 | Nạp tiền bị từ chối          |
| amount\_gte\_10.000\_vnd                       | Số tiền tối thiểu 10,000 VNĐ |
| description\_is\_required                      | Mô tả là bắt buộc            |
| description\_is\_to\_short.gte\_50\_characters | Mô tả phải lớn 50 ký tự      |
