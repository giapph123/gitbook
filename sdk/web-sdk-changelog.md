---
description: Lịch sử cập nhật tính năng của Web SDK
---

# Web SDK Changelog

### 2.0.71 (05/07/2023)

\- Bổ sung giao diện chọn đầu số tương tự như phiên bản Web của OMICall\
\- Fix lỗi hiển thị sai thời gian của thông tin cuộc gọi gần nhất



### 2.0.66 (15/02/2023)

\- Thêm form field id "**note**", type "**text**", multiline, khi không có **forms** và bật cả hai **options.showNoteInput** và **options.showTagField**\
\- Fix bug không hiển thị contact info khi gọi nội bộ tới chính mình\
\- Luồng API lưu thông tin cuộc gọi: bổ sung param "**tag**" từ form data, nếu có



### 2.0.0-rc.65 (14/02/2023)

\- Cập nhật **iceServers** IP config\
\- Thêm **options.showTagField**, thêm nhanh form field id "**tag**", type "**multiselect**" cho **forms**\
\- Thêm **options.showInfoLastCall**, search contact ở OMI và info last call của **remoteNumber** đang gọi. Nếu truyền giá trị **{ overrideContact: true }**, sẽ ưu tiên hiển thị contact info từ API, dù trước đó đã dùng **omiSDK.updateContactInfo()**\
\- Support thêm form field với type "**multiselect**" (thường dùng cho việc gán tag cuộc gọi,...).\
&#x20; Dùng kèm với các function:\
&#x20;  \+ **omiSDKTheme.setSelections(id, selections)**\
&#x20;  \+ **omiSDKTheme.setSelecteds(id, selecteds)**\
&#x20;   \* **selections và selecteds:** mảng dữ liệu, item có thể là **String** hoặc **Object(label, value)**\
&#x20;   **\* selecteds** phải là mảng con, thuộc mảng **selections** => dùng **omiSDKTheme.setSelections** trước **omiSDKTheme.setSelecteds**



### 2.0.0-rc.64 (03/02/2023)

\- **Salesforce:** Support **runApex** trong khi thực hiện cuộc gọi và thêm nút "Logout" ở UI dial



### 2.0.0-rc.63 (23/12/2022)

\- **Fix BUG**: không gọi ra được nếu đang set busy = true\
\- Thêm method **omiSDK.setBusy(Boolean)** và **omiSDK.isBusy()**, thay cho omiSDK.busy như trước đó, hiện sẽ lưu trạng thái busy trong localStorage để đồng bộ trạng thái giữa các tab của trình duyệt, vẫn có thể cập nhật trạng thái busy trong config khi init như cũ



### 2.0.0-rc.62 (23/12/2022)

\- **Fix BUG**: error trong callback event, chỉ chặn makeCall khi có calling session 1 lần,...\
\- Support khai báo callback event dạng:\
&#x20; \+ **omiSDK.on('eventName', callback);**\
&#x20; \+ **omiSDK.off('eventName');**\
\- Support UX/UI cho **Salesforce**



### 2.0.0-rc.61 (08/10/2022)

\- Cập nhật một số màu cơ bản và bộ icon của theme default\
\- Thêm chức năng hiển thị thời gian đổ chuông ở dialog call in và out\
\- Thêm chức năng chỉ đổ chuông cuộc gọi tới khi không có cuộc gọi nào đang diễn ra ở trong cùng một trình duyệt\
\- Thêm biến **isAccepted** trong callback event data để biết cuộc gọi đã được trả lời hay chưa\
\- Thêm menu chức năng hiển thị danh sách cuộc gọi gần đây của số nội bộ đang kết nối\
\- Fix một số bug console.log lỗi ko cần thiết



### 2.0.0-rc.60 (24/08/2022)

\- Bổ sung biến **sipDomain và sipUser** trong callback data\
\- Remove việc sử dụng **encodeURIComponent** với data customize cần lưu thêm vào lịch sử cuộc gọi



### 2.0.0-rc.59 (22/08/2022)

\- Remove biến **session** trong callback data để hạn chế lỗi không xác định\
\- Update method **omiSDK.makeCall,** cho phép truyền tham số thứ 2 dạng Object để có thể truyền thêm custom data và thực hiện cuộc gọi giám sát.\
&#x20;Ví dụ: \
&#x20;\+ **`omiSDK.makeCall('100', { sneakyType: 'whisper' });`** : thực hiện cuộc gọi giám sát thì thầm tới số nội bộ 100;\
&#x20;\+ **`omiSDK.makeCall('0394749346', { datas: { 'User-Data': '{"module":"contact","emp_id":"1"}' } });`** : truyền một String bất kỳ hoặc Object đã stringify (max length = 256 ) để lưu thông tin thêm vào lịch sử cuộc gọi, dữ liệu này sẽ được **encodeURIComponent** trước khi truyền lên tổng đài\


### 2.0.0-rc.58 (02/08/2022)

\- Thêm options **`extraUserAgentString: String`** sẽ cộng chuỗi thêm vào userAgentString của phiên kết nối tổng đài, có format là: \
**`defualtUserAgentString + ';' + extraUserAgentString`**

\- Cập nhật STUN IP cho kết nối tới tổng đài để fix lỗi DNS



### 2.0.0-rc.57 (10/07/2022)

\- Thêm options **`draggable: Boolean`** để cho phép để thay đổi vị trí của nút bật tắt dialog call và dialog cuộc gọi

\- Thêm options **`btnCloseText: String`** để tuỳ chỉnh nội dung chữ của nút đóng và lưu lại cuộc gọi nếu có hiển thị input note hoặc custom forms



### 2.0.0-rc.56 (30/06/2022)

\- Fix lỗi không hiển thị nút "**Đóng và lưu lại**" khi có truyền **forms** tuỳ chỉnh



### 2.0.0-rc.55 (29/06/2022)

\- Cập nhật âm lượng âm báo khi kết thúc cuộc gọi bằng **`0.25 * ringtoneVolume`**



### 2.0.0-rc.54 (27/06/2022)

\- Thêm options **`showNoteInput: Boolean`** để hiển thị input note mặc định và nút "**Đóng và lưu lại**"

