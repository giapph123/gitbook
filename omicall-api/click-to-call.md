# Click To Call

API dùng để thực hiện **click-to-call**.

Sau khi thực hiện click-to-call, hệ thống sẽ gọi vào số extension của domain, sau khi extension pickup cuộc gọi thì có một cuộc gọi đẩy ra số mobile dựa vào parameter của API.

{% swagger baseUrl="[URL]" path="/api/click2call" method="post" summary="Click To Call" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Bearer 'Access Token'
{% endswagger-parameter %}

{% swagger-parameter in="body" name="extension" type="string" %}
Số máy lẻ nhân viên thực hiện cuộc gọi
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hotline" type="string" %}
Số Hotline (Hay số SIP)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone_number" type="string" %}
Số điện thoại gọi tới
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "call_uuid": "b4dae7fe-9d09-4491-918f-2b391fd5feef" // id cuộc gọi
    },
    "key_enabled": false
}
```
{% endswagger-response %}
{% endswagger %}

| ERROR CODE                   | DESCRIPTION                                  |
| ---------------------------- | -------------------------------------------- |
| _data\_is\_required_         | Dữ liệu là bắt buộc                          |
| _tenant\_invalid_            | Doanh nghiệp không hợp lệ                    |
| _user\_not\_registered_      | Số máy lẻ không được ghi danh tổng đài       |
| _number\_call\_out\_invalid_ | Số hotline gọi ra không hợp lệ hoặc không có |
| _extension\_invalid_         | Số máy lẻ không hợp lệ                       |
