<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>打开邮箱应用</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script>
        function generateQRCode() {
            var qrCodeContainer = document.getElementById("qrcode");
            // 指向托管在公共网络上的页面链接，用户扫描后可以进行进一步操作
            var middlePageUrl = "https://yourdomain.com/yourpage.html"; // 替换为你托管文件的实际 URL
            new QRCode(qrCodeContainer, {
                text: middlePageUrl,
                width: 128,
                height: 128
            });
        }

        function openMailApp() {
            // 使用 JavaScript 尝试触发 mailto 链接
            window.location.href = "mailto:service@aqqapet.com?subject=Hello&body=请在这里填写您的内容";
        }
    </script>
</head>
<body onload="generateQRCode();">
    <h2>扫描二维码以打开 QQ 邮箱应用</h2>
    <div id="qrcode" style="margin-bottom: 20px;"></div>
    <button onclick="openMailApp()">点击这里以打开邮箱应用</button>
    <div id="backup-links">
        <h2>如果二维码无法打开应用，请选择以下方式打开邮箱</h2>
        <ul>
            <!-- 如果未安装 QQ 邮箱，则提供网页版链接 -->
            <li><a href="https://mail.qq.com/">打开 QQ 邮箱网页版</a></li>

            <!-- 其他邮箱应用 -->
            <li><a href="mailto:service@aqqapet.com?subject=Hello&body=请在这里填写您的内容">用默认邮件应用编写邮件</a></li>
        </ul>
    </div>
</body>
</html>
