---
description: >-
  API dùng để lấy access token thông qua API KEY được cung cấp. AcessToken là
  chuỗi mã hóa chứa thông tin của doanh nghiệp, có thời gian hết hạn là 24 giờ
---

# Xác thực

{% api-method method="get" host="\[URL\]" path="/api/auth?apiKey=" %}
{% api-method-summary %}
Get AccessToken
{% endapi-method-summary %}

{% api-method-description %}
Lấy Access Token thông qua API KEY
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="apiKey" type="string" required=true %}
API key của doanh nghiệp được cung cấp
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Khi yêu cầu API thành công
{% endapi-method-response-example-description %}

```
{
    "status_code": 9999,
    "instance_id": "stg",
    "instance_name": "cloud-vihat-saas-sync-public-api-77689c7b9c",
    "payload": {
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9 ...",
        "access_type" : "normal",
        "token_type": "Bearer"
    },
    "key_enabled": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**Thông tin kết quả trả về payload**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Tham s&#x1ED1;</th>
      <th style="text-align:left">M&#xF4; t&#x1EA3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">access_token</td>
      <td style="text-align:left">Access token truy c&#x1EAD;p</td>
    </tr>
    <tr>
      <td style="text-align:left">access_type</td>
      <td style="text-align:left">
        <p>C&#xF3; 2 lo&#x1EA1;i</p>
        <ul>
          <li><b>normal </b>: Doanh nghi&#x1EC7;p ng&#x1B0;&#x1EDD;i d&#xF9;ng cu&#x1ED1;i</li>
          <li><b>bussiness </b>: Doanh nghi&#x1EC7;p l&#xE0; &#x111;&#x1ED1;i t&#xE1;c
            c&#x1EE7;a OMICALL</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">token_type</td>
      <td style="text-align:left">Bearer</td>
    </tr>
  </tbody>
</table>

