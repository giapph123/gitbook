# Tổng quan

```
URL : https://public-v1-stg.omicall.com
Version : 2.1.03
Last Updated : 25/04/2021
```

## API Key

Đăng ký tài khoản tại : [https://sso.omicall.com/](https://sso.omicrm.com/)

* Truy cập **Tài khoản &gt; Cấu hình &gt; Quản lý API**
* Tạo Api key cho doanh nghiệp

![](../.gitbook/assets/image%20%282%29.png)

Yêu cầu API hoặc thu hồi API

![](../.gitbook/assets/image%20%288%29.png)

**Thuật ngữ và loại dữ liệu dùng trong OMI**

| Thuật ngữ | Mô tả |
| :--- | :--- |
| **OMICALL\_API**     | Hệ thống cho phép đối tác thao tác với dữ liệu của mình trên OMI thông qua API |
| **ACCESS\_TOKEN** | Là token mà OMI cung cấp cho đối tác, để thao tác với OMICALL API. Token sẽ có thời gian timeout là **24** \(giờ\) |
| **API\_KEY** | Là khóa định danh API cho mỗi doanh nghiệp, dùng để kết nối với OMICALL. Dùng API Key để lấy Access Token |

**RESPONSE**

<table>
  <thead>
    <tr>
      <th style="text-align:left">STT</th>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left"><b>status_code</b>
      </td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">
        <p><b>9999 </b>: Thao t&#xE1;c th&#xE0;nh c&#xF4;ng</p>
        <p><b>-9999</b> : Thao t&#xE1;c th&#x1EA5;t b&#x1EA1;i</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left"><b>message</b>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">M&#xE3; l&#x1ED7;i ho&#x1EB7;c th&#xF4;ng b&#xE1;o l&#x1ED7;i</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left"><b>payload</b>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">D&#x1EEF; li&#x1EC7;u tr&#x1EA3; v&#x1EC1; sau x&#x1EED; l&#xFD;</td>
    </tr>
  </tbody>
</table>

**ERROR CODE**

| Code | Description |
| :--- | :--- |
| _api\_key\_is\_required_ | API Key là bắt buộc |
| _api\_key\_invalid_ | API Key không hợp lệ |
| _request\_body\_required_ | Thiếu request body trong dữ liệu truyền lên api |



