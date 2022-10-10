---
description: API gọi tự động
---

# Gọi tự động

{% swagger baseUrl="[URL]" path="/api/auto_call/execute_by_phone?phone_number=" method="post" summary="Tạo phiên gọi tự động" %}
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
Tốc độ đọc, Giá trị từ  -3 - 3 : Mặc định là 0

\


\- 3 : Cực kì chậm

\


\-2 : Rất chậm

\


\-1 : Chậm

\


0 : Bình thường

\


1 : Nhanh

\


...
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
Cấu trúc phiên gọi tự động theo loại. 

\




_1. Phiên gọi tự động với file ghi âm_

\




`[{`

\


  

`"target_type" : "Recording",`

\


  

`"target":"5ed0c6dffb7b390007e111"`

\


`}]`

\


target

_: Là Id của file ghi âm được lấy từ  chức năng_

\




**Cấu hình >> Tổng đài >> File ghi âm**

\




\




_2. Phiên gọi tự động  với Text To Speech_

\




`[{`

\


   

`"target_type":"Text_variable"`

\


`}]`

\




\




_3. Phiên gọi tự động với file ghi âm và Text To Speech. Thực thi theo thứ tự_

 

\




`[{`

 

\


   

`"target_type":"Text_variable"`

 

\


 

`},`

 

\


 

`{`

 

\


    

`"target_type":"Recording",`

   

\


    

`"target":"5ed0c6dffb7b390007e5211"`

 

\


 

`}]`
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

| Mã lỗi                   | Mô tả                                                                                                                                              |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| limit\_service           | Giới hạn gói dịch vụ. Gói trải nghiệm không cho phép thực thi Auto Call                                                                            |
| limit\_word              | <p>Vượt quá giới hạn từ trong 1 phiên hoặc tổng số từ trong ngày </p><p>(<strong>300 từ / phiên</strong> và <strong>3.000 từ / ngày</strong> )</p> |
| balance\_is\_not\_enough | Số dư không đủ để thực hiện                                                                                                                        |

