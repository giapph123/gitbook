---
description: >-
  OmiCall Web SDK : là công cụ bao gồm thư viện, và tài liệu mà OmiCall cung cấp
  cho đối tác, để đối tác xây dựng tính năng call ngay chính trên ứng dụng web
  của mình.
---

# Web SDK

```markup
Version : 2.0.0
Release date : 15/07/2021 22:00
Changelog : https://api.omicall.com/chang-log#26-05-2021
```

### Hướng dẫn cài đặt

![Giao di&#x1EC7;n Dialog Call](../.gitbook/assets/sdk1.png)

Nhúng web-sdk vào trang HTML của mình



```markup
<!-- import omisdk -->
<script omi-sdk type="text/javascript" src="https://cdn.omicrm.com/sdk/2.0.0/sdk.min.js"></script>
<script>
    document.addEventListener('DOMContentLoaded', () => {
			let config = {
				theme: 'default', // themes mặc định của dialog
				language: 'vi', // Ngôn ngữ giao diện dialog,
				ringtoneVolume: 0.5, // âm lượng từ 0 - 1
				options: {
					hideCallButton: false, // true/false : Ẩn hiện cửa số nhập số
				},
				callbacks: {
					register: (data) => { // Sự kiện xảy ra khi ghi danh tổng đài
						// console.log('register:', data);
					},
					connecting: (data) => { // Sự kiện xảy ra khi bắt đầu thực hiện cuộc gọi ra
						// console.log('connecting:', data);
					},
					ringing: (data) => { // Sự kiện xảy ra khi bắt đầu rung chuông
						// console.log('ringing:', data);
					},
					invite: (data) => { // Sự kiện xảy ra khi có một cuộc gọi tới
						// console.log('invite:', data);
					},
					inviteRejected: (data) => { // Sự kiện xảy ra khi có một cuộc gọi tới
						// console.log('inviteRejected:', data);
					},
					incall: (data) => { // Sự kiện xảy ra sau khi cuộc gọi đã được kết nối mỗi 1 giây
						// console.log('incall:', data);
					},
					accepted: (data) => { // Sự kiện xảy ra khi cuộc gọi được chấp nhận
						// console.log('accepted:', data);
					},
					acceptedByOther: (data) => { // Sự kiện xảy ra khi cuộc gọi hiện tại được nghe máy ở thiết bị khác
						// 	console.log('acceptedByOther:', data);
					},
					ended: (data) => { // Sự kiện xảy ra khi cuộc gọi kết thúc
						// console.log('ended:', data);
					},
					holdChanged: (status) => { // Sự kiện xảy ra khi cuộc gọi đang được giữ
						// console.log('on hold:', status);
					},
				}
			};
			// Khởi tạo SDK
			omiSDK.init(config, () => {
				
				// Ghi danh tổng đài
				// Truy cập OMI: Cấu hình >> Tổng đài >> Số nội bộ
				omiSDK.register({
					domain: '', // Domain tổng đài
					username: '', // Số máy lẻ nhân viên
					password: '' // Mật khẩu số máy lẻ
				});
				
			});
		});
</script>
```

{% file src="../.gitbook/assets/index \(3\).html" caption="Ví dụ tích hợp" %}

**Thuộc tính và Sự kiện**

<table>
  <thead>
    <tr>
      <th style="text-align:right">Tham s&#x1ED1;</th>
      <th style="text-align:left">Ki&#x1EC3;u</th>
      <th style="text-align:left">M&#xF4; t&#x1EA3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:right">config.<b>theme</b>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>Giao di&#x1EC7;n dialog cu&#x1ED9;c g&#x1ECD;i (n&#x1EBF;u &#x111;&#x1EC3;
          tr&#x1ED1;ng th&#xEC; s&#x1EBD; kh&#xF4;ng c&#xF3; giao di&#x1EC7;n). Ho&#x1EB7;c
          m&#x1ED9;t trong c&#xE1;c gi&#xE1; tr&#x1ECB; sau</p>
        <ul>
          <li><b>default </b>: Giao di&#x1EC7;n (nh&#x1B0; &#x1EA3;nh &#x1EDF; tr&#xEA;n)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>language</b>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Ng&#xF4;n ng&#x1EEF; hi&#x1EC3;n th&#x1ECB; dialog cu&#x1ED9;c g&#x1ECD;i.
        G&#x1ED3;m
        <br />&quot;<b>vi</b>&quot; : Ti&#x1EBF;ng Vi&#x1EC7;t,
        <br />&quot;<b>en</b>&quot; : Ti&#x1EBF;ng anh</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>options</b>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left"><em><code>hideCallButton </code></em><code>: true/false</code> : &#x1EA8;n
        hi&#x1EC7;n n&#xFA;t g&#x1ECD;i</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>ringtoneVolume</b>
      </td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">&#xC2;m l&#x1B0;&#x1EE3;ng chu&#xF4;ng, khi kh&#xE1;ch g&#x1ECD;i t&#x1EDB;i
        (t&#x1EEB; 0 - 1)</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>register</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi ghi danh t&#x1ED5;ng &#x111;&#xE0;i
        th&#xE0;nh c&#xF4;ng ho&#x1EB7;c th&#x1EA5;t b&#x1EA1;i</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>connecting</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi b&#x1EAF;t &#x111;&#x1EA7;u th&#x1EF1;c
        hi&#x1EC7;n cu&#x1ED9;c g&#x1ECD;i ra</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>ringing</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi b&#x1EAF;t &#x111;&#x1EA7;u rung
        chu&#xF4;ng</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>invite</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi cu&#x1ED9;c g&#x1ECD;i &#x111;&#x1B0;&#x1EE3;c
        ch&#x1EA5;p nh&#x1EAD;n</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>inviteRejected</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi c&#xF3; m&#x1ED9;t cu&#x1ED9;c
        g&#x1ECD;i t&#x1EDB;i</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>incall</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra sau khi cu&#x1ED9;c g&#x1ECD;i &#x111;&#xE3;
        &#x111;&#x1B0;&#x1EE3;c k&#x1EBF;t n&#x1ED1;i m&#x1ED7;i 1 gi&#xE2;y</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>accepted</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi cu&#x1ED9;c g&#x1ECD;i &#x111;&#x1B0;&#x1EE3;c
        ch&#x1EA5;p nh&#x1EAD;n</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>acceptedByOther</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi cu&#x1ED9;c g&#x1ECD;i hi&#x1EC7;n
        t&#x1EA1;i &#x111;&#x1B0;&#x1EE3;c nghe m&#xE1;y &#x1EDF; thi&#x1EBF;t
        b&#x1ECB; kh&#xE1;c</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>ended</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi cu&#x1ED9;c g&#x1ECD;i k&#x1EBF;t
        th&#xFA;c</td>
    </tr>
    <tr>
      <td style="text-align:right">config.<b>holdChanged</b>
      </td>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">S&#x1EF1; ki&#x1EC7;n x&#x1EA3;y ra khi cu&#x1ED9;c g&#x1ECD;i &#x111;ang
        &#x111;&#x1B0;&#x1EE3;c gi&#x1EEF;</td>
    </tr>
  </tbody>
</table>

Dữ liệu data callback từ sự kiện

| Tham số | Loại | Mô tả |
| :--- | :--- | :--- |
| **event\_name** | String | Tên sự kiện |
| **direction** | String | Hướng gọi : inbound, outboud, local |
| **transaction\_id** | String | Id cuộc gọi |
| **phone** | String | Số điện thoại khách hàng gọi đi hoặc gọi đến |
| **start\_time** | Number | Thời gian bắt đầu gọi |
| **start\_time\_to\_answer** | Number | Thời gian bắt đầu trả lời |
| **end\_time** | Number | Thời gian kết thúc |
| **getDuration** | Function | Thời gian tính từ khi gọi, đến khi kết thúc cuộc gọi |
| **getBillSec** | Function | Số giây tính tiền |

**Phương thức**

<table>
  <thead>
    <tr>
      <th style="text-align:right">Ph&#x1B0;&#x1A1;ng th&#x1EE9;c</th>
      <th style="text-align:left">M&#xF4; t&#x1EA3;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:right">omiSDK<b>.init(config,callback)</b>
      </td>
      <td style="text-align:left">Kh&#x1EDF;i t&#x1EA1;o SDK.</td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>register(params)</b>
      </td>
      <td style="text-align:left">
        <p>Ph&#x1B0;&#x1A1;ng th&#x1EE9;c ghi danh t&#x1ED5;ng &#x111;&#xE0;i</p>
        <p><code>var params = {<br />  domain : &quot;testcompany&quot; //domain c&#xF4;ng ty</code>
        </p>
        <p><code>  username: &quot;142&quot;, //S&#x1ED1; n&#x1ED9;i b&#x1ED9; c&#x1EE7;a nh&#xE2;n vi&#xEA;n</code>
        </p>
        <p><code>  password: &quot;&lt;mk&gt;&quot; // M&#x1EAD;t kh&#x1EA9;u s&#x1ED1; n&#x1ED9;i b&#x1ED9;</code>
        </p>
        <p><code>}</code>
        </p>
        <p>C&#xF3; th&#x1EC3; l&#x1EA5;y th&#xF4;ng tin danh s&#xE1;ch nh&#xE2;n
          vi&#xEA;n v&#xE0; s&#x1ED1; n&#x1ED9;i b&#x1ED9; th&#xF4;ng qua Api</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>makeCall(phone) </b>
      </td>
      <td style="text-align:left">
        <p>S&#x1ED1; c&#x1EA7;n g&#x1ECD;i t&#x1EDB;i</p>
        <ul>
          <li>S&#x1ED1; &#x111;i&#x1EC7;n tho&#x1EA1;i kh&#xE1;ch h&#xE0;ng</li>
          <li>S&#x1ED1; n&#x1ED9;i b&#x1ED9; c&#x1EE7;a nh&#xE2;n vi&#xEA;n</li>
          <li>S&#x1ED1; n&#x1ED9;i b&#x1ED9; c&#x1EE7;a nh&#xF3;m</li>
          <li>S&#x1ED1; n&#x1ED9;i b&#x1ED9; c&#x1EE7;a nh&#xF3;m b&#xEA;n ngo&#xE0;i</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>stopCall</b>()</td>
      <td style="text-align:left">K&#x1EBF;t th&#xFA;c cu&#x1ED9;c g&#x1ECD;i</td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>acceptCall</b>()</td>
      <td style="text-align:left">Ch&#x1EA5;p nh&#x1EAD;n cu&#x1ED9;c g&#x1ECD;i</td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>reregister</b>()</td>
      <td style="text-align:left">K&#x1EBF;t n&#x1ED1;i tr&#x1EDF; l&#x1EA1;i t&#x1ED5;ng &#x111;&#xE0;i</td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>transferCall(extension)</b>
      </td>
      <td style="text-align:left">
        <p>Chuy&#x1EC3;n ti&#x1EBF;p cu&#x1ED9;c g&#x1ECD;i.</p>
        <ul>
          <li><b>extension</b> : L&#xE0; s&#x1ED1; m&#xE1;y l&#x1EBB; nh&#xE2;n vi&#xEA;n
            c&#x1EA7;n chuy&#x1EC3;n t&#x1EDB;i</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>unregister</b>()</td>
      <td style="text-align:left">Ng&#x1EAF;t k&#x1EBF;t n&#x1ED1;i t&#x1ED5;ng &#x111;&#xE0;i</td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>rejectCall()</b>
      </td>
      <td style="text-align:left">T&#x1EEB; ch&#x1ED1;i cu&#x1ED9;c g&#x1ECD;i (trong tr&#x1B0;&#x1EDD;ng
        h&#x1EE3;p kh&#xF4;ng mu&#x1ED1;n nh&#x1EAD;n)</td>
    </tr>
    <tr>
      <td style="text-align:right">omiSDK.<b>updateContactInfo</b>(Object)</td>
      <td style="text-align:left">
        <p>C&#x1EAD;p nh&#x1EAD;t T&#xEA;n v&#xE0; Avatar c&#x1EE7;a kh&#xE1;ch h&#xE0;ng
          tr&#xEA;n c&#x1EED;a s&#x1ED1; cu&#x1ED9;c g&#x1ECD;i</p>
        <p><em>omiSDK.<b>updateContactInfo</b>({</em>
        </p>
        <p><em>name : &quot;Nguy&#x1EC5;n Thanh Sang&quot;,</em>
        </p>
        <p><em>avatar : &quot;https://....&quot;</em>
        </p>
        <p><em>})</em>
        </p>
      </td>
    </tr>
  </tbody>
</table>



