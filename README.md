# GoSwiftgithub.io


```html
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>GoSwift | شركة الشحن الذكية</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #eef2f3;
      text-align: center;
      padding: 40px;
      color: #333;
    }
    h1 {
      color: #007acc;
    }
    .section {
      background: #fff;
      padding: 20px;
      margin: 20px auto;
      max-width: 600px;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    .btn {
      padding: 10px 20px;
      background: #007acc;
      color: #fff;
      border: none;
      border-radius: 5px;
      margin-top: 15px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>GoSwift</h1>
  <p>نوصلك بسرعة وأمان في كل مكان</p>

  <div class="section">
    <h2>خدماتنا</h2>
    <p>شحن محلي ودولي - تتبع مباشر - توصيل في نفس اليوم</p>
  </div>

  <div class="section">
    <h2>تواصل معنا</h2>
    <p>للطلبات والاستفسارات: 01012345678</p>
    <button class="btn">راسلنا الآن</button>
  </div>

</body>
</html>
```
:

```html
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>تتبع الشحنة - GoSwift</title>
  <style>
    body {
      font-family: Arial;
      padding: 30px;
      text-align: center;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin-top: 10px;
    }
    #result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>تتبع شحنتك</h2>
  <p>ادخل رقم التتبع:</p>
  <input type="text" id="trackingNumber" placeholder="مثال: GS12345">
  <br>
  <button onclick="track()">تتبع الآن</button>

  <div id="result"></div>

  <script>
    function track() {
      const number = document.getElementById("trackingNumber").value;
      let resultBox = document.getElementById("result");

      if (number === "GS12345") {
        resultBox.innerText = "الشحنة في الطريق – سيتم التوصيل خلال 24 ساعة.";
      } else if (number === "GS67890") {
        resultBox.innerText = "تم تسليم الشحنة بنجاح.";
      } else {
        resultBox.innerText = "رقم التتبع غير موجود. برجاء التأكد.";
      }
    }
  </script>

</body>
</html>
```
:

```html
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>نموذج تواصل معنا</title>
  <style>
    body {
      font-family: Arial;
      direction: rtl;
      padding: 20px;
      background-color: #f9f9f9;
    }
    form {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px #ccc;
    }
    input, textarea, button {
      width: 100%;
      margin-top: 10px;
      padding: 10px;
      font-size: 16px;
    }
    button {
      background-color: #004aad;
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: #003080;
    }
  </style>
</head>
<body>

  <form>
    <h2>تواصل معنا</h2>
    <label>الاسم:</label>
    <input type="text" placeholder="اكتب اسمك">

    <label>البريد الإلكتروني:</label>
    <input type="email" placeholder="example@email.com">

    <label>الرسالة:</label>
    <textarea rows="5" placeholder="اكتب رسالتك هنا..."></textarea>

    <button type="submit">إرسال</button>
  </form>

</body>
</html>
```


```sql
CREATE DATABASE goswift;

USE goswift;

CREATE TABLE messages (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  message TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

*2. ملف HTML (form.html):*
```html
<form action="save_message.php" method="POST">
  <input type="text" name="name" placeholder="الاسم" required>
  <input type="email" name="email" placeholder="البريد الإلكتروني" required>
  <textarea name="message" placeholder="اكتب رسالتك" required></textarea>
  <button type="submit">إرسال</button>
</form>
```

*3. ملف PHP لحفظ البيانات (save_message.php):*
```php
<?php
conn = new mysqli("localhost", "root", "", "goswift");

if (conn->connect_error) {
  die("فشل الاتصال: " . conn->connect_error);name = _POST['name'];email = _POST['email'];message = _POST['message'];sql = "INSERT INTO messages (name, email, message) VALUES ('name', 'email', 'message')";

if (conn->query(sql) === TRUE) 
  echo "تم إرسال الرسالة بنجاح!";
 else 
  echo "خطأ: " .sql . "<br>" . conn->error;conn->close();
?>
```


```php
<?php
conn = new mysqli("localhost", "root", "", "goswift");

if (conn->connect_error) {
  die("فشل الاتصال: " . conn->connect_error);name = _POST['name'];email = _POST['email'];message = _POST['message'];

// حفظ الرسالة في قاعدة البياناتsql = "INSERT INTO messages (name, email, message) VALUES ('name', 'email', 'message')";conn->query(sql);

// إرسال البريد الإلكترونيto = "yourcompany@email.com"; // غيرها لبريد شركتك
subject = "رسالة جديدة منname";
body = "الاسم:name\nالبريد الإلكتروني: email:message";
headers = "From:email";

if (mail(to,subject, body,headers)) {
  echo "تم إرسال الرسالة بنجاح!";
} else {
  echo "حدث خطأ أثناء إرسال البريد.";
}

$conn->close();
?>




