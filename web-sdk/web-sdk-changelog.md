---
description: Lịch sử cập nhật tính năng của Web SDK
---

# Web SDK Changelog

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

