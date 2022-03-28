---
description: Webhook cuộc gọi
---

# Webhook

## Nhận dữ liệu cuộc gọi từ Webhook

* Đối tác khai báo API để nhận dữ liệu cuộc gọi từ WEBHOOK trả về
* _**METHOD : POST**_
* _**Content-type : application/json**_

{% hint style="info" %}
**Webhook data khi cuộc gọi đã kết thúc**
{% endhint %}

![](<../.gitbook/assets/image (6).png>)

```
{
   "tenant_id": "5f68.......", // Id của doanh nghiệp
   "transaction_id":"91d3e842-9da2-43ec-8bb1-979c17e817ad", // id cuộc gọi
   "direction":"outbound", // Hướng gọi outbound, inbound, local
   "source_number":"842727777787", //Số hotline
   "destination_number":"0979816773", // Số khách hàng
   "disposition":"answered", //Tình trạng cuộc gọi
   "bill_sec":232, // Số giây tính tiền
   "record_seconds":232, // Số giây file ghi âm
   "time_start_to_answer":1589015432, //thời gian bắt đầu trả lời
   "recording_file":"https://drive.google.com/uc?id=1Jry_LGzQM....", // File ghi âm
   "sip_user":"101", // Số máy lẻ nhân viên
   "created_date":1589015675440, // Thời gian tạo
   "last_updated_date":1589015678726, // Lần cập nhật cuối cùng
   "ivr":"none",
   "provider":"viettel", // Nhà mạng của số khách hàng
   "duration":242, // Số giây tính từ khi đổ chuông đến khi kết thúc
   "is_auto_call" : false, // Gọi thường hoặc gọi tự động
   "call_out_price" : 3990.0, // Số tiền
   "user":[
      {
         "full_name":"TestBoss 123",
         "full_name_unsigned":"TestBoss 123",
         "note":"Ghi chu cuoc goi",
         "tag":[{"name":"hailong"},{"name":"dongy"},{"name":"vip"}]
      }
   ],
   "customer":{
      "full_name":"Trần Văn Tiến 1",
      "full_name_unsigned":"Tran Van Tien 1"
   }
}
```

{% hint style="info" %}
**Webhook khi cuộc gọi đang diễn ra**
{% endhint %}

* Gửi thông tin cuộc gọi đang diễn ra cho đối tác tích hợp
* **Trạng thái gồm : ringing**(Đổ chuông)**, answered** (Kết nối) , **hangup** (Kết thúc)

![](<../.gitbook/assets/image (4).png>)

```
{
  "to_number": "0395187319", // Số điện thoại khách hàng
  "created_time": 1626693561, // Ngày khởi tạo cuộc gọi
  "date_time": 1626693561000, // Thời gian hook
  "from_number": "100", // Số máy lẻ gọi
  "hotline": "0868694566", // Số hotline của doanh nghiệp
  "call_uuid": "fee91d6c-90b0-4826-97d7-9ca74c58a4e7", // Id cuộc gọi = transaction_id
  "state": "ringing", //ringing : Đang kết nối; answered : Kết nối, hangup : Kết thúc 
  "direction": "outbound" // outbound : Gọi ra, inbound : Gọi vào
}
```
