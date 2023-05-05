---
description: mô tả các đầu số trong tổng đài, ý nghĩa, định dạng từng loại đầu số
---

# Định nghĩa đầu số

Hiện tại trong tổng đài có nhiều tập dữ liệu khác nhau:

* Contact: lưu trữ thông tin liên hệ của khách hàng gồm tên/ số điện thoại ...&#x20;
* Nhân viên: lưu trữ các tài khoản của nhân viên, được phép truy cập vào web của công ty tuỳ theo phân quyền để sử dụng các chức năng . <mark style="color:green;">**Mỗi nhân viên được gán 1 đầu số gọi là số nội bộ để có thể tiếp nhận cuộc gọi hoặc gọi qua lại lẫn nhau**</mark>
* Nhóm nội bộ: Trong tổng đài Omicall cho phép gom nhóm nhiều nhân viên với nhau để tạo thành 1 nhóm các nhân viên, mục đích chia phòng ban, nhóm nhỏ để có thể lắng nghe cuộc gọi ví dụ nhóm chăm sóc khách hàng sẽ được phân nghe số hotline xxx . <mark style="color:green;">**Mỗi nhóm nội bộ được gán 1 đầu số nội bộ và có thể gọi tới đầu số nội bộ này từ một số nội bộ khác ví dụ số nội bộ của nhân viên gọi vào số nội bộ của nhóm nộ bộ, vẫn hợp lệ**</mark>&#x20;
* Tương tác phím: hay còn gọi là IVR , là một chương trình dùng để cấu hình tương tác với người dùng trong cuộc gọi, cho phép bắt được các sự kiện nhấn phím trên điện thoại của người dùng để có các hành động khác nhau ( phát nhạc chờ, chuyển cuộc gọi ...) khi người dùng nhấn phím 1, thì sẽ làm gì, phím 2 thì sẽ làm gì . <mark style="color:green;">**Mỗi tương tác phím được gán một đầu số nội bộ và có thể gọi tới đầu số nội bộ này từ một số nội bộ khác ví dụ số nội bộ của nhân viên gọi vào số nội bộ của nhóm nộ bộ, vẫn hợp lệ**</mark>
* Kịch bản : là một chương trình quy định các tham số cấu hình cuộc gọi cho một đầu số, tóm lại kịch bản sẽ quy định cách đầu số hoạt động như trỏ vào nhóm nội bộ nào, hay trỏ vào nhân viên nào... . <mark style="color:green;">**Mỗi  Kịch bản được gán một đầu số nội bộ và có thể gọi tới đầu số nội bộ này từ một số nội bộ khác ví dụ số nội bộ của nhân viên gọi vào số nội bộ của nhóm nộ bộ, vẫn hợp lệ**</mark>
* Đầu số của doanh nghiệp: là số SIP doanh nghiệp thuê của nhà mạng để đón cuộc gọi của khách hàng, định dạng 10 số&#x20;
* Số điện thoại khách hàng: là đầu số mobile phone của khách hàng dạng 10 số&#x20;

Định dạng ( Format ) của các đầu số :&#x20;

* Số điện thoai khách hàng thường: 10 chữ số&#x20;
* Số nội bộ:
  * Số nhân viên < 5 số&#x20;
  * Số kịch bản từ 5 -> 9 số&#x20;
  * Số cây tương tác phím IVR từ 5 -> 9 số&#x20;
  * Số nhóm nội bộ từ 5 -> 9 số
