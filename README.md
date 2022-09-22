# Overview

**HƯỚNG DẪN TÍCH HỢP OMICALL API CƠ BẢN**&#x20;

* **Xác thực**

{% hint style="info" %}
Mỗi DN sẽ có 1 API KEY . Dùng API KEY để lấy AccessToken.&#x20;

Access Token sẽ có giá trị trong vòng 24h. Hết hạn thì tiến hành lấy lại

LẤY API KEY và XÁC THỰC

[https://api.omicall.com/omicall-api/overview](https://api.omicall.com/omicall-api/overview)

[https://api.omicall.com/omicall-api/authentication](https://api.omicall.com/omicall-api/authentication)
{% endhint %}

* **Tạo mới nhân viên , tạo mới tổng đài cho nhân viên**

{% hint style="success" %}
Mỗi nhân viên được định danh trong hệ thống qua&#x20;

số NỘI BỘ / EXTENSION / MÁY NHÁNH

Mỗi nhân viên sẽ có 3 giá trị để xác thực với tổng đài&#x20;

* **domain** : Domain tổng đài của doanh nghiệp
* **username** : Mã máy nhánh ví dụ : 101, 102, 103 ...&#x20;
* **password** : Mật khẩu máy nhánh&#x20;

Dùng API bên dưới để tạo 1 nhân viên, OMI sẽ response về thông tin tổng đài cho 1 nhân viên, bên thứ 3 có thể lưu vào hệ thống

[https://api.omicall.com/omicall-api/agent](https://api.omicall.com/omicall-api/agent)

API : /api/agent/invite

Hoặc : Nếu nhân viên đã có ở OMI, mà không cần tạo mới thì có thể lấy qua API

[https://api.omicall.com/omicall-api/call-center](https://api.omicall.com/omicall-api/call-center)
{% endhint %}

* **Tích hợp WebSDK nghe và gọi trên phần mềm thứ 3**

{% hint style="success" %}
Sau khi có được 3 thông số : domain, username, password ở Bước 2

Tiến hành tích hợp websdk và điền 3 thông số trên vào WebSDK để nghe và gọi

WebSDK: [https://api.omicall.com/web-sdk/overview](https://api.omicall.com/web-sdk/overview)

**Chú ý** : _Develop trên localhost có thể không cần https, nhưng khi đưa lên production bắt buộc phải là https (vì chỉ https mới mở được micro, sound trên trình duyệt)_
{% endhint %}

* **Nhận dữ liệu cuộc gọi**

{% hint style="success" %}
Sau khi kết thúc cuộc gọi, có thể lấy data cuộc gọi thông qua 2 cơ chế

**Webhook** : Nhận data cuộc gọi chủ động, lưu bên thứ 3

[https://api.omicall.com/webhooks/call-hooks](https://api.omicall.com/webhooks/call-hooks)



API lịch sử : Nhận dữ liệu qua API của OMICall

[https://api.omicall.com/omicall-api/call-transaction](https://api.omicall.com/omicall-api/call-transaction)


{% endhint %}

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

{% content-ref url="web-sdk/overview.md" %}
[overview.md](web-sdk/overview.md)
{% endcontent-ref %}
