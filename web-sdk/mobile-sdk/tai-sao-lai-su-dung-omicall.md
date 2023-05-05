# Tại sao lại sử dụng OMICALL

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Ngày nay với sự phát triển của công nghệ để tạo một ứng dụng nghe gọi qua công nghệ Voip là vô cùng đơn giản, chỉ cần vài dòng code là đã có thể thực hiện được.

Tuy nhiên việc áp dụng VOIP vào môi trường production nơi mà mọi sai sót đều phải giảm thiểu tối đa, mọi thông số cần tối ưu hoá, để phù hợp với đại đa số hoàn cảnh thực tế , Điều này đòi hỏi kinh nghiệm và không phải đơn vị/ cá nhân nào cũng có thể làm tốt được.

Với một cuộc gọi Voip, thông thường các thông số sau sẽ cần được quan tâm:

* Jitter: độ trễ khi nhận các gói tin,  cao sẽ làm méo, giật giọng &#x20;
* Latency: độ trễ giữa các lần gửi các gói tin , cao sẽ làm méo, giật giọng&#x20;
* Package loss:  mất mát gói tin , cao sẽ làm méo, giật giọng&#x20;
* MOS: điểm đánh giá chất lượng cuộc gọi , điểm thấp sẽ làm méo, giật giọng&#x20;

Để tối ưu 4 thông số trên đòi hỏi phải quan tâm đến rất nhiều thông số bao gồm:

* **Phía client:**
  * Codec thoại phù hợp với từng dòng thiết bị smartphone&#x20;
  * Các thông số như frame rate/ bit rate cần được tính toán thời gian thực để có quyết định mã hoá cũng như giải mã với tốc độ vừa phải không ảnh hưởng chất lượng thoại&#x20;
  * Jitter buffer: thông số cực kỳ quan trọng trong điều kiện mạng yếu, buffer sẽ giúp chúng ta không bị loss dữ liệu, chiến thuật buffer như nào, chiến thuật để xử lý các gói tin tràn buffer ra sao là vấn đề quan trọng&#x20;
* **Phía máy chủ:**
  * Đòi hỏi phải tinh chỉnh các thông số codec tương tự&#x20;
  * Tuỳ vào bản tin phía client để xác định điều kiện mạng từ  đó đưa ra chiến thuật encode phù hợp để client có thể giải mã nhanh nhất ( giảm bit rate )&#x20;
  * Monitor thường xuyên các thông số bandwidth/ latency /RAm/CPU để có phương án dự phòng, nâng cấp, tránh làm giảm chất lượng ví dụ khi cần convert nhiều codec thì CPU sẽ cao, cần nâng cấp khi tới ngưỡng để tránh ảnh hưởng cuộc gọi

Hệ thống phải có các báo cáo rỏ ràng về các thông số trên để theo dõi, cảnh báo chất lượng thoại VOIP một cách tường minh.

Ở Omicall với đội ngũ kinh nghiệm hơn 10 năm VOIP, xây dựng Omicall hơn 5 năm, hoàn toàn có kinh nghiệm xử lý các vấn đề bên trên để đảm bảo chất lượng thoại, video call mượt mà nhất, ngay cả thời điểm chất lượng mạng kém.

Với Omicall không chỉ phục vụ như một tổng đài mà còn cả hệ sinh thái phía sau cuộc gọi : chiến dịch automation workflow,Ticket, Đã kênh, Mail, Drive ...., AI Callbot, AI Phân tích cuộc gọi, AI Speech 2 text ...
