# Khởi tạo SDK

## Omi SDK usages

### Thông tin tài khoản cần cung cấp cho SDK <a href="#user-content-account-informations-for-initialize-sdk" id="user-content-account-informations-for-initialize-sdk"></a>

Mỗi tài khoản thực hiện cuộc gọi trong OMI là tài khoản tổng đài của nhân viên, tài khoản này dùng để đăng nhập vào hệ thống tổng đài gồm các thông tin

* User name : Tên đăng nhập
* Password : Mật khẩu
* Realm : Domain của doanh nghiệp , domain này khi đăng ký và đăng nhập trên Web sẽ hiện thị đường dẫn có domain như sau:&#x20;

![](<../../../.gitbook/assets/image (3).png>)

* customUI: Dùng để tuỳ chỉnh màn hình thoại đến và đi



Khởi tạo Omi SDK bằng cách thêm đoạn mã sau vào trong MainActivity của Project

```java
OmiClient(requireContext()).register(
    userName,
    password,
    realm,
    customUI = true
)
OmiSDKUtils.startOmiService(requireActivity())
```

### Xử lý kết quả trả về khi xin các quyền cần thiết  <a href="#user-content-handle-permissions-result" id="user-content-handle-permissions-result"></a>

Use OmiSDKUtils to handle permissions results

```java
override fun onRequestPermissionsResult(
        requestCode: Int,
        permissions: Array<out String>,
        grantResults: IntArray
) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults)
    OmiSDKUtils.handlePermissionRequest(requestCode, permissions, grantResults, requireActivity())
}
```

### &#x20;<a href="#user-content-listeners" id="user-content-listeners"></a>
