<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shop Mod & Acc - Đăng Nhập & Đăng Ký</title>
    
    <!-- Phông chữ cơ bản: Roboto (Google Fonts) - đơn giản, hiện đại như các web lớn -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <!-- Icon Font Awesome cho icon (mắt mật khẩu, social, v.v.) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Sign-In API (thêm login bằng Google) -->
    <meta name="google-signin-client_id" content="YOUR_CLIENT_ID.apps.googleusercontent.com"> <!-- Thay YOUR_CLIENT_ID bằng Client ID thật từ Google Console -->
    <script src="https://apis.google.com/js/platform.js" async defer></script>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', sans-serif;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: url('https://source.unsplash.com/random/1920x1080/?mountain,sunset') no-repeat center center/cover; /* Nền ảnh núi hoàng hôn giống ảnh */
            color: #fff;
            overflow: hidden;
            position: relative;
        }

        /* Overlay mờ để tăng độ tương phản cho form */
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.4); /* Overlay tối */
            z-index: -1;
        }

        /* Hiệu ứng glassmorphism cho container giống ảnh */
        .container {
            background: rgba(255, 255, 255, 0.1); /* Kính mờ */
            backdrop-filter: blur(15px);
            border-radius: 15px;
            padding: 40px;
            width: 400px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            text-align: center;
            animation: fadeIn 1s ease-out;
            position: relative;
            z-index: 1;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Header tiêu đề "Login" giống ảnh */
        .header {
            margin-bottom: 30px;
        }

        .title {
            font-size: 32px;
            font-weight: 500;
            color: #fff;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
        }

        /* Input fields giống ảnh: placeholder trắng, border dưới */
        .input-group {
            position: relative;
            margin-bottom: 20px;
            text-align: left;
        }

        .input-group label {
            display: block;
            font-size: 14px;
            color: #ddd;
            margin-bottom: 8px;
            font-weight: 300;
        }

        .input-group input {
            width: 100%;
            padding: 12px 15px;
            background: transparent;
            border: none;
            border-bottom: 1px solid rgba(255, 255, 255, 0.5);
            color: #fff;
            font-size: 16px;
            transition: border-bottom 0.3s;
        }

        .input-group input:focus {
            border-bottom: 1px solid #fff;
            outline: none;
        }

        .input-group input::placeholder {
            color: #ccc;
            font-weight: 300;
        }

        /* Icon mắt cho password (chi tiết thêm) */
        .password-group .password-toggle {
            position: absolute;
            right: 0;
            top: 40px;
            color: #ccc;
            cursor: pointer;
            font-size: 16px;
            transition: color 0.3s;
        }

        .password-group .password-toggle:hover {
            color: #fff;
        }

        /* Remember me và forgot password giống ảnh */
        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            font-size: 14px;
            color: #ddd;
        }

        .options label {
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .options input[type="checkbox"] {
            margin-right: 8px;
            accent-color: #fff;
        }

        .forgot-password {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }

        .forgot-password:hover {
            color: #fff;
            text-decoration: underline;
        }

        /* Button Log In giống ảnh: trắng, border radius */
        .btn-login {
            width: 100%;
            padding: 12px;
            background: #fff;
            border: none;
            border-radius: 25px;
            color: #333;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            transition: background 0.3s, transform 0.3s;
            margin-bottom: 20px;
        }

        .btn-login:hover {
            background: #eee;
            transform: translateY(-2px);
        }

        /* Link register giống ảnh */
        .register-link {
            font-size: 14px;
            color: #ddd;
        }

        .register-link a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .register-link a:hover {
            color: #ccc;
            text-decoration: underline;
        }

        /* Thêm login bằng Google (như yêu cầu) */
        .social-login {
            margin-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            padding-top: 20px;
        }

        .social-title {
            font-size: 14px;
            color: #ddd;
            margin-bottom: 15px;
        }

        .btn-google {
            width: 100%;
            padding: 12px;
            background: #4285F4;
            border: none;
            border-radius: 25px;
            color: #fff;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: background 0.3s;
        }

        .btn-google:hover {
            background: #357ae8;
        }

        .btn-google i {
            font-size: 18px;
        }

        /* Alert cho validation/error (siêu chi tiết) */
        .alert {
            background: rgba(255, 0, 0, 0.3);
            border-radius: 8px;
            padding: 10px;
            margin-bottom: 15px;
            font-size: 14px;
            display: none;
            text-align: left;
            animation: fadeInAlert 0.5s;
        }

        @keyframes fadeInAlert {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Footer với terms, privacy (chi tiết như web lớn) */
        .footer {
            margin-top: 30px;
            font-size: 12px;
            color: #aaa;
            text-align: center;
        }

        .footer a {
            color: #ccc;
            text-decoration: none;
            margin: 0 5px;
            transition: color 0.3s;
        }

        .footer a:hover {
            color: #fff;
        }

        /* Responsive cho mobile (chi tiết) */
        @media (max-width: 480px) {
            .container {
                width: 90%;
                padding: 30px 20px;
            }

            .title {
                font-size: 28px;
            }
        }
    </style>
</head>
<body>

    <!-- Container chính giống ảnh -->
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1 class="title">Login</h1>
        </div>

        <!-- Alert hiển thị lỗi -->
        <div id="alert-message" class="alert"></div>

        <!-- Form Đăng nhập -->
        <form id="login-form">
            <div class="input-group">
                <input type="email" id="email" placeholder="Enter your email" required>
            </div>
            <div class="input-group password-group">
                <input type="password" id="password" placeholder="Enter your password" required>
                <i class="fas fa-eye-slash password-toggle" onclick="togglePassword('password', this)"></i>
            </div>
            <div class="options">
                <label>
                    <input type="checkbox" checked>
                    Remember me
                </label>
                <a href="#" class="forgot-password">Forgot password?</a>
            </div>
            <button type="button" class="btn-login" onclick="handleLogin()">Log In</button>
        </form>

        <!-- Link register -->
        <div class="register-link">
            Don't have an account? <a href="#" onclick="showRegisterForm()">Register</a>
        </div>

        <!-- Login bằng Google -->
        <div class="social-login">
            <div class="social-title">Or log in with</div>
            <button class="btn-google" onclick="handleGoogleLogin()">
                <i class="fab fa-google"></i> Google
            </button>
        </div>

        <!-- Form Đăng ký (ẩn ban đầu, chi tiết hơn) -->
        <form id="register-form" style="display: none;">
            <div class="input-group">
                <input type="text" id="reg-username" placeholder="Enter your username" required>
            </div>
            <div class="input-group">
                <input type="email" id="reg-email" placeholder="Enter your email" required>
            </div>
            <div class="input-group password-group">
                <input type="password" id="reg-password" placeholder="Enter your password" required>
                <i class="fas fa-eye-slash password-toggle" onclick="togglePassword('reg-password', this)"></i>
            </div>
            <div class="input-group password-group">
                <input type="password" id="reg-confirm" placeholder="Confirm your password" required>
                <i class="fas fa-eye-slash password-toggle" onclick="togglePassword('reg-confirm', this)"></i>
            </div>
            <div class="options">
                <label>
                    <input type="checkbox" required>
                    I agree to the <a href="#">terms and conditions</a>
                </label>
            </div>
            <button type="button" class="btn-login" onclick="handleRegister()">Register</button>
            <div class="register-link">
                Already have an account? <a href="#" onclick="showLoginForm()">Log in</a>
            </div>
        </form>

        <!-- Footer -->
        <div class="footer">
            <a href="#">Privacy Policy</a> | <a href="#">Terms of Service</a> | <a href="#">Contact Us</a> | <a href="#">FAQ</a>
        </div>
    </div>

    <script>
        // Toggle password visibility (chi tiết)
        function togglePassword(id, icon) {
            const input = document.getElementById(id);
            if (input.type === 'password') {
                input.type = 'text';
                icon.classList.replace('fa-eye-slash', 'fa-eye');
            } else {
                input.type = 'password';
                icon.classList.replace('fa-eye', 'fa-eye-slash');
            }
        }

        // Chuyển form (animation mượt)
        function showRegisterForm() {
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('register-form').style.display = 'block';
            document.querySelector('.title').textContent = 'Register';
            clearAlert();
        }

        function showLoginForm() {
            document.getElementById('register-form').style.display = 'none';
            document.getElementById('login-form').style.display = 'block';
            document.querySelector('.title').textContent = 'Login';
            clearAlert();
        }

        // Xử lý login (validation chi tiết)
        function handleLogin() {
            const email = document.getElementById('email').value.trim();
            const password = document.getElementById('password').value;

            if (!email) {
                showAlert('Please enter your email!');
                return;
            }
            if (!/\S+@\S+\.\S+/.test(email)) {
                showAlert('Invalid email format!');
                return;
            }
            if (!password) {
                showAlert('Please enter your password!');
                return;
            }
            if (password.length < 6) {
                showAlert('Password must be at least 6 characters!');
                return;
            }

            // Demo login success
            alert('Login successful! Redirecting to dashboard...');
            // Thực tế: gửi form đến server
        }

        // Xử lý register (validation siêu chi tiết)
        function handleRegister() {
            const username = document.getElementById('reg-username').value.trim();
            const email = document.getElementById('reg-email').value.trim();
            const password = document.getElementById('reg-password').value;
            const confirm = document.getElementById('reg-confirm').value;

            if (!username) {
                showAlert('Please enter your username!');
                return;
            }
            if (username.length < 4 || username.length > 20) {
                showAlert('Username must be 4-20 characters!');
                return;
            }
            if (!/^[a-zA-Z0-9_]+$/.test(username)) {
                showAlert('Username can only contain letters, numbers, and underscores!');
                return;
            }
            if (!email) {
                showAlert('Please enter your email!');
                return;
            }
            if (!/\S+@\S+\.\S+/.test(email)) {
                showAlert('Invalid email format!');
                return;
            }
            if (!password) {
                showAlert('Please enter your password!');
                return;
            }
            if (password.length < 8) {
                showAlert('Password must be at least 8 characters!');
                return;
            }
            if (!/[A-Z]/.test(password)) {
                showAlert('Password must contain at least one uppercase letter!');
                return;
            }
            if (!/[0-9]/.test(password)) {
                showAlert('Password must contain at least one number!');
                return;
            }
            if (password !== confirm) {
                showAlert('Passwords do not match!');
                return;
            }

            // Demo register success
            alert('Registration successful! Redirecting to login...');
            showLoginForm();
            // Thực tế: gửi form đến server
        }

        // Xử lý login bằng Google
        function handleGoogleLogin() {
            // Demo: Thực tế tích hợp Google API
            alert('Logging in with Google... (Demo: Please configure Google Client ID for real integration)');
            // Sử dụng gapi.auth2.signIn() cho thực tế
        }

        // Hiển thị alert
        function showAlert(message) {
            const alert = document.getElementById('alert-message');
            alert.textContent = message;
            alert.style.display = 'block';
        }

        function clearAlert() {
            document.getElementById('alert-message').style.display = 'none';
        }
    </script>
</body>
</html>
