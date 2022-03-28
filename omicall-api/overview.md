# Tổng quan

```
URL : https://public-v1-stg.omicall.com
Version : 2.1.03
Last Updated : 25/04/2021
```

## API Key

Đăng ký tài khoản tại : [https://sso.omicall.com/](https://sso.omicrm.com)

* Truy cập **Tài khoản > Cấu hình > Quản lý API**
* Tạo Api key cho doanh nghiệp

![](<../.gitbook/assets/image (2).png>)

Yêu cầu API hoặc thu hồi API

![](<../.gitbook/assets/image (8).png>)

**Thuật ngữ và loại dữ liệu dùng trong OMI**

| Thuật ngữ            | Mô tả                                                                                                            |
| -------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **OMICALL\_API**     | Hệ thống cho phép đối tác thao tác với dữ liệu của mình trên OMI thông qua API                                   |
| **ACCESS\_TOKEN**    | Là token mà OMI cung cấp cho đối tác, để thao tác với OMICALL API. Token sẽ có thời gian timeout là **24** (giờ) |
| **API\_KEY**         | Là khóa định danh API cho mỗi doanh nghiệp, dùng để kết nối với OMICALL. Dùng API Key để lấy Access Token        |

**RESPONSE**

| STT | Code             | Type    | Description                                                                                         |
| --- | ---------------- | ------- | --------------------------------------------------------------------------------------------------- |
| 1   | **status\_code** | Integer | <p><strong>9999</strong> : Thao tác thành công</p><p><strong>-9999</strong> : Thao tác thất bại</p> |
| 2   | **message**      | String  | Mã lỗi hoặc thông báo lỗi                                                                           |
| 3   | **payload**      | Object  | Dữ liệu trả về sau xử lý                                                                            |

**ERROR CODE**

| Code                      | Description                                     |
| ------------------------- | ----------------------------------------------- |
| _api\_key\_is\_required_  | API Key là bắt buộc                             |
| _api\_key\_invalid_       | API Key không hợp lệ                            |
| _request\_body\_required_ | Thiếu request body trong dữ liệu truyền lên api |

