---
description: API gọi tự động
---

# Gọi tự động

{% api-method method="post" host="\[URL\]" path="/api/auto\_call/execute\_by\_phone?phone\_number=" %}
{% api-method-summary %}
Tạo phiên gọi tự động
{% endapi-method-summary %}

{% api-method-description %}
Tạo phiên gọi tự động dựa trên cấu hình & thực thi
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-type" type="string" required=false %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token Bearer token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="speed" type="number" required=false %}
Tốc độ đọc, Giá trị từ  -3 - 3 : Mặc định là 0  
- 3 : Cực kì chậm  
-2 : Rất chậm  
-1 : Chậm  
0 : Bình thường  
1 : Nhanh  
...
{% endapi-method-parameter %}

{% api-method-parameter name="voice" type="string" required=false %}
Giọng đọc, có thể một trong các giá trị sau  
**banmai** : Giọng nữ miền Bắc  
**leminh** : Giọng nam miền Bắc  
**lannhi** : Giọng nữ miền Nam
{% endapi-method-parameter %}

{% api-method-parameter name="cid" type="string" required=false %}
Đầu số dùng để gọi tự động.   
_Nếu không truyền, mặc định ưu tiên gọi nội mạng_
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Tên của phiên gọi tự động
{% endapi-method-parameter %}

{% api-method-parameter name="template\_dialplans" type="array" required=true %}
Cấu trúc phiên gọi tự động theo loại.   
_1. Phiên gọi tự động với file ghi âm_  
`[{  
  "target_type" : "Recording",  
  "target":"5ed0c6dffb7b390007e111"  
}]`  
target_: Là Id của file ghi âm được lấy từ  chức năng_  
**Cấu hình &gt;&gt; Tổng đài &gt;&gt; File ghi âm**  
  
_2. Phiên gọi tự động  với Text To Speech_  
`[{  
   "target_type":"Text_variable"  
}]`  
  
_3. Phiên gọi tự động với file ghi âm và Text To Speech. Thực thi theo thứ tự_   
`[{   
   "target_type":"Text_variable"   
 },   
 {   
    "target_type":"Recording",     
    "target":"5ed0c6dffb7b390007e5211"   
 }]`
{% endapi-method-parameter %}

{% api-method-parameter name="variables" type="string" required=false %}
Mảng giá trị cho Text To Speech  
_Ví dụ_   
`[   
 "Đơn hàng của bạn là ",  
 "CKHDKD00203",  
 "Số tiền",  
 "900000",  
 "Đã được bàn giao cho đối tác vận chuyển"  
]`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Thông tin phiên gọi tự động
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "payload": {
        "autocall_id": "91d3e842-9da2-43ec-8bb1-979c17e817ad",
        "name": "Chiến dịch giới thiệu sản phẩm mới"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**Ví dụ** :Tham số một phiên gọi tự động với **File ghi âm**

```text
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

```text
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

**Ví dụ** :Tham số một phiên gọi tự động **File ghi âm và Text To Speech** 

```text
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

<table>
  <thead>
    <tr>
      <th style="text-align:left">M&#xE3; l&#x1ED7;i</th>
      <th style="text-align:left">M&#xF4; t&#x1EA3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">limit_service</td>
      <td style="text-align:left">Gi&#x1EDB;i h&#x1EA1;n g&#xF3;i d&#x1ECB;ch v&#x1EE5;. G&#xF3;i tr&#x1EA3;i
        nghi&#x1EC7;m kh&#xF4;ng cho ph&#xE9;p th&#x1EF1;c thi Auto Call</td>
    </tr>
    <tr>
      <td style="text-align:left">limit_word</td>
      <td style="text-align:left">
        <p>V&#x1B0;&#x1EE3;t qu&#xE1; gi&#x1EDB;i h&#x1EA1;n t&#x1EEB; trong 1 phi&#xEA;n
          ho&#x1EB7;c t&#x1ED5;ng s&#x1ED1; t&#x1EEB; trong ng&#xE0;y</p>
        <p>(<b>300 t&#x1EEB; / phi&#xEA;n</b> v&#xE0; <b>3.000 t&#x1EEB; / ng&#xE0;y</b> )</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">balance_is_not_enough</td>
      <td style="text-align:left">S&#x1ED1; d&#x1B0; kh&#xF4;ng &#x111;&#x1EE7; &#x111;&#x1EC3; th&#x1EF1;c
        hi&#x1EC7;n</td>
    </tr>
  </tbody>
</table>



