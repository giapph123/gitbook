# AI



{% swagger method="post" path="" baseUrl="https://tts-api-v1-stg.omicall.com/v1/tts" summary="API TTS (Text2Speech):" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="apikey" type="String" required="true" %}
Token xác thực truy cập API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="String" required="true" %}
Nội dung văn bản
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speed" type="Integer" %}
Tốc độ đọc là giá trị thực trong khoảng \[0.8, 1.2]. Mặc định là 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speaker_id" type="String" %}
ID giọng đọc mặc định là 'northern\_female\_ngocanh'.&#x20;



Danh sách ID các giọng đọc:&#x20;

northern\_female\_ngocanh

southern\_female\_honganh

southern\_male\_tienhuy

northern\_male\_anhkiet

southern\_female\_khangan
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% code overflow="wrap" %}
```
{
    "data": {
        "audioDuration": 1.55, // Thời lượng tính bằng giây của audio
        "sampleRate": 8000, // Tần số lấy mẫu 
        "url": "https://tts-api-v1-stg.omicall.com/v1/....." //URL download
    }
}
```
{% endcode %}
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="" baseUrl="https://asr-api-v1-stg.omicall.com/api/asr/register" summary="API ASR (Speech2Text): Đăng ký webhook url để nhận kết quả ASR" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="apikey" type="String" required="true" %}
Token xác thực để truy cập API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="String" required="true" %}
Đường dẫn nhận dữ liệu
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}

{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="" baseUrl="https://asr-api-v1-stg.omicall.com/api/asr/upload" summary="API ASR (Speech2Text): Upload audio, kết quả ASR sẽ được trả về webhook url " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="apikey" type="String" required="true" %}
Token xác thực để truy cập API
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="audio" type="String" %}
audio file (định dạng .wav) muốn chuyển sang text
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="String" required="true" %}
String (id sẽ được đính kèm trong kết quả trả về giúp phân biệt các kết quả)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}
{% endswagger %}
