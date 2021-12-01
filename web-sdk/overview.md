---
description: >-
  OmiCall Web SDK : là công cụ bao gồm thư viện và tài liệu mà OmiCall cung cấp
  cho đối tác, để đối tác xây dựng tính năng call ngay chính trên ứng dụng web
  của mình.
---

# Web SDK

```markup
Version : 2.0.0
Release date : 15/07/2021 22:00
Changelog : https://api.omicall.com/chang-log#26-05-2021
```

### Hướng dẫn cài đặt

![Giao diện Dialog Call](../.gitbook/assets/sdk1.png)



Nhúng Web SDK vào HTML của website cần tích hợp

```markup
<body>

    <!-- other html -->
    
    <script omi-sdk type="text/javascript" src="https://cdn.omicrm.com/sdk/2.0.0/sdk.min.js"></script>
    
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Ví dụ về một số config có thể dùng khi init SDK
            let config = {
                theme: 'default',
                // debug: false,
                // busy: false,
                language: 'vi',
                ringtoneVolume: 1,
                options: {
                    hideCallButton: false,
                    showContactLoading: false,
                },
                // classes: {
                //     btnToggle: 'custom-btn-toggle-call btn-call-left',
                //     dialog: 'custom-dialog-call dialog-call-left',
                // },
                // styles: {
                //     btnToggle: {
                //         'background-color': 'red',
                //         justifyContent: 'center',
            	//         color: 'red',
                //     },
                //     dialog: {
                //        'background-color': 'gray',
                //        justifyContent: 'center',
                //        color: 'pink',
                //    },
                //},
                callbacks: {
                    register: (data) => {
                        // Sự kiện xảy ra khi trạng thái kết nối tổng đài thay đổi
                        console.log('register:', data);
                    },
                    connecting: (data) => {
                        // Sự kiện xảy ra khi bắt đầu thực hiện cuộc gọi ra
                        console.log('connecting:', data);
                    },
                    invite: (data) => {
                         // Sự kiện xảy ra khi có cuộc gọi tới
                         console.log('invite:', data);
                    },
                    inviteRejected: (data) => {
                         // Sự kiện xảy ra khi có cuộc gọi tới, nhưng bị tự động từ chối
                         // trong khi đang diễn ra một cuộc gọi khác
                         console.log('inviteRejected:', data);
                    },
                    ringing: (data) => {
                        // Sự kiện xảy ra khi cuộc gọi ra bắt đầu đổ chuông
                        console.log('ringing:', data);
                    },
                    accepted: (data) => {
                         // Sự kiện xảy ra khi cuộc gọi vừa được chấp nhận
                         console.log('accepted:', data);
                    },
                    incall: (data) => {
                         // Sự kiện xảy ra mỗi 1 giây sau khi cuộc gọi đã được chấp nhận
                         console.log('incall:', data);
                    },
                    acceptedByOther: (data) => {
                         // Sự kiện dùng để kiểm tra xem cuộc gọi bị kết thúc
                         // đã được chấp nhận ở thiết bị khác hay không
                         console.log('acceptedByOther:', data);
                    },
                    ended: (data) => {
                         // Sự kiện xảy ra khi cuộc gọi kết thúc
                         console.log('ended:', data);
                    },
                    holdChanged: (status) => {
                         // Sự kiện xảy ra khi trạng thái giữ cuộc gọi thay đổi
                         console.log('on hold:', status);
                    },
                }
            };
            omiSDK.init(config, () => {
                omiSDK.register({
                    domain: '',
                    username: '',
                    password: ''
                });
            });
        });
    </script>

</body>
```

{% file src="../.gitbook/assets/index (8).html" %}
Ví dụ tích hợp
{% endfile %}

**Cấu hình và Sự kiện**

