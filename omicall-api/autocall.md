---
description: API gọi tự động
---

# Gọi tự động

{% swagger baseUrl="[URL]" path="/api/auto_call/execute_by_phone?phone_number=" method="post" summary="Gọi tự động tới một số điện thoại khách hàng" fullWidth="false" %}
{% swagger-description %}
Tạo phiên gọi tự động dựa trên cấu hình & thực thi
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speed" type="number" %}
Tốc độ đọc.Từ chậm : -3. Đến nhanh : 3.&#x20;

Mặc định là 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="voice" type="string" %}
Giọng đọc, có thể một trong các giá trị sau

\




**banmai**

 : Giọng nữ miền Bắc

\




**leminh**

 : Giọng nam miền Bắc

\




**lannhi**

 : Giọng nữ miền Nam
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cid" type="string" %}
Đầu số dùng để gọi tự động. 

\




_Nếu không truyền, mặc định ưu tiên gọi nội mạng_
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Tên của phiên gọi tự động
{% endswagger-parameter %}

{% swagger-parameter in="body" name="template_dialplans" type="array" %}
Cấu trúc phiên gọi tự động theo loại. (tham khảo ví dụ)\
_1. Phiên gọi tự động với file ghi âm_\
\
_2. Phiên gọi tự động  với Text To Speech_\
\
_3. Phiên gọi tự động với file ghi âm và Text To Speech._&#x20;



_4. Phiên gọi tự động với kịch bản bấm phím_&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="body" name="variables" type="string" %}
Mảng giá trị cho Text To Speech

\




_Ví dụ_

 

\




`[`

 

\


 

`"Đơn hàng của bạn là ",`

\


 

`"CKHDKD00203",`

\


 

`"Số tiền",`

\


 

`"900000",`

\


 

`"Đã được bàn giao cho đối tác vận chuyển"`

\


`]`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone_number_list" type="Array" required="true" %}
Danh sách số điện thoại cần gọi
{% endswagger-parameter %}

{% swagger-parameter in="body" name="num_retry" type="Integer" %}
Số lần gọi lại khi không nghe máy. Mặc định là 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="num_per_call" type="Integer" %}
Số cuộc gọi mỗi lần. Mặc định là 15 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="distance_per_call" type="Integer" %}
Khoảng cách thời gian , giữa các lần gọi. Mặc định là 30s
{% endswagger-parameter %}

{% swagger-parameter in="body" name="distance_retry" type="Integer" %}
Khoảng cách giữa các lần gọi lại . Mặc định là 0
{% endswagger-parameter %}

{% swagger-response status="200" description="Thông tin phiên gọi tự động" %}
```
{
    "status_code": 9999,
    "payload": {
        "autocall_id": "91d3e842-9da2-43ec-8bb1-979c17e817ad",
        "name": "Chiến dịch giới thiệu sản phẩm mới"
    }
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/api/auto_call/execute_by_extension?exension=" baseUrl="[URL]" summary="Gọi tự động tới 1 máy nhánh (extension) của tổng đài" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="template_dialplans" type="Array" required="true" %}
Cấu trúc của cuộc gọi , tham khảo ví dụ bên dưới\
_1. Phiên gọi tự động với file ghi âm_



_2. Phiên gọi tự động  với Text To Speech_



_3. Phiên gọi tự động với file ghi âm và Text To Speech. Thực thi theo thứ tự_&#x20;



_4. Phiên gọi tự động với kịch bản bấm phím_&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="query" name="extension" type="String" required="true" %}
Số máy lẻ nhận cuộc gọi
{% endswagger-parameter %}

{% swagger-parameter in="body" name="variables" type="Array" required="true" %}
Mãng giá trị chuỗi, chứa nội dung văn bản cần đọc , nếu kịch bản có chứa Text To Speech 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="extensions" type="Array" %}
Danh sách các số máy lẻ nhận cuộc gọi 
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}


```json
{
    "instance_id": "stg",
    "payload": {
        "autocall_uuids": [
            "f5d39f30-fef7-49df-9ef6-697bf5353983"
        ],
        "autocall_id": "64b8117691447377aecac985"
    },
    "instance_version": "1.2.164",
    "key_enabled": false,
    "status_code": 9999
}
```
{% endswagger-response %}
{% endswagger %}

**Ví dụ** :Tham số một phiên gọi tự động với **File ghi âm**

```
{
   "name":"Chiến dịch giới thiệu sản phẩm mới",
   "speed" : 0
   "template_dialplans":[
      {
         "target_type":"Recording",
         "target":"5ed0c6dffb7b390007e5211"
      }
   ],
   "variables":[]
}
```

**Ví dụ** : Tham số một phiên gọi tự động với **Text To Speech**

```
{
   "name":"Thông báo đơn hàng",
   "template_dialplans":[
      {"target_type":"Text_variable"},
      {"target_type":"Text_variable"},
      {"target_type":"Text_variable"},
      {"target_type":"Text_variable"}
   ],
   "variables":[
      "Đơn hàng của bạn là",
      "HHKKK",
      "Tổng giá trị",
      "90000"
   ]
}
```

**Ví dụ** :Tham số một phiên gọi tự động **File ghi âm và Text To Speech**&#x20;

```
{
   "name":"Tên phiên gọi tự động",
   "template_dialplans":[
     {"target_type":"Text_variable"},
     {"target_type":"Text_variable"},
     {"target_type":"Text_variable"},
     {"target_type":"Text_variable"},
     { 
       "target_type":"Recording",   
       "target":"5e9eac95e44159000710f0xxx" 
    }],
   "variables" : [
      "Đơn hàng của bạn là",
      "HHKKK",
      "Tổng giá trị",
      "90000"
   ]
}
```

Ví dụ về phiên gọi tự động : **Kịch bản bấm phím**

```
{
   "name":"Tên phiên gọi tự động",
   "template_dialplans":[
     { 
       "target_type":"Ivr_menu",   
       // Id phiên bấm phím,
       // API : Tổng đài >> Danh sách kịch bản bấm phím
       "target":"5e9eac95e44159000710f0xxx"  
    }],
   "variables" : [
   ]
}
```

| Mã lỗi                   | Mô tả                                                                                                                                                    |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| limit\_service           | Giới hạn gói dịch vụ. Gói trải nghiệm không cho phép thực thi Auto Call                                                                                  |
| limit\_word              | <p>Vượt quá giới hạn từ trong 1 phiên hoặc tổng số từ trong ngày </p><p>(<strong>300 ký tự / phiên</strong> và <strong>3.000 ký tự / ngày</strong> )</p> |
| limit\_word\_session     | Vượt quá số lượng ký tự text to speech. Chỉ hỗ trợ 300 ký tự / 1 phiên                                                                                   |
| balance\_is\_not\_enough | Số dư không đủ để thực hiện                                                                                                                              |

