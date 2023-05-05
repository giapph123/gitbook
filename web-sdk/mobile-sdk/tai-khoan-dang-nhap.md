# Tài khoản đăng nhập

Lưu ý chỉ đăng nhập được bằng tài khoản nhân viên, hoăc đăng nhập bằng Apikey vào SDK để thực hiện cuộc gọi

## Cách 1: đăng nhập bằng tài khoản nhân viên:

Mỗi nhân viên có một số nội bộ để thực hiện cuộc gọi , số này được cấu hình trong tổng đài, khi đăng nhập vào web/mobile app hệ thống sẽ tự lấy số nội bộ này đăng nhập cho bạn.

Đối với SDK chúng ta cần 3 trường thông tin để đăng nhập vào thực hiện cuộc gọi&#x20;

* user: số nội bộ&#x20;
* password: mật khẩu
* realm: domain tổng đài&#x20;

Các thông tin này tìm chúng ta có thể truy cập trong phần : Cấu hình -> Tổng Đài -> Số nội bộ -> Nhấn vào chi tiết 1 số nội bộ&#x20;

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## Cách 2: đăng nhập bằng Api key:

Mỗi tài khoản sẽ được cấp một API key để truy cập dịch vụ&#x20;

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

**Login SDK bằng lệnh:**

```
[OmiClient initWithUUID:<#(NSString * _Nonnull)#> fullName:<#(NSString * _Nullable)#> apiKey:<#(NSString * _Nonnull)#>]
```

Trong đó:

* uuid: là id định dạng của user ( có thể lấy username khách hàng của đối tác tích hợp SDK để làm uuid )
* fullName: Tên của khách hàng dùng để hiển thị khi có cuộc gọi đến&#x20;
* apiKey: key dùng để xác minh khách hàng