|                    Tham số | Kiểu         | Mô tả                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| -------------------------: | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|           config.**theme** | **String**   | <p>Giao diện dialog cuộc gọi (nếu để trống thì sẽ không có giao diện). Hoặc một trong các giá trị sau </p><ul><li><strong>default</strong> : Giao diện (như ảnh ở trên)</li></ul>                                                                                                                                                                                                                                                                                                                                             |
|           config.**debug** | **Boolean**  | <p>Bật tắt chức năng log các sự kiện của SDK.</p><p>Mặc định: <strong>false</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|            config.**busy** | **Boolean**  | Trạng thái cho phép thực hiện cuộc gọi ra, nhưng sẽ tự động từ chối tất cả các cuộc gọi tới                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|        config.**language** | **String**   | <p>Ngôn ngữ hiển thị dialog cuộc gọi mặc định của SDK.</p><p>Gồm: <br> "<strong>vi</strong>" : Tiếng Việt (<strong>default</strong>)<br> "<strong>en</strong>" : Tiếng anh</p>                                                                                                                                                                                                                                                                                                                                                |
|  config.**ringtoneVolume** | **Number**   | Âm lượng chuông, khi khách gọi tới (từ 0 - 1)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|         config.**options** | **Object**   | <ul><li><em><strong><code>hideCallButton</code></strong></em><code>: </code><strong><code>Boolean</code></strong> Ẩn hiện nút gọi</li></ul><ul><li><strong><code>showContactLoading</code></strong><code>:</code><strong><code>Boolean</code></strong> Ẩn hiện loading vị trí tên của người gọi trong dialog cuộc gọi</li></ul>                                                                                                                                                                                               |
|         config.**classes** | **Object**   | <ul><li><strong><code>btnToggle</code></strong><code>:</code><strong><code>String</code></strong> được truyền vào thuộc tính <strong><code>class</code></strong> của div ngoài cùng của button đóng mở UI cuộc gọi</li><li><strong><code>dialog</code></strong><code>:</code><strong><code>String</code></strong> được truyền vào thuộc tính <strong><code>class</code></strong> của div ngoài cùng của dialog UI cuộc gọi</li></ul>                                                                                          |
|          config.**styles** | **Object**   | <p></p><ul><li><strong><code>btnToggle</code></strong><code>:</code><strong><code>Object</code></strong> được truyền vào thuộc tính <strong><code>style</code></strong> của div ngoài cùng của button đóng mở UI cuộc gọi</li><li><strong><code>dialog</code></strong><code>:</code><strong><code>Object</code></strong> được truyền vào thuộc tính <strong><code>style</code></strong> của div ngoài cùng của dialog UI cuộc gọi</li></ul><p><strong>*Lưu ý</strong>: ví dụ cách dùng ở hướng dẫn nhúng script phía trên</p> |
|        config.**register** | **Function** | Sự kiện xảy ra khi trạng thái kết nối tổng đài thay đổi                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|      config.**connecting** | **Function** | Sự kiện xảy ra khi bắt đầu thực hiện cuộc gọi ra                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|          config.**invite** | **Function** | Sự kiện xảy ra khi có cuộc gọi tới                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|  config.**inviteRejected** | **Function** | Sự kiện xảy ra khi có cuộc gọi tới, nhưng bị tự động từ chối                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|         config.**ringing** | **Function** | Sự kiện xảy ra khi cuộc gọi ra bắt đầu đổ chuông                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        config.**accepted** | **Function** | Sự kiện xảy ra khi cuộc gọi vừa được chấp nhận                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|          config.**incall** | **Function** | Sự kiện xảy ra mỗi 1 giây sau khi cuộc gọi đã được chấp nhận                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| config.**acceptedByOther** | **Function** | Sự kiện dùng để kiểm tra xem cuộc gọi bị kết thúc, đã được chấp nhận ở thiết bị khác hay không                                                                                                                                                                                                                                                                                                                                                                                                                                |
|           config.**ended** | **Function** | Sự kiện xảy ra khi cuộc gọi kết thúc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|     config.**holdChanged** | **Function** | Sự kiện xảy ra khi trạng thái giữ cuộc gọi thay đổi                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |



