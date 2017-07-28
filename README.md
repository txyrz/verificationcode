<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Bulk Numbers for Receiving SMS</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="/static/bootstrap/css/bootstrap.min.css" rel="stylesheet" media="screen">
    <link href="/static/select2/select2.css" rel="stylesheet" media="screen">
  </head>
  <body>
    <div class="" style="margin: 10px 20px">
      <div>
        <h3>Basic Information of Your Order </h3>
        <hr>
        <div class="row">
          <ul>
            <li>App: Fully Functioning</li>
            <li>Count of numbers: 1/1</li>
            <li>Ordering time: 2017-01-03 05:03:58</li>
          </ul>
        </div>
      </div>
      <div>
        <h3 id="section-phones">Number List</h3>
        <hr>
        <table class="table table-bordered table-stripped" id="sms-table">
          <thead>
			<th>#</th>
            <th>Number</th>
            <th>Status</th>
            <th>Sender</th>
            <th>Content</th>
			      <th>Receiving Time</th>
          </thead>
          <tbody>
							<tr number="+19082917846">
					<td>1</td>
					<td>+19082917846</td>
					<td>SMS received</td>
					<td>+13143669444</td>
					<td>【阿里巴巴】您正在重置密码，验证码257603，请在15分钟内按页面提示提交验证 
码，切勿将验证码泄露于他人。
您的帐号  帮助中心
<https://support.google.com/voice#topic=1707989> 帮助论坛
<https://productforums.google.com/forum/#!forum/voice>
如要修改关于text messages的电子邮件偏好设置，请在您的帐号中转到电子邮件通知 
设置
<#voicemailsettings>。
Google Inc.
1600 Amphitheatre Pkwy
Mountain View CA 94043 USA</td>
					<td>2017-07-26 08:50:05</td>
				</tr>
			          </tbody>
        </table>
      </div>


    <script src="/static/jquery/jquery-1.11.1.min.js"></script>
    <script src="/static/site/common.js"></script>
    <script src="/static/select2/select2.min.js"></script>
    <script src="/static/bootstrap/js/bootstrap.min.js"></script>
    <script>
      $(document).ready(function() {
        setInterval(function() {
          $.get("/view-update?t=5ff2c868ccd6ec0be5dac2c27b33abfd2fb1f1da938d2775057a28bdcc0ece17", function (data) {
            data = eval(data);
            
            for (var i = 0, l = data.length; i < l; ++i) {
              var tds = $("tr[number$="+data[i][0].substr(1)+"] td");
              if ($(tds[4]).text() != data[i][2]) {
                $(tds[3]).text(data[i][1]);
                $(tds[4]).text(data[i][2]);
                $(tds[5]).text(data[i][3]);
              }
            }
          });
        }, 10000);
      });
    </script>
  </body>
</html>
