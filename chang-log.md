---
description: Thay đổi bổ sung API OMICALL
---

# Changelog

## 26-05-2021

### Web SDK 2.0.0

### Fixed

* Nâng cấp **SIP.js 2.0.0**
* **Bỏ import jquery**
* Fix lỗi duy trì kết nối WebSocket
* Tối ưu nghe và gọi trên browser, ưu tiên gọi nội mạng
* Phân quyền che số điện thoại
* Rõ ràng hơn các sự kiện trong một cuộc gọi

### Changed

* Thay đổi tên các sự kiện, thuộc tính so với bản 1.0.22 gồm&#x20;
* Thay đổi tên các sự kiện cũ

| 2.0.0               | 1.0.22 (v22)    |
| ------------------- | --------------- |
| **register**        | register\_fn    |
| **invite**          | invite\_fn      |
| **incall**          | ping\_fn        |
| **accepted**        | accept\_fn      |
| **inviteRejected**  | invite\_2fn     |
| **acceptedByOther** | accept\_out\_fn |
| **ended**           | endcall\_fn     |

* Thay đổi tên thuộc tính

| 2.0.0              | 1.0.22(v22)      |
| ------------------ | ---------------- |
| **options**        | form\_ui         |
| **ringtoneVolume** | ringtone\_volume |

### Added

* Bổ sung thêm các sự kiện : Hold cuộc gọi
* UI bổ sung : Thang đo tín hiệu cuộc gọi, Hold cuộc gọi, Chuyển cuộc gọi, Bấm phím