**Dữ liệu callback từ sự kiện**

| Tham số                         | Loại       | Mô tả                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **direction**                   | **String** | Hướng của cuộc gọi: **`outbound, inbound`**                                                                                                                                                                                                                                                                                                                                                                                                 |
| **directionTxt**                | **String** | Tên hướng của cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **status**                      | **String** | Trạng thái hiện tại của cuộc gọi: **`connecting, ringing, connected, ended, hold`**                                                                                                                                                                                                                                                                                                                                                         |
| **statusTxt**                   | **String** | Tên trạng thái hiện tại của cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                        |
| **remoteNumber** hoặc **phone** | **String** | <ul><li>với <strong>direction outbound</strong>: số được gọi ra</li><li>với <strong>direction inbound</strong>: số đang gọi tới</li></ul>                                                                                                                                                                                                                                                                                                   |
| **sipNumber**                   | **String** | Số tổng đài đang dùng để thực hiện cuộc gọi ra hay nhận cuộc gọi tới                                                                                                                                                                                                                                                                                                                                                                        |
| **startTime**                   | **Date**   | Thời gian bắt đầu cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **answerTime**                  | **Date**   | Thời gian bắt đầu chấp nhận cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                        |
| **endTime**                     | **Date**   | Thời gian kết thúc cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **endCause**                    | **String** | <p>Nguyễn nhân kết thúc cuộc gọi.</p><p>Gồm:</p><ul><li><strong>BUSY</strong>: máy bận</li><li><strong>NO_ANSWER</strong>: hết thời gian đổ chuông</li><li><strong>TRIAL_REJECTION</strong>: khi gọi tới số điện thoại chưa gọi vào số tổng tài (với tài khoản OMI Trial)</li><li><strong>LIMITATION_DECLINE</strong>: quá thời lượng cho phép gọi ra</li><li><strong>ALLOTTED_TIMEOUT</strong>: Cuộc gọi đạt giới hạn thời lượng</li></ul> |
| **uuid**                        | **String** | **Transaction ID** của cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                             |
| **duration**                    | **Number** | Thời gian gọi giữa 2 người sau khi chấp nhận cuộc gọi cho tới khi cuộc gọi kết thúc                                                                                                                                                                                                                                                                                                                                                         |
| **durationTxt**                 | **String** | Thời gian gọi giữa 2 người sau khi chấp nhận cuộc gọi cho tới khi cuộc gọi kết thúc và đã được định dạng theo thời gian: **`00:00`**                                                                                                                                                                                                                                                                                                        |
| **totalDuration**               | **Number** | Tổng thời gian từ khi bắt đầu thực hiện/nhận cuộc gọi tới khi kết thúc                                                                                                                                                                                                                                                                                                                                                                      |
| **ping**                        | **Object** | Dữ liệu về trạng thái tín hiệu của cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                 |



**Phương thức**

