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
  "answer_sec": 5, // Số giây trả lời 
  "bill_sec": 6, // Thời lượng cuộc gọi , tính tiền 
  "call_out_price": 55.002, // Tổng tiền cuộc gọi 
  "create_by": { // Người tạo hoặc nhân viên thực hiện cuộc gọi đó
    "contact_id": "6209c98c067f745da47367d1",
    "id": "6209c98561c1cb163ded25fa",
    "name": "Trần Văn Tiến 1234"
  },
  "created_date": 1697595795704, // Ngày tạo
  "customer": {
    "full_name": "Mr. Tiến Demo2",
    "full_name_unsigned": "mr. tien demo2"
  },
  "destination_number": "0395187319", // Số bị gọi
  "direction": "outbound", // Hướng gọi : inbound, outbound, local
  "domain_fusion": "contact18",
  "duration": 12, // Tổng thời gian, tính từ khi có tín hiệu rung chuông
  "endby_name": "end_call_by_customer",
  "from_number": "100",
  "hotline": "842899959300", // Số hotline
  "is_auto_call": false,
  "is_have_forward_out": false,
  "ivr": "none",
  "last_updated_date": 1697595795853,
  "note": "",
  "phone_number": "0395187319",
  "provider": "viettel",
  "record_seconds": 5,
  "recording_file_url": "https://public-v1-stg.omicrm.com/third_party/recording/uc?id=SVJ1TTVlK0ZUZUdZZ1luR3VEdTlNemIwYTAwb3FEY2VkekJveGtvRTRhdlV2NCtKcytDT1dNbEJsOFRXWWhqWmpKSmNmUUtRQW40V1ZpbGpWZnpzVkE9PQ==&code=ae5f56fc-7baa-4537-b312-1105023bbb49",
  "send_num_retry": 1,
  "sip_number": "842899959300",
  "sip_user": "100",
  "source_number": "842899959300",
  "state": "cdr",
  "tag": [],
  "tenant_id": "6209c98461c1cb163ded25f7",
  "time_end_call": 1697595795,
  "time_start_call": 1697595783, // Thời gian bắt đầu gọi 
  "time_start_to_answer": 1697595783,
  "to_number": "0395187319",
  "transaction_id": "ae5f56fc-7baa-4537-b312-1105023bbb49", // ID cuộc gọi
  "transfer_histories": [],
  "user": [
    {
      "full_name": "Trần Văn Tiến 1234",
      "full_name_unsigned": "Tran Van Tien 1234"
    }
  ]
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
