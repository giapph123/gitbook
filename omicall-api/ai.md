# AI



{% swagger method="post" path="" baseUrl="https://tts-api-v1-stg.omicall.com/v1/tts" summary="API TTS (Text2Speech):" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="apikey" type="String" required="true" %}
Token key
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="String" required="true" %}
Nội dung văn bản
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speed" type="Integer" %}
Tốc độ đọc là giá trị thực trong khoảng \[0.8, 1.2]. Mặc định là 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speaker_id" type="String" %}
ID giọng đọc mặc định là 'northern\_female\_ngocanh'.&#x20;



Danh sách ID các giọng đọc: 'northern\_female\_ngocanh', 'southern\_female\_honganh', 'southern\_male\_tienhuy', 'northern\_male\_anhkiet', 'southern\_female\_khangan'
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}
{% endswagger %}
