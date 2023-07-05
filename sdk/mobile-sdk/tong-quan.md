# Tổng Quan

## SDK OMICALL <a href="#plivo-android-sdk" id="plivo-android-sdk"></a>

OMICALL  SDK cho phép bạn tạo các ứng dụng có khả năng thực hiện và nhận cuộc gọi trong ứng dụng Android/IOS của bạn. SDK này hỗ trợ cả mạng IPv4 và IPv6, có nghĩa là bạn có thể thực hiện và nhận cuộc gọi khi thiết bị của bạn được kết nối với mạng sử dụng một trong hai hoặc cả hai phiên bản của giao thức. **SDK hỗ trợ Android phiên bản 6 trở lên và Android API cấp 21 trở lên với IOS thì hỗ trợ IOS 11 trở lên** .

Phiên bản hiện tại của  SDK được xây dựng dựa trên giao thức SIP 2.0, với lỗi là WebRTC các bộ mã được hỗ trợ đầy đủ giúp tối ưu hoá chất lượng cuộc gọi như : OPUS/G.711/G711a/G729/GSM

### Điều kiện bắt buộc <a href="#prerequisites" id="prerequisites"></a>

Trước khi bạn bắt đầu viết mã ứng dụng của mình:

1. [Đăng ký tài khoản OMICALL](https://sso.omicrm.io/). Bạn cần có tài khoản OMICALL để tạo kết nối từ SDK này vào hệ thống OMICALL để thực hiện cuộc gọi
2. Cấu hình tài khoản để tạo các người dùng có thể thực hiện cuộc gọi trên hệ thống OMICALL. Đầu tiên chúng ta cần tạo các tài khoản nhân viên tại [đây](https://docs.omicrm.io/nhan-vien/gioi-thieu) , mỗi tài khoản nhân viên này được cấp phát 1 số nội bộ, cùng với đó là user và mật khẩu để đăng nhập vào SDK OMICALL được tạo và chỉnh sửa ở [đây](https://docs.omicrm.io/cau-hinh-tong-dai/so-noi-bo)&#x20;
3. Cấu hình thông tin để tích hợp phần Notification vào ứng dụng&#x20;

<figure><img src="../../.gitbook/assets/image (2) (2) (1).png" alt=""><figcaption></figcaption></figure>

