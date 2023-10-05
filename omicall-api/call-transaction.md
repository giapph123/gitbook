---
description: Quản lý thông tin lịch sử cuộc gọi
---

# Lịch sử cuộc gọi

{% swagger baseUrl="[URL]" path="/api/call_transaction/list" method="get" summary="Danh sách" %}
{% swagger-description %}
Lấy danh sách lịch sửa cuộc gọi
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token: Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="agents" type="array" %}
Mảng email nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user_uuids" type="Array" %}
Username hoặc Usercode của bên thứ 3
{% endswagger-parameter %}

{% swagger-parameter in="query" name="is_auto_call" type="boolean" %}
Bao gồm cuộc gọi tự động (true / false / NULL)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keyword" type="string" %}
Từ khóa tìm kiếm
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sip_user" type="string" %}
Số nội bộ của nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="query" name="agents" type="array" %}
Danh sách email nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="query" name="disposition" type="string" %}
Trạng thái : '**cancelled**' : Không trả lời, '**answered**' : Trả lời
{% endswagger-parameter %}

{% swagger-parameter in="query" name="direction" type="array" %}
Hướng gọi ('**outbound**' : Gọi đi ; '**inbound**' : Gọi đến; '**local**' : Gọi nội bộ)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="number" %}
Trang : Bắt đầu từ 1 ( Mặc định là 1)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="size" type="number" %}
Số lượng record trên một trang. Mặc định 50&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="query" name="from_date" type="number" %}
Từ ngày (Timestamp in milliseconds)&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="query" name="to_date" type="number" %}
Đến ngày (Timestamp in milliseconds)&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sip_numbers" type="array" %}
Danh sách số hotline
{% endswagger-parameter %}

{% swagger-parameter in="query" name="queue_destination" type="array" %}
Danh sách số nhóm nội bộ (Hàng đợi)

_API Tổng đài >> Nhóm nội bộ_
{% endswagger-parameter %}

