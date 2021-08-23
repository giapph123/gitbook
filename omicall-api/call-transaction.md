---
description: Quản lý thông tin lịch sử cuộc gọi
---

# Lịch sử cuộc gọi

{% api-method method="get" host="\[URL\]" path="/api/call\_transaction/list" %}
{% api-method-summary %}
Danh sách
{% endapi-method-summary %}

{% api-method-description %}
Lấy danh sách lịch sửa cuộc gọi
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token: Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="agents" type="array" required=false %}
Mảng email nhân viên
{% endapi-method-parameter %}

{% api-method-parameter name="is\_auto\_call" type="boolean" required=false %}
Bao gồm cuộc gọi tự động \(true / false / NULL\)
{% endapi-method-parameter %}

{% api-method-parameter name="keyword" type="string" required=false %}
Từ khóa tìm kiếm
{% endapi-method-parameter %}

{% api-method-parameter name="sip\_user" type="string" required=false %}
Số nội bộ của nhân viên
{% endapi-method-parameter %}

{% api-method-parameter name="disposition" type="string" required=false %}
Trạng thái : '**cancelled**' : Không trả lời, '**answered**' : Trả lời
{% endapi-method-parameter %}

{% api-method-parameter name="direction" type="array" required=false %}
Hướng gọi \('**outbound**' : Gọi đi ; '**inbound**' : Gọi đến; '**local**' : Gọi nội bộ\)
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="number" required=false %}
Trang : Bắt đầu từ 1 \( Mặc định là 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" required=false %}
Số lượng record trên một trang. Mặc định 50 
{% endapi-method-parameter %}

{% api-method-parameter name="from\_date" type="number" required=true %}
Từ ngày \(Timestamp in milliseconds\) 
{% endapi-method-parameter %}

{% api-method-parameter name="to\_date" type="number" required=true %}
Đến ngày \(Timestamp in milliseconds\) 
{% endapi-method-parameter %}

{% api-method-parameter name="source\_number" type="string" %}
Số điện thoại gọi đi
{% endapi-method-parameter %}

{% api-method-parameter name="destination\_number" type="string" %}
Số điện thoại nhận
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Danh sách cuộc gọi
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

| Mã Lỗi | Mô tả |
| :--- | :--- |
| _limit\_request\_30\_minute_ | Các request cách nhau 30 phút |
| _from\_date\_is\_required_ | Từ ngày là bắt buộc |
| _to\_date\_is\_required_ | Đến ngày là bắt buộc |
| _date\_invalid_ | Từ ngày hoặc đến ngày không hợp lệ |
| _date\_is\_too\_long_ | Khoảng cách giữa từ ngày - đến ngày : Chỉ cho phép 3 ngày |

{% api-method method="get" host="\[URL\]" path="/api/call\_transaction/detail/:transaction\_id" %}
{% api-method-summary %}
Chi tiết cuộc gọi
{% endapi-method-summary %}

{% api-method-description %}
Lấy thông tin chi tiết cuộc gọi
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="transaction\_id" type="string" required=true %}
Id cuộc gọi
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Access token: Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Yêu cầu thành công
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="\[URL\]" path="/api/call\_transaction/change/:transaction\_id" %}
{% api-method-summary %}
Cập nhật thông tin cuộc gọi
{% endapi-method-summary %}

{% api-method-description %}
- Cập nhật các thông tin bổ sung cho lịch sử cuộc gọi
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="transaction\_id" type="string" required=true %}
Id cuộc gọi
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Access token: Bearer 'token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="tag" type="array" required=false %}
Danh sách Tag được gán với lịch sử cuộc gọi   
Ví dụ : `tag : ["hailong","goilaisau"]`
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=true %}
Ghi chú cuộc gọi
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="\[URL\]" path="/api/call\_transaction/report" %}
{% api-method-summary %}
Thống kê cuộc gọi
{% endapi-method-summary %}

{% api-method-description %}
Thống kê tổng quan lịch sử cuộc gọi
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token: Bearer 'token'
{% endapi-method-parameter %}

{% api-method-parameter name="Content-type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="numbers" type="array" required=false %}
Danh sách đầu số
{% endapi-method-parameter %}

{% api-method-parameter name="sip\_user" type="string" required=false %}
Số nội bộ nhân viên
{% endapi-method-parameter %}

{% api-method-parameter name="to\_date" type="number" required=true %}
Đến ngày \(Timestamp in milliseconds\)
{% endapi-method-parameter %}

{% api-method-parameter name="from\_date" type="number" required=true %}
Từ ngày \(Timestamp in milliseconds\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Tổng quan báo cáo cuộc gọi
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

