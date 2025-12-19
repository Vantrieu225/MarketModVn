<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shop Mod & Acc - Đăng Nhập & Đăng Ký</title>
    
    <!-- Font Poppins cho chữ đẹp -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Icon Font Awesome cho icon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%); /* Nền gradient xanh dương hiện đại cho shop game/mod */
            overflow: hidden;
            transition: background 0.5s ease;
        }

        /* Hiệu ứng particle background cho siêu đẹp (như sao rơi) */
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
            width: 450px;
            background: rgba(255, 255, 255, 0.05); /* Glassmorphism kính mờ */
            backdrop-filter: blur(25px);
            border-radius: 25px;
            padding: 50px 40px;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            color: #fff;
            overflow: hidden;
            animation: fadeIn 1s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h2 {
            font-size: 28px;
            margin-bottom: 35px;
            letter-spacing: 1px;
            text-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
        }

        .input-box {
            position: relative;
            margin: 30px 0;
        }

        .input-box input {
            width: 100%;
            padding: 15px 25px;
            background: rgba(255, 255, 255, 0.1);
            border: none;
            outline: none;
            border-radius: 50px;
            color: #fff;
            font-size: 16px;
            transition: 0.3s;
            box-shadow: inset 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .input-box input:focus {
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
        }

        .input-box input::placeholder {
            color: rgba(255, 255, 255, 0.6);
            font-style: italic;
        }

        .input-box i {
            position: absolute;
            right: 25px;
            top: 50%;
            transform: translateY(-50%);
            color: rgba(255, 255, 255, 0.8);
            font-size: 18px;
            transition: 0.3s;
        }

        .input-box input:focus ~ i {
            color: #fff;
        }

        button {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, #00b4db, #0083b0); /* Gradient xanh dương cho nút */
            border: none;
            border-radius: 50px;
            color: #fff;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            transition: all 0.4s ease;
            margin-top: 20px;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            background: linear-gradient(45deg, #0083b0, #00b4db);
        }

        .links {
            margin-top: 30px;
            font-size: 14px;
            color: rgba(255, 255, 255, 0.7);
        }

        .links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: 0.3s;
        }

        .links a:hover {
            text-decoration: underline;
            color: #00b4db;
        }

        /* Toggle giữa login và register */
        #register-form {
            display: none;
        }

        /* Thông báo lỗi/thành công */
        .alert {
            margin-bottom: 20px;
            padding: 10px;
            border-radius: 10px;
            font-size: 14px;
            display: none;
        }

        .alert.success {
            background: rgba(0, 255, 0, 0.2);
            color: #0f0;
        }

        .alert.error {
            background: rgba(255, 0, 0, 0.2);
            color: #f00;
        }
    </style>