{% swagger-response status="200" description="Danh sách cuộc gọi" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "DESKTOP-3I0NHO0",
    "payload": {
        "items": [
            {
                "transaction_id": "2159f8d9-5a6e-440f-8995-8d0f55c1xxx", // id 
                "direction": "outbound", // Loại cuộc gọi
                "source_number": "842899990338", // Số điện thoại gọi đi
                "destination_number": "0395187319", // Số điện thoại nhận
                "disposition": "answered", // answered : Trả lời, cancelled : Không trả lời
                "bill_sec": 5, // Thời lượng tính tiền
                "record_seconds" : 10, // Trả lời / không trả lời (số giây file ghi âm)
                "time_start_to_answer": 1575253218, //Thời gian bắt đầu cuộc gọi
                "recording_file": "https://drive.google.com/uc?id=6NZI5ZucJ6E-g9NcvXPU8D0&export=download", // Đường dẫn file ghi âm
                "sip_user": "142", // Số nội bộ
                "duration": 20, //Thời lượng tính từ khi bấm gọi
                "provider" : "viettel", // Nhà mạng
                "note": "Ghi chu cuoc goi",
                "tag":["hailong","dongy","vip"],
                "record_seconds": 5, // Số giây file ghi âm,
                "call_out_price": 2389, //Cước phí,
                "created_date": 1575253235933, // Ngày tạo
                "last_updated_date": 1575253239002, // Lần cập nhật cuối cùng
                "is_voicemail" : true/false, // Hộp thư thoại
                "recording_file_voicemail" : "", //File ghi âm hộp thư thoại
                "user": [ // Thông tin nhân viên
                    {
                        "full_name": "TRAN VAN TIEN",
                        "full_name_unsigned": "TRAN VAN TIEN",
                        "note" : "Ghi chú về cuộc gọi ở đây",
                        "tag" :[ // Danh sách thẻ tag cuộc gọi
                            {"name": "hailong"},
                            {"name": "dongy"},
                            {"name": "vip"}
                        ]
                    }
                ],
                "create_by":{ // Thông tin người gọi
                       "id":"6475adb3600dc522432610f0",
                       "name":"Nguyen Thi Hoa",
                       "contact_id":"6475adb0600dc522432610ef",
                       "avatar":null,
                       "gender":null,
                       "uuid":"0383459972",
                       "type":"extension"
                },
                "internal_destination":{ // Thông tin người nhận (cho gọi nội bộ)
                       "id":"6475ae1a600dc5224326111c",
                       "contact_id":"6475ae19600dc5224326111b",
                       "name":"Bui Chi Hau",
                       "uuid":"0344171555",
                       "extension":"6350",
                       "type":"extension"
                },
                "evaluations": null, // Chi tiết về ĐÁNH GIÁ cuộc gọi,
                "total_evaluate": null, // Điểm trung bình và số lần đánh giá
                "customer": { // Thông tin khách hàng
                    "full_name": "Trần Văn Tiến",
                    "full_name_unsigned": "Tran Van Tien"
                },
                "is_have_forward_out" : true, // Chuyển tiến ra sim true/false
                "bill_sec_forward_out" : 90 // Số giây chuyển tiếp ra bên ngoài 
            }
        ],
        "page_number": 1, // Trang
        "page_size": 50, // Kích thước trang
        "total_items": 943, // Tổng số records
        "total_pages": 19, // Tổng số trang
        "has_next": true,
        "next_page": 2,
        "has_previous": false,
        "previous_page": 1
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

| Mã Lỗi                       | Mô tả                                                      |
| ---------------------------- | ---------------------------------------------------------- |
| _limit\_request\_30\_minute_ | Các request cách nhau 30 phút                              |
| _from\_date\_is\_required_   | Từ ngày là bắt buộc                                        |
| _to\_date\_is\_required_     | Đến ngày là bắt buộc                                       |
| _date\_invalid_              | Từ ngày hoặc đến ngày không hợp lệ                         |
| _date\_is\_too\_long_        | Khoảng cách giữa từ ngày - đến ngày : Chỉ cho phép 30 ngày |



{% swagger baseUrl="[URL]" path="/api/call_transaction/detail/:transaction_id" method="get" summary="Chi tiết cuộc gọi" %}
{% swagger-description %}
Lấy thông tin chi tiết cuộc gọi
{% endswagger-description %}

{% swagger-parameter in="path" name="transaction_id" type="string" %}
Id cuộc gọi
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token: Bearer 'token'
{% endswagger-parameter %}

{% swagger-response status="200" description="Yêu cầu thành công" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "cloud-vihat-saas-sync-public-api-687664b69d-69mmh",
    "payload": {
        "transaction_id": "91d3e842-9da2-43ec-8bb1-979c17e817ad",
        "direction": "outbound",
        "source_number": "842727777787",
        "destination_number": "0979816773",
        "disposition": "answered",
        "bill_sec": 232,
        "record_seconds": 232,
        "time_start_to_answer": 1589015432,
        "recording_file": "https://drive.google.com/.......",
        "sip_user": "101",
        "created_date": 1589015675440,
        "last_updated_date": 1589015678726,
        "ivr": "none",
        "call_out_price": 2389,
        "note": "Ghi chu cuoc goi", // Ghi chu cuoc goi
        "tag":["hailong","dongy","vip"], // tag cuoc goi
        "provider": "viettel",
        "duration": 242,
        "user": [
            {
                "full_name": "TestBoss 123",
                "full_name_unsigned": "TestBoss 123",
                "note" : "Ghi chú về cuộc gọi ở đây",
                "tag" :[ // Danh sách thẻ tag cuộc gọi
                    {"name": "hailong"},
                    {"name": "dongy"},
                    {"name": "vip"}
                ]
            }
        ],
        "customer": {
            "full_name": "Trần Văn Tiến 1",
            "full_name_unsigned": "Tran Van Tien 1"
        },
        "is_have_forward_out" : true, // Chuyển tiến ra sim true/false
        "bill_sec_forward_out" : 90 // Số giây chuyển tiếp ra bên ngoài 
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/call_transaction/change/:transaction_id" method="post" summary="Cập nhật thông tin cuộc gọi" %}
{% swagger-description %}
\- Cập nhật các thông tin bổ sung cho lịch sử cuộc gọi
{% endswagger-description %}

{% swagger-parameter in="path" name="transaction_id" type="string" %}
Id cuộc gọi
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token: Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tag" type="array" %}
Danh sách Tag được gán với lịch sử cuộc gọi \
Ví dụ : `tag : ["hailong","goilaisau"]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="note" type="string" %}
Ghi chú cuộc gọi
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "status_code": 9999,
    "payload": {
        "transaction_id": "91d3e842-9da2-43ec-8bb1-979c17e817ad",
        "direction": "outbound",
        "source_number": "842727777787",
        "destination_number": "0979816773",
        "disposition": "answered",
        "bill_sec": 232,
        "record_seconds": 232,
        "time_start_to_answer": 1589015432,
        "recording_file": "https://drive.google.com/uc?id=1Jry_LGzQM....",
        "sip_user": "101",
        "created_date": 1589015675440,
        "last_updated_date": 1589015678726,
        "ivr": "none",
        "note": null,
        "provider": "viettel",
        "note": "Ghi chu cuoc goi",
        "tag":["hailong","dongy","vip"],
        "duration": 242,
        "user": [
            {
                "full_name": "TestBoss 123",
                "full_name_unsigned": "TestBoss 123",
                "note": "Ghi chu cuoc goi",
                "tag" :[ // Danh sách thẻ tag cuộc gọi
                    {"name": "hailong"},
                    {"name": "dongy"},
                    {"name": "vip"}
                ]
            }
        ],
        "customer": {
            "full_name": "Trần Văn Tiến 1",
            "full_name_unsigned": "Tran Van Tien 1"
        }
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="[URL]" path="/api/call_transaction/report" method="get" summary="Thống kê cuộc gọi" %}
{% swagger-description %}
Thống kê tổng quan lịch sử cuộc gọi
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token: Bearer 'token'
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="numbers" type="array" %}
Danh sách đầu số
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sip_user" type="string" %}
Số nội bộ nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="query" name="agents" type="array" %}
Danh sách email nhân viên
{% endswagger-parameter %}

{% swagger-parameter in="query" name="to_date" type="number" %}
Đến ngày (Timestamp in milliseconds)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="from_date" type="number" %}
Từ ngày (Timestamp in milliseconds)
{% endswagger-parameter %}

{% swagger-response status="200" description="Tổng quan báo cáo cuộc gọi" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "cloud-vihat-saas-sync-public-api-5f7c4fc9d6-vjgrb",
    "payload": {
        "categorized_by_direction": [
            {
                "_id": "inbound", // Gọi vào
                "total_count": 1051, // Số cuộc 
                "total_time": 978 // Số giây
            },
            {
                "_id": "outbound", // Gọi ra
                "total_count": 138, // Số cuộc
                "total_time": 1658 // Số giây
            }
        ],
        "categorized_by_disposition": [
            {
                "_id": "cancelled", // Gọi không trả lời
                "total_count": 1177, // Tổng số cuộc
                "total_outbound": 133, // Số cuộc gọi ra
                "total_inbound": 1044 // Số cuộc gọi vào
            },
            {
                "_id": "answered", // Gọi trả lời
                "total_count": 12, // Tổng số cuộc
                "total_outbound": 5, // Số cuộc gọi ra
                "total_inbound": 7 // Số cuộc gọi vào
            }
        ],
        "categorized_by_local_direction": { // Gọi nội bộ
            "total_call": 23,  // Tổng số cuộc
            "total_call_answer": null // Tổng số trả lời
        }
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/api/evaluation_criteria/call/list" baseUrl="[URL]" summary="Danh sách tiêu chí đánh giá cuộc gọi" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Access token: Bearer 'token'
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://public-v1-stg.omicall.com/api/call_transaction/search" summary="Lấy danh sách chi tiết lịch sử cuộc gọi" %}
{% swagger-description %}
Danh sách chi tiết lịch sử cuộc gọi, lấy chi tiết rút gọn

Dữ liệu Body truyền lên dưới định dạng JSON. Ví dụ:

{

&#x20; "from\_date" : 1693846799000,

&#x20; "to\_date" : 1696438799000,

&#x20; "user\_uuids" : \["0123456789"]

}
{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-key" required="true" %}
API key
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user_uuids" type="List<String>" required="true" %}
Danh sách user UUID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="from_date" required="true" %}
Thời gian bắt đầu lấy log (milisecond)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="to_date" required="true" %}
Thời gian kết thúc lấy log (milisecond)
{% endswagger-parameter %}

{% swagger-parameter in="path" name="page" type="int" %}
Page cần get (= 1)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="direction" type="List<String>" %}
Hướng gọi ("inbound", "outbound", "local")
{% endswagger-parameter %}

{% swagger-parameter in="path" name="size" type="int" %}
Số phần tử trong trang (max 50 item)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="disposition" type="List<String>" %}
Trạng thái trả lời/không trả lời ("answered", "cancelled")
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="List<String>" %}
Danh sách ID tags
{% endswagger-parameter %}

{% swagger-parameter in="body" name="numbers" type="List<String>" %}
Danh sách đầu số
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Dữ liệu trả về thành công (JSON format)" %}
```json
// sample data
{
  "instance_id": "stg",
  "payload": {
    "items": [
      {
        "_id": "123400000000000000000000",
        "created_date": 946659600000,
        "last_updated_date": 946659600000,
        "create_by": {
          "id": "123400000000000000000000",
          "name": "Lorem ipsum dolor sit amet.",
          "contact_id": "123400000000000000000000",
          "type": "agent",
          "extension": "0123456"
        },
        "tenant_id": "123400000000000000000000",
        "transaction_id": "7125081d-288a-4d35-8eb1-012345678912",
        "direction": "local",
        "source_number": "0123456",
        "destination_number": "0123456",
        "disposition": "cancelled",
        "duration": 28,
        "bill_sec": 0,
        "record_seconds": 0,
        "time_start_call": 9466596000,
        "time_end_call": 9466596000,
        "time_start_to_answer": 9466596000,
        "ms_time_start_to_answer": 946659600000,
        "time_start_media": 9466596000,
        "wait_sec": 0,
        "hold_call_sec": 0,
        "hangup_cause": "ORIGINATOR_CANCEL",
        "hangup_cause_q850": 16,
        "customer": {
          "_id": "649e981afd4c703b39692f5f",
          "full_name": "Lorem ipsum dolor sit amet.",
          "full_name_unsigned": "Lorem ipsum dolor sit amet.",
          "uuid": "0123456789",
          "type": "extension",
          "extension": "0123456"
        },
        "user": [
          {
            "_id": "123400000000000000000000",
            "full_name": "Lorem ipsum dolor sit amet.",
            "full_name_unsigned": "Lorem ipsum dolor sit amet.",
            "tags_view": [],
            "note_created_date": 1696421425598
          }
        ],
        "sip_user": "0123456",
        "is_stop_ivr": false,
        "ivr": "none",
        "is_have_forward_out": false,
        "is_auto_call": false,
        "is_deleted": false,
        "rtp_audio_in_mos": 4.5,
        "is_callbot": false,
        "dial_status": "CANCEL",
        "answer_sec": 0,
        "domain_fusion": "Lorem ipsum dolor sit amet.",
        "sip_from_user": "1000071",
        "nation": "vn",
        "is_ai": false,
        "domain": "Lorem ipsum dolor sit amet.",
        "playback_seconds": 0,
        "pbx_type": "",
        "is_trunk": false,
        "suspicious_checked": false,
        "is_missed_call": false,
        "is_analyzed": false,
        "internal_destination": {
          "id": "123400000000000000000000",
          "contact_id": "649e981afd4c703b39692f5f",
          "name": "Lorem ipsum dolor sit amet.",
          "uuid": "0123456789",
          "extension": "0123456",
          "type": "extension"
        }
      }
    ],
    "pageNumber": 1,
    "pageSize": 20,
    "totalItems": 1000,
    "totalPages": 100,
    "hasNext": true,
    "nextPage": 2,
    "hasPrevious": false,
    "previousPage": 1
  },
  "instance_version": "1.0.0",
  "key_enabled": false,
  "status_code": 9999
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/api/call_transaction/add_evaluation/:transaction_id" baseUrl="[URL]" summary="Đánh giá cuộc gọi theo tiêu chí " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="transaction_id" type="String" required="true" %}
Transaction Id cuộc gọi
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user_uuid" type="String" required="true" %}
Id của User bên thứ 3 hoặc Số máy lẻ trong hệ thống
{% endswagger-parameter %}

{% swagger-parameter in="body" name="evaluation" type="Object" required="true" %}
Đối tượng chưa thông tin đánh giá, json format như sau

_**(Format như ảnh bên dưới )**_
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thông tin cuộc gọi + đánh giá" %}

{% endswagger-response %}

{% swagger-response status="201" description="" %}

{% endswagger-response %}
{% endswagger %}

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-27 at 8.30.23 AM.png" alt=""><figcaption></figcaption></figure>