|                          Phương thức | Mô tả                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| -----------------------------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|    omiSDK**.init(config, callback)** | Khởi tạo các cấu hình cần thiết cho SDK và load UI nếu có truyền theme                                                                                                                                                                                                                                                                                                                                                                                                               |
|          omiSDK.**register(params)** | <ul><li>Gọi tới khi sau khi function SDK init callback.</li><li>Phương thức ghi danh tổng đài: <strong>Object</strong></li></ul><p><code>{</code><br>   <code>domain : "abc" // domain tổng dài</code></p><p>   <code>username: "100", // Số nội bộ</code></p><p>   <code>password: "***" // Mật khẩu số nội bộ</code></p><p><code>}</code></p><p></p><p><strong>*Lưu ý:</strong> Có thể lấy các thông tin ghi danh tổng đài ở cấu hình số nội bộ hoặc thông qua API của OMICall</p> |
|              omiSDK.**unregister()** | Ngưng kết nối với tổng đài                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|        omiSDK.**reregister(params)** | Ngưng kết nối với tổng đài và tạo một phiên kết nối mới với params trước đó hoặc từ params mới truyền                                                                                                                                                                                                                                                                                                                                                                                |
|          omiSDK.**makeCall(phone)**  | <p><strong>- phone</strong>:</p><ul><li>Số điện thoại khách hàng</li><li>Số nội bộ của nhân viên</li><li>Số nội bộ của nhóm</li><li>Số nội bộ của nhóm bên ngoài</li></ul>                                                                                                                                                                                                                                                                                                           |
|  omiSDK.**makeCall(phone, hotline)** | <p><strong>- phone</strong>:</p><ul><li>Số điện thoại khách hàng</li><li>Số nội bộ của nhân viên</li><li>Số nội bộ của nhóm</li><li>Số nội bộ của nhóm bên ngoài</li></ul><p>- <strong>hotline:</strong> đầu số tổng đài dùng để gọi ra (*<strong>Lưu ý</strong>: phải là đầu số cho phép gọi ra và tài khoản nhân viên thực hiện cuộc gọi được quyền sử dụng đầu số này)</p>                                                                                                        |
|                omiSDK.**stopCall**() | Kết thúc cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|              omiSDK.**rejectCall()** | Từ chối cuộc gọi (trong trường hợp không muốn nhận)                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|              omiSDK.**acceptCall**() | Chấp nhận cuộc gọi                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|   omiSDK.**transferCall(extension)** | <p>Chuyển tiếp cuộc gọi. </p><p><strong>extension</strong> : Là số máy lẻ nhân viên cần chuyển tới</p>                                                                                                                                                                                                                                                                                                                                                                               |
|            omiSDK.**sendDTMF(tone)** | <p>Gửi tín hiệu tương tác bấm phím</p><p><strong>tone</strong>: các số từ 0-9 hoặc *#</p>                                                                                                                                                                                                                                                                                                                                                                                            |
|        omiSDK.**toggleMute(status)** | <p>Bật tắt âm thanh từ micro của bạn</p><p><strong>status:</strong></p><ul><li><strong>true</strong>: tắt âm thanh</li><li><strong>false</strong>: bật âm thanh</li></ul>                                                                                                                                                                                                                                                                                                            |
|        omiSDK.**toggleHold(status)** | <p>Thay đổi trạng thái giữ cuộc gọi</p><p><strong>status:</strong></p><ul><li><strong>true</strong>: giữ cuộc gọi</li><li><strong>false</strong>: bỏ giữ cuộc gọi</li></ul>                                                                                                                                                                                                                                                                                                          |
|               omiSDK.**getStatus()** | <p>Lấy trạng thái kết nối hiện tại của SDK với tổng đài:</p><ul><li><strong>registering</strong>: đang kết nối</li><li><strong>registered</strong>: đã kết nối</li><li><strong>unregistered</strong>: chưa kết nối</li></ul>                                                                                                                                                                                                                                                         |
|            omiSDK.**toggleDialog()** | Chủ động ẩn hiện dialog cuộc gọi của SDK nếu có sử dụng theme                                                                                                                                                                                                                                                                                                                                                                                                                        |
| omiSDK.**updateContactInfo**(Object) | <p>Cập nhật Tên và Avatar của khách hàng trên cửa số cuộc gọi</p><p><em></em></p><p><em>omiSDK.<strong>updateContactInfo</strong>({</em></p><p>   <em>name : "Nguyễn Thanh Sang",</em></p><p>   <em>avatar : "https://...."</em></p><p><em>});</em></p><p><em></em></p><p><em>*G</em>iá trị <strong>avatar</strong> sẽ được truyền vào thuộc tính <code>src</code> của thẻ <code>img</code>: có thẻ là http link hoặc base64,...</p>                                                 |