</head>
<body>

    <!-- Container chính cho cả login và register -->
    <div class="container">
        <!-- Trang Đăng Nhập -->
        <div id="login-form">
            <h2>Đăng Nhập Vào Shop Mod & Acc</h2>
            <div id="login-alert" class="alert"></div>
            <div class="input-box">
                <input type="text" id="login-identifier" placeholder="Tên đăng nhập hoặc Email" required>
                <i class="fas fa-user"></i>
            </div>
            <div class="input-box">
                <input type="password" id="login-password" placeholder="Mật khẩu (ít nhất 8 ký tự)" required>
                <i class="fas fa-lock"></i>
            </div>
            <button onclick="handleLogin()">Đăng Nhập Ngay</button>
            <div class="links">
                <p>Quên mật khẩu? <a href="#">Khôi phục</a></p>
                <p>Chưa có tài khoản? <a href="#" onclick="showRegister()">Đăng ký miễn phí</a></p>
            </div>
        </div>

        <!-- Trang Đăng Ký -->
        <div id="register-form">
            <h2>Đăng Ký Tài Khoản Shop Mod & Acc</h2>
            <div id="register-alert" class="alert"></div>
            <div class="input-box">
                <input type="text" id="reg-username" placeholder="Tên đăng nhập (4-20 ký tự, chữ cái/số)" required>
                <i class="fas fa-user"></i>
            </div>
            <div class="input-box">
                <input type="email" id="reg-email" placeholder="Email hợp lệ (ví dụ: user@example.com)" required>
                <i class="fas fa-envelope"></i>
            </div>
            <div class="input-box">
                <input type="password" id="reg-password" placeholder="Mật khẩu (ít nhất 8 ký tự, có chữ hoa/thường/số)" required>
                <i class="fas fa-lock"></i>
            </div>
            <div class="input-box">
                <input type="password" id="reg-confirm" placeholder="Xác nhận mật khẩu" required>
                <i class="fas fa-lock"></i>
            </div>
            <button onclick="handleRegister()">Đăng Ký Và Bắt Đầu Mua Sắm</button>
            <div class="links">
                <p>Đã có tài khoản? <a href="#" onclick="showLogin()">Đăng nhập</a></p>
            </div>
        </div>
    </div>

    <!-- Hiệu ứng particle background (siêu đẹp, như sao bay) -->
    <canvas id="particles"></canvas>

    <script>
        // Hiệu ứng particle background
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
                this.size = Math.random() * 2 + 0.5;
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
                ctx.fillStyle = 'rgba(255,255,255,0.8)';
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

        // Xử lý đăng ký
        function handleRegister() {
            const username = document.getElementById('reg-username').value.trim();
            const email = document.getElementById('reg-email').value.trim();
            const password = document.getElementById('reg-password').value;
            const confirm = document.getElementById('reg-confirm').value;
            const alertBox = document.getElementById('register-alert');

            alertBox.style.display = 'none';

            if (!username || !email || !password || !confirm) {
                showAlert(alertBox, 'error', 'Vui lòng điền đầy đủ thông tin!');
                return;
            }

            if (username.length < 4 || username.length > 20) {
                showAlert(alertBox, 'error', 'Tên đăng nhập phải từ 4-20 ký tự!');
                return;
            }

            if (!/^[a-zA-Z0-9]+$/.test(username)) {
                showAlert(alertBox, 'error', 'Tên đăng nhập chỉ chứa chữ cái và số!');
                return;
            }

            if (!/\S+@\S+\.\S+/.test(email)) {
                showAlert(alertBox, 'error', 'Email không hợp lệ!');
                return;
            }

            if (password.length < 8) {
                showAlert(alertBox, 'error', 'Mật khẩu phải ít nhất 8 ký tự!');
                return;
            }

            if (!/(?=.*[a-z])(?=.*[A-Z])(?=.*\d)/.test(password)) {
                showAlert(alertBox, 'error', 'Mật khẩu phải có chữ hoa, thường và số!');
                return;
            }

            if (password !== confirm) {
                showAlert(alertBox, 'error', 'Mật khẩu không trùng khớp!');
                return;
            }

            let users = JSON.parse(localStorage.getItem('users')) || [];
            if (users.find(u => u.username === username || u.email === email)) {
                showAlert(alertBox, 'error', 'Tên đăng nhập hoặc email đã tồn tại!');
                return;
            }

            users.push({ username, email, password }); // Lưu plain text chỉ để demo, thực tế hash mật khẩu
            localStorage.setItem('users', JSON.stringify(users));
            showAlert(alertBox, 'success', 'Đăng ký thành công! Đang chuyển sang đăng nhập...');
            setTimeout(showLogin, 2000);
        }

        // Xử lý đăng nhập
        function handleLogin() {
            const identifier = document.getElementById('login-identifier').value.trim();
            const password = document.getElementById('login-password').value;
            const alertBox = document.getElementById('login-alert');

            alertBox.style.display = 'none';

            if (!identifier || !password) {
                showAlert(alertBox, 'error', 'Vui lòng điền đầy đủ!');
                return;
            }

            let users = JSON.parse(localStorage.getItem('users')) || [];
            let user = users.find(u => (u.username === identifier || u.email === identifier) && u.password === password);

            if (user) {
                localStorage.setItem('currentUser', JSON.stringify(user));
                showAlert(alertBox, 'success', 'Đăng nhập thành công! Đang chuyển đến shop...');
                setTimeout(() => {
                    alert('Chào mừng đến shop buôn bán acc & mod! (Đây là demo, bạn có thể thêm shop thực tế)');
                    // Ở đây bạn có thể redirect đến trang shop: window.location.href = 'shop.html';
                }, 2000);
            } else {
                showAlert(alertBox, 'error', 'Sai tên đăng nhập/email hoặc mật khẩu!');
            }
        }

        // Hiển thị alert
        function showAlert(box, type, message) {
            box.className = `alert ${type}`;
            box.textContent = message;
            box.style.display = 'block';
        }

        // Chuyển sang trang đăng ký
        function showRegister() {
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('register-form').style.display = 'block';
            clearAlerts();
        }

        // Chuyển sang trang đăng nhập
        function showLogin() {
            document.getElementById('register-form').style.display = 'none';
            document.getElementById('login-form').style.display = 'block';
            clearAlerts();
        }

        function clearAlerts() {
            document.querySelectorAll('.alert').forEach(alert => {
                alert.style.display = 'none';
            });
        }

        // Kiểm tra nếu đã đăng nhập thì redirect (demo)
        window.onload = function() {
            const currentUser = localStorage.getItem('currentUser');
            if (currentUser) {
                alert('Bạn đã đăng nhập! Chuyển đến shop...');
                // window.location.href = 'shop.html'; // Thêm trang shop nếu cần
            }
        };
    </script>
</body>
</html>
