<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketModVn - Đăng Nhập</title>
    <!-- Font Roboto cho phông chữ hiện đại, đơn giản như các shop game lớn -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <!-- Font Awesome cho icon (user, lock, eye, social) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Biến CSS cho dễ tùy chỉnh, tỉ mỉ như pro */
        :root {
            --primary-color: #00ffaa; /* Màu xanh neon gaming */
            --secondary-color: #ffaa00; /* Màu vàng cho highlight */
            --background-gradient: linear-gradient(135deg, #0f0c29, #302b63, #24243e); /* Nền dark game */
            --glass-bg: rgba(255, 255, 255, 0.1); /* Kính mờ */
            --glass-blur: blur(15px);
            --text-color: #fff;
            --text-secondary: #ccc;
            --border-color: rgba(255, 255, 255, 0.2);
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            --transition: all 0.3s ease;
            --animation-duration: 0.5s;
        }

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
            background: var(--background-gradient);
            overflow: hidden;
            position: relative;
        }

        /* Particle background siêu mượt cho gaming feel */
        #particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .container {
            position: relative;
            background: var(--glass-bg);
            backdrop-filter: var(--glass-blur);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 40px;
            max-width: 400px;
            width: 100%;
            box-shadow: var(--shadow);
            text-align: center;
            animation: fadeIn var(--animation-duration) ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .logo {
            font-size: 32px;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 30px;
            text-shadow: 0 0 10px var(--primary-color);
            animation: logoGlow 2s ease infinite alternate;
        }

        @keyframes logoGlow {
            from { text-shadow: 0 0 5px var(--primary-color); }
            to { text-shadow: 0 0 20px var(--primary-color); }
        }

        form {
            display: flex;
            flex-direction: column;
        }

        .input-box {
            position: relative;
            margin-bottom: 30px;
        }

        .input-box input {
            width: 100%;
            padding: 12px 15px;
            background: transparent;
            border: none;
            border-bottom: 2px solid var(--border-color);
            color: var(--text-color);
            font-size: 16px;
            transition: var(--transition);
        }

        .input-box input:focus {
            border-bottom: 2px solid var(--primary-color);
        }

        .input-box label {
            position: absolute;
            top: 50%;
            left: 0;
            transform: translateY(-50%);
            color: var(--text-secondary);
            pointer-events: none;
            transition: var(--transition);
        }

        .input-box input:focus ~ label,
        .input-box input:valid ~ label {
            top: -5px;
            font-size: 12px;
            color: var(--primary-color);
        }

        .input-box i {
            position: absolute;
            right: 0;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-secondary);
            cursor: pointer;
            transition: var(--transition);
        }

        .input-box i:hover {
            color: var(--primary-color);
        }

        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            font-size: 14px;
        }

        .options label {
            display: flex;
            align-items: center;
            color: var(--text-secondary);
            cursor: pointer;
        }

        .options input {
            margin-right: 10px;
        }

        .forgot {
            color: var(--text-secondary);
            text-decoration: none;
            transition: var(--transition);
        }

        .forgot:hover {
            color: var(--primary-color);
            text-decoration: underline;
        }

        .btn {
            background: var(--primary-color);
            color: #000;
            padding: 15px;
            border: none;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
            margin-bottom: 20px;
        }

        .btn:hover {
            background: #00cc88;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 204, 136, 0.5);
        }

        .social-login {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .social-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--glass-bg);
            padding: 15px;
            border-radius: 50px;
            color: var(--text-color);
            text-decoration: none;
            transition: var(--transition);
            font-size: 16px;
        }

        .social-btn i {
            margin-right: 10px;
            font-size: 20px;
        }

        .social-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 255, 255, 0.2);
        }

        .google-btn { background: #4285f4; color: #fff; }
        .google-btn:hover { background: #357ae8; }
        .facebook-btn { background: #3b5998; color: #fff; }
        .facebook-btn:hover { background: #2d4373; }
        .apple-btn { background: #000; color: #fff; }
        .apple-btn:hover { background: #333; }

        .switch-link {
            margin-top: 30px;
            font-size: 14px;
            color: var(--text-secondary);
        }

        .switch-link a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }

        .switch-link a:hover {
            text-decoration: underline;
        }

        .alert {
            background: rgba(255, 0, 0, 0.8);
            color: #fff;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            display: none;
            animation: fadeIn 0.3s ease;
        }

        .success { background: rgba(0, 255, 0, 0.8); }

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

    <!-- Background Particles cho hiệu ứng gaming siêu đẹp -->
    <canvas id="particles"></canvas>

    <!-- Container Đăng Nhập -->
    <div class="container">
        <div class="logo">MarketModVn</div>

        <form id="login-form">
            <div class="input-box">
                <input type="email" id="email" required>
                <label>Email</label>
            </div>
            <div class="input-box">
                <input type="password" id="password" required>
                <label>Mật khẩu</label>
                <i class="fas fa-eye-slash" id="toggle-password" onclick="togglePassword()"></i>
            </div>
            <div class="options">
                <label>
                    <input type="checkbox" id="remember-me">
                    Nhớ mật khẩu
                </label>
                <a href="#" class="forgot" onclick="forgotPassword()">Quên mật khẩu?</a>
            </div>
            <button type="button" class="btn" onclick="login()">Đăng Nhập</button>
        </form>

        <div class="social-login">
            <a href="#" class="social-btn google-btn">
                <i class="fab fa-google"></i>
                Đăng nhập bằng Google
            </a>
            <a href="#" class="social-btn facebook-btn">
                <i class="fab fa-facebook-f"></i>
                Đăng nhập bằng Facebook
            </a>
            <a href="#" class="social-btn apple-btn">
                <i class="fab fa-apple"></i>
                Đăng nhập bằng Apple
            </a>
        </div>

        <div class="switch-link">
            Chưa có tài khoản? <a href="#" onclick="switchToRegister()">Đăng ký ngay</a>
        </div>

        <div id="alert" class="alert"></div>
    </div>

    <script>
        // Particle Background (siêu mượt, nhẹ)
        const canvas = document.getElementById('particles');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let particlesArray = [];
        const numberOfParticles = 100;

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 3 + 1;
                this.speedX = Math.random() * 1 - 0.5;
                this.speedY = Math.random() * 1 - 0.5;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.x > canvas.width || this.x < 0) this.speedX = -this.speedX;
                if (this.y > canvas.height || this.y < 0) this.speedY = -this.speedY;
            }
            draw() {
                ctx.fillStyle = 'rgba(0, 255, 170, 0.6)';
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particlesArray = [];
            for (let i = 0; i < numberOfParticles; i++) {
                particlesArray.push(new Particle());
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particlesArray.forEach(particle => {
                particle.update();
                particle.draw();
            });
            requestAnimationFrame(animateParticles);
        }

        initParticles();
        animateParticles();

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            initParticles();
        });

        // Toggle Password Visibility
        function togglePassword() {
            const password = document.getElementById('password');
            const icon = document.getElementById('toggle-password');
            if (password.type === 'password') {
                password.type = 'text';
                icon.classList.replace('fa-eye-slash', 'fa-eye');
            } else {
                password.type = 'password';
                icon.classList.replace('fa-eye', 'fa-eye-slash');
            }
        }

        // Login Function (siêu tỉ mỉ với validation)
        function login() {
            const email = document.getElementById('email').value.trim();
            const password = document.getElementById('password').value;
            const remember = document.getElementById('remember-me').checked;

            if (!email || !password) {
                showAlert('Vui lòng điền đầy đủ thông tin!', 'error');
                return;
            }

            if (!validateEmail(email)) {
                showAlert('Email không hợp lệ!', 'error');
                return;
            }

            if (password.length < 8) {
                showAlert('Mật khẩu phải ít nhất 8 ký tự!', 'error');
                return;
            }

            // Demo login (thực tế kết nối backend)
            if (remember) {
                localStorage.setItem('rememberEmail', email);
            } else {
                localStorage.removeItem('rememberEmail');
            }

            showAlert('Đăng nhập thành công!', 'success');
            // Redirect đến dashboard (demo)
            setTimeout(() => window.location.href = '/dashboard', 1000);
        }

        // Forgot Password (tỉ mỉ với modal or page)
        function forgotPassword() {
            const email = prompt('Nhập email để khôi phục mật khẩu:');
            if (email && validateEmail(email)) {
                showAlert('Link khôi phục đã gửi đến email!', 'success');
            } else {
                showAlert('Email không hợp lệ!', 'error');
            }
        }

        // Switch to Register (tỉ mỉ, có thể thay form)
        function switchToRegister() {
            // Demo: Chuyển sang form register
            alert('Chuyển sang trang đăng ký...');
            // Thực tế: load form register or redirect
        }

        // Validation Email
        function validateEmail(email) {
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
        }

        // Show Alert
        function showAlert(message, type) {
            const alert = document.getElementById('alert');
            alert.textContent = message;
            alert.className = 'alert' + (type === 'success' ? ' success' : '');
            alert.style.display = 'block';
            setTimeout(() => alert.style.display = 'none', 3000);
        }

        // Load Remember Me
        window.onload = () => {
            const rememberedEmail = localStorage.getItem('rememberEmail');
            if (rememberedEmail) {
                document.getElementById('email').value = rememberedEmail;
                document.getElementById('remember-me').checked = true;
            }
        };
    </script>
</body>
</html>
