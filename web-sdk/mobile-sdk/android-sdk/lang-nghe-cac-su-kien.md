# Lắng nghe các sự kiện



### Thực hiện cuộc gọi

&#x20;Để thực hiện một cuộc gọi ra chúng ta gọi hàm như sau

```
InCallActivity.startInCall(
                requireContext(),
                phoneNumber
            )

```

### &#x20;<a href="#user-content-handle-call-by-yourself" id="user-content-handle-call-by-yourself"></a>

### Lắng nghe các sự kiện <a href="#user-content-listeners" id="user-content-listeners"></a>

Khi sử dụng SDK các sự kiện từ SDK sẽ được notification ra bằng cách lắng nghe các lớp&#x20;

* `OmiListener` Lắng nghe các sự kiện trong cuộc gọi

``

`OmiListener`&#x20;

| Tên hàm                 | Mô tả                                                              | Ví dụ                                                                 |
| ----------------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------- |
| `onAccountRegistered`   | Sự kiện được gọi khi tài khoản đăng nhập thành công                |                                                                       |
| onAccountRegisterFailed | Sự kiện được gọi khi tài khoản đăng nhập thất bại                  |                                                                       |
| onCallEstablished       | Sự kiện được gọi khi cuộc gọi được thiết lập thành công            |                                                                       |
| onCallEnd               | Sự kiện được gọi khi cuộc gọi kết thúc                             |                                                                       |
| incomingReceived        | Sự kiện được gọi khi có cuộc gọi đến                               |                                                                       |
| onRinging               | Cuộc gọi kết nối thành công đang đổ chuông                         |                                                                       |
| onConnectionTimeout     | Cuộc gọi kết nối thất bại do không nhận được phản hồi của máy chủ  |                                                                       |
| onHold                  | Cuộc gọi bị giữ lại                                                | <p></p><pre><code>OmiClient.instance.toggleHold()</code></pre><p></p> |
| onMuted                 | Cuộc gọi bị tắt âm thanh                                           | <pre><code>OmiClient.instance.toggleMute()</code></pre>               |

để làm việc này chúng ta cần thực hiện như sau:

```
OmiClient.instance.setListener(OmiListener)
```

### Thông báo cuộc gọi đến <a href="#user-content-handle-call-by-yourself" id="user-content-handle-call-by-yourself"></a>

Initialize SDK with customUI parme set to true

Thông thường SDK sẽ tự có màn hình để hiển thị cuộc gọi đến như sau:

<img src="../../../.gitbook/assets/image (1).png" alt="" data-size="original">



Trường hợp bạn muốn mình tự Custom màn hình này thì có thể tuỳ chỉnh cấu hình SDK như sau:

```
OmiClient(requireContext()).initSDK(
    userName,
    password,
    realm,
    customUI = true
)
```

Sau đó chúng ta sẽ cài đặt Listenner để lắng nghe sự kiện thông báo cuộc gọi tới như sau:

```
OmiClient.instance.setListener(OmiListener)
```

### Các sự kiện khi cuộc gọi diễn ra <a href="#user-content-actions-when-in-a-call" id="user-content-actions-when-in-a-call"></a>

Các sự kiện chúng ta có thể thực hiện để can thiệp vào một cuộc gọi bao gồm :

&#x20;

| Tên hàm    | Mô tả                          | Ví dụ                                                              |
| ---------- | ------------------------------ | ------------------------------------------------------------------ |
| pickUp     | chấp nhận cuộc gọi tới         | <pre><code>OmiClient.instance.pickUp()</code></pre>                |
| decline    | Từ chối cuộc gọi               | <p></p><pre><code>OmiClient.instance.decline()</code></pre><p></p> |
| hangup     | Tự chối cuộc gọi               | <p></p><pre><code>OmiClient.instance.hangUp()</code></pre><p></p>  |
| toggleHold | Giữ cuộc gọi hiện tại          | <p></p><pre><code>OmiClient.instance.toggleHold()</code></pre>     |
| toggleMute | Tắt âm thanh cuộc gọi hiện tại | <pre><code>OmiClient.instance.toggleMute()</code></pre>            |

