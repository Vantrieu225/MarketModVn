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
            background: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%); /* Gradient tối cho shop game, như Steam/Epic */
            color: #fff;
            overflow: hidden;
        }

        /* Hiệu ứng background động (như sao hoặc particle nhẹ cho game feel) */
        #background-particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .container {
            background: rgba(255, 255, 255, 0.05); /* Glassmorphism mờ đục tinh tế */
            backdrop-filter: blur(15px);
            border-radius: 15px;
            padding: 40px;
            width: 420px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            text-align: center;
            animation: fadeIn 0.8s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Header với logo và tiêu đề (như web lớn) */
        .header {
            margin-bottom: 30px;
        }

        .logo {
            font-size: 32px;
            font-weight: 700;
            color: #00bfff; /* Màu xanh neon cho game */
            text-shadow: 0 0 10px rgba(0, 191, 255, 0.5);
            margin-bottom: 10px;
        }

        .subtitle {
            font-size: 14px;
            color: #a0a0a0;
            font-weight: 300;
        }

        /* Form chung */
        form {
            display: flex;
            flex-direction: column;
        }

        .input-group {
            position: relative;
            margin-bottom: 20px;
        }

        .input-group input {
            width: 100%;
            padding: 12px 45px 12px 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 8px;
            color: #fff;
            font-size: 16px;
            transition: border 0.3s, background 0.3s;
        }

        .input-group input:focus {
            border: 1px solid #00bfff;
            background: rgba(255, 255, 255, 0.15);
            outline: none;
        }

        .input-group input::placeholder {
            color: #ccc;
            font-weight: 300;
        }

        .input-icon {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: #a0a0a0;
            font-size: 16px;
        }

        .password-toggle {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: #a0a0a0;
            cursor: pointer;
            font-size: 16px;
            transition: color 0.3s;
        }

        .password-toggle:hover {
            color: #fff;
        }

        /* Checkbox remember me (chi tiết như web lớn) */
        .remember-me {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 20px;
            font-size: 14px;
            color: #ccc;
        }

        .remember-me label {
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .remember-me input {
            margin-right: 8px;
            accent-color: #00bfff;
        }

        .forgot-password {
            color: #00bfff;
            text-decoration: none;
            transition: color 0.3s;
        }

        .forgot-password:hover {
            color: #fff;
        }

        /* Nút login (đẹp, với hover effect) */
        .btn-primary {
            background: linear-gradient(45deg, #00bfff, #1e90ff);
            border: none;
            border-radius: 8px;
            padding: 12px;
            color: #fff;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
            margin-bottom: 20px;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 191, 255, 0.4);
        }

        /* Social login (như Epic/Steam) */
        .social-login {
            margin: 20px 0;
            position: relative;
            text-align: center;
        }

        .social-login::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            height: 1px;
            background: rgba(255, 255, 255, 0.2);
        }

        .social-login span {
            background: #0f2027;
            padding: 0 10px;
            position: relative;
            color: #a0a0a0;
            font-size: 14px;
        }

        .social-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 15px;
        }

        .social-btn {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 8px;
            padding: 10px 20px;
            color: #fff;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: background 0.3s, border 0.3s;
            font-size: 14px;
        }

        .social-btn:hover {
            background: rgba(255, 255, 255, 0.15);
            border: 1px solid #00bfff;
        }

        .social-btn i {
            font-size: 18px;
        }

        /* Link chuyển sang register */
        .switch-form {
            font-size: 14px;
            color: #ccc;
        }

        .switch-form a {
            color: #00bfff;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .switch-form a:hover {
            color: #fff;
        }

        /* Footer (như web lớn: privacy, terms) */
        .footer {
            margin-top: 30px;
            font-size: 12px;
            color: #a0a0a0;
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

        /* Alert cho lỗi/validation (siêu chi tiết) */
        .alert {
            background: rgba(255, 0, 0, 0.2);
            border-radius: 8px;
            padding: 10px;
            margin-bottom: 20px;
            font-size: 14px;
            display: none;
            animation: shake 0.3s;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }

        /* Responsive cho mobile */
        @media (max-width: 480px) {
            .container {
                width: 90%;
                padding: 30px;
            }
        }
    </style>
</head>
<body>

    <!-- Background particles cho hiệu ứng đẹp (như game) -->
    <canvas id="background-particles"></canvas>

    <!-- Container chính -->
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="logo">MarketModVn</div>
            <div class="subtitle">Buôn bán acc, mod, hack game hot nhất</div>
        </div>

        <!-- Alert hiển thị lỗi -->
        <div id="alert-message" class="alert"></div>

        <!-- Form Đăng nhập (mặc định hiển thị) -->
        <form id="login-form">
            <div class="input-group">
                <i class="fas fa-user input-icon"></i>
                <input type="text" id="login-username" placeholder="Tên đăng nhập hoặc Email" required>
            </div>
            <div class="input-group">
                <i class="fas fa-lock input-icon"></i>
                <input type="password" id="login-password" placeholder="Mật khẩu" required>
                <i class="fas fa-eye-slash password-toggle" onclick="togglePassword('login-password', this)"></i>
            </div>
            <div class="remember-me">
                <label>
                    <input type="checkbox" checked>
                    Nhớ đăng nhập
                </label>
                <a href="#" class="forgot-password">Quên mật khẩu?</a>
            </div>
            <button type="button" class="btn-primary" onclick="handleLogin()">Đăng Nhập</button>
        </form>

        <!-- Social login -->
        <div class="social-login">
            <span>Hoặc đăng nhập với</span>
        </div>
        <div class="social-buttons">
            <a href="#" class="social-btn"><i class="fab fa-google"></i> Google</a>
            <a href="#" class="social-btn"><i class="fab fa-facebook-f"></i> Facebook</a>
            <a href="#" class="social-btn"><i class="fab fa-apple"></i> Apple</a>
        </div>

        <!-- Chuyển sang đăng ký -->
        <div class="switch-form">
            Chưa có tài khoản? <a href="#" onclick="showRegisterForm()">Đăng ký ngay</a>
        </div>

        <!-- Form Đăng ký (ẩn ban đầu) -->
        <form id="register-form" style="display: none;">
            <div class="input-group">
                <i class="fas fa-user input-icon"></i>
                <input type="text" id="reg-username" placeholder="Tên đăng nhập (4-20 ký tự)" required>
            </div>
            <div class="input-group">
                <i class="fas fa-envelope input-icon"></i>
                <input type="email" id="reg-email" placeholder="Email" required>
            </div>
            <div class="input-group">
                <i class="fas fa-lock input-icon"></i>
                <input type="password" id="reg-password" placeholder="Mật khẩu (ít nhất 8 ký tự)" required>
                <i class="fas fa-eye-slash password-toggle" onclick="togglePassword('reg-password', this)"></i>
            </div>
            <div class="input-group">
                <i class="fas fa-lock input-icon"></i>
                <input type="password" id="reg-confirm" placeholder="Xác nhận mật khẩu" required>
                <i class="fas fa-eye-slash password-toggle" onclick="togglePassword('reg-confirm', this)"></i>
            </div>
            <button type="button" class="btn-primary" onclick="handleRegister()">Đăng Ký</button>
            <div class="switch-form">
                Đã có tài khoản? <a href="#" onclick="showLoginForm()">Đăng nhập</a>
            </div>
        </form>

        <!-- Footer -->
        <div class="footer">
            <a href="#">Chính sách bảo mật</a> |
            <a href="#">Điều khoản dịch vụ</a> |
            <a href="#">Hỗ trợ</a> |
            <a href="#">Liên hệ</a>
        </div>
    </div>

    <script>
        // Hiệu ứng background particles (siêu đẹp, nhẹ)
        const canvas = document.getElementById('background-particles');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let particles = [];
        for (let i = 0; i < 50; i++) {
            particles.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                radius: Math.random() * 2 + 1,
                speed: Math.random() * 0.5 + 0.1
            });
        }

        function drawParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                ctx.beginPath();
                ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
                ctx.fillStyle = 'rgba(255, 255, 255, 0.3)';
                ctx.fill();

                p.y += p.speed;
                if (p.y > canvas.height) p.y = 0;
            });
            requestAnimationFrame(drawParticles);
        }
        drawParticles();

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        // Toggle password visibility (chi tiết như web lớn)
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

        // Chuyển form
        function showRegisterForm() {
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('register-form').style.display = 'block';
            clearAlert();
        }

        function showLoginForm() {
            document.getElementById('register-form').style.display = 'none';
            document.getElementById('login-form').style.display = 'block';
            clearAlert();
        }

        // Xử lý login (validation chi tiết)
        function handleLogin() {
            const username = document.getElementById('login-username').value.trim();
            const password = document.getElementById('login-password').value;

            if (!username || !password) {
                showAlert('Vui lòng điền đầy đủ thông tin!');
                return;
            }

            // Demo: Lưu session và redirect
            localStorage.setItem('loggedIn', true);
            alert('Đăng nhập thành công! Chuyển đến shop...');
            // window.location.href = '/shop.html'; // Thay bằng link shop thật
        }

        // Xử lý register (validation siêu chi tiết)
        function handleRegister() {
            const username = document.getElementById('reg-username').value.trim();
            const email = document.getElementById('reg-email').value.trim();
            const password = document.getElementById('reg-password').value;
            const confirm = document.getElementById('reg-confirm').value;

            if (username.length < 4 || username.length > 20) {
                showAlert('Tên đăng nhập phải 4-20 ký tự!');
                return;
            }

            if (!email.match(/^\S+@\S+\.\S+$/)) {
                showAlert('Email không hợp lệ!');
                return;
            }

            if (password.length < 8) {
                showAlert('Mật khẩu phải ít nhất 8 ký tự!');
                return;
            }

            if (password !== confirm) {
                showAlert('Mật khẩu không khớp!');
                return;
            }

            // Demo: Lưu và chuyển
            localStorage.setItem('loggedIn', true);
            alert('Đăng ký thành công! Chuyển đến shop...');
            // window.location.href = '/shop.html';
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
