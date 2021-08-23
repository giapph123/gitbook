# Click To Call

API dùng để thực hiện **click-to-call**.

Sau khi thực hiện click-to-call, hệ thống sẽ gọi vào số extension của domain, sau khi extension pickup cuộc gọi thì có một cuộc gọi đẩy ra số mobile dựa vào parameter của API.

{% api-method method="post" host="\[URL\]" path="/api/click2call" %}
{% api-method-summary %}
Click To Call
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer 'Access Token'
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="extension" type="string" required=true %}
Số máy lẻ nhân viên thực hiện cuộc gọi
{% endapi-method-parameter %}

{% api-method-parameter name="hotline" type="string" required=true %}
Số Hotline \(Hay số SIP\)
{% endapi-method-parameter %}

{% api-method-parameter name="phone\_number" type="string" required=true %}
Số điện thoại gọi tới
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
    "instance_id": "stg",
    "instance_version": "1.2.163",
    "payload": {
        "call_uuid": "b4dae7fe-9d09-4491-918f-2b391fd5feef" // id cuộc gọi
    },
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

| ERROR CODE | DESCRIPTION |
| :--- | :--- |
| _data\_is\_required_ | Dữ liệu là bắt buộc |
| _tenant\_invalid_ | Doanh nghiệp không hợp lệ |
| _user\_not\_registered_ | Số máy lẻ không được ghi danh tổng đài |
| _number\_call\_out\_invalid_ | Số hotline gọi ra không hợp lệ hoặc không có |
| _extension\_invalid_ | Số máy lẻ không hợp lệ |

