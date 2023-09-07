# API tiêu chí kịch bản

#### API : Ưu tiên nhân viên quản lý khách hàng

OMICall hỗ trợ gọi API chủ động sang bên đối tác CRM, CMS, ERP ... đế lấy thông tin người phụ trách khách hàng theo số điện thoại , khi doanh nghiệp không muốn lưu trữ KH ở OMI

Đối tác cần chuẩn bị API theo yêu cầu sau

1. API dạng GET
2. Chứng thực bằng dạng KEY Header (X-API-KEY)
3. Response là dạng Text với format : 101:102:104 (Trong đó các giá trị là số máy lẻ (extension) của nhân viên
4. Trường hợp không có người phụ trách : Trả về empty, hệ thống sẽ tự chuyển vào kịch bản tiếp theo
5. Timeout request chỉ cho phép là 3s&#x20;

{% swagger method="get" path="get_ower_contact_by_phone?phoneNumber=?" baseUrl="https://demo.crm.com.vn/" summary="API lấy người phụ trách theo số điện thoại" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="phoneNumber" type="String" required="true" %}
Số điện thoại KH gọi vào
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="100:102" %}

{% endswagger-response %}
{% endswagger %}
