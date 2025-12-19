<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketModVn - Login & Dashboard</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Roboto', sans-serif; }
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: url('https://images.pexels.com/photos/206359/pexels-photo-206359.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1') no-repeat center center/cover;
            position: relative;
        }
        body::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.45); z-index: -1;
        }
        .container {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(18px);
            border-radius: 15px;
            padding: 45px 40px;
            width: 420px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
            color: #fff;
        }
        h1 {
            font-size: 36px;
            font-weight: 500;
            margin-bottom: 40px;
        }
        .input-group {
            position: relative;
            margin-bottom: 25px;
            text-align: left;
        }
        .input-group input {
            width: 100%;
            padding: 12px 0;
            background: transparent;
            border: none;
            border-bottom: 1px solid rgba(255, 255, 255, 0.6);
            color: #fff;
            font-size: 16px;
        }
        .input-group input::placeholder { color: rgba(255, 255, 255, 0.7); }
        .input-group input:focus { border-bottom: 2px solid #fff; outline: none; }
        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 20px 0 30px;
            font-size: 14px;
        }
        .options label { display: flex; align-items: center; cursor: pointer; }
        .options input[type="checkbox"] { margin-right: 8px; accent-color: #fff; }
        .forgot { color: rgba(255,255,255,0.8); text-decoration: none; cursor: pointer; }
        .forgot:hover { text-decoration: underline; }
        .btn {
            width: 100%;
            padding: 14px;
            background: #fff;
            border: none;
            border-radius: 30px;
            color: #222;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            transition: 0.3s;
        }
        .btn:hover { background: #f0f0f0; transform: translateY(-2px); }
        .switch {
            margin-top: 25px;
            font-size: 14px;
        }
        .switch a { color: #fff; text-decoration: none; font-weight: 500; cursor: pointer; }
        .switch a:hover { text-decoration: underline; }

        /* Trang Dashboard */
        #dashboard {
            display: none;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
            position: fixed;
            top: 0; left: 0;
            overflow-y: auto;
        }
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: rgba(0, 0, 0, 0.5);
        }
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: #fff;
        }
        .user-profile {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            border: 2px solid #00ffaa;
            box-shadow: 0 0 10px rgba(0, 255, 170, 0.3);
            cursor: pointer;
        }
        .username {
            font-size: 16px;
            color: #fff;
        }
        .logout-btn {
            background: #ff4d4d;
            padding: 8px 20px;
            border-radius: 20px;
            color: #fff;
            cursor: pointer;
            font-size: 14px;
        }
        .logout-btn:hover { background: #ff1a1a; }
        .dashboard-content {
            padding: 60px 40px;
            color: #fff;
            text-align: center;
        }
        .dashboard-content h2 {
            font-size: 42px;
            margin-bottom: 30px;
        }
        .dashboard-content p {
            font-size: 18px;
            margin-bottom: 20px;
        }
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }
        .product {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: left;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
            transition: 0.3s;
        }
        .product:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3); }
        .product img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 15px;
        }
        .product h3 { font-size: 20px; margin-bottom: 10px; }
        .product p { font-size: 14px; color: #ddd; margin-bottom: 15px; }
        .product .price { font-size: 18px; font-weight: 500; color: #00ffaa; }
        .buy-btn {
            background: #00ffaa;
            color: #000;
            padding: 10px;
            border-radius: 10px;
            text-align: center;
            cursor: pointer;
            margin-top: 10px;
        }
        .buy-btn:hover { background: #00cc88; }

        /* Alert box cho lỗi/validation */
        .alert-box {
            background: rgba(255, 0, 0, 0.6);
            color: #fff;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            display: none;
            font-size: 14px;
            text-align: left;
        }
    </style>
</head>
<body>

    <!-- Trang Login / Register -->
    <div class="container" id="auth-container">
        <h1 id="form-title">Login</h1>
        <div id="alert-box" class="alert-box"></div>

        <!-- Form -->
        <form id="auth-form">
            <div id="username-field" class="input-group" style="display:none;">
                <input type="text" id="username" placeholder="Enter your username" required>
            </div>
            <div class="input-group">
                <input type="email" id="email" placeholder="Enter your email" required>
            </div>
            <div class="input-group">
                <input type="password" id="password" placeholder="Enter your password" required>
            </div>
            <div id="confirm-field" class="input-group" style="display:none;">
                <input type="password" id="confirm" placeholder="Confirm your password" required>
            </div>

            <div class="options">
                <label><input type="checkbox" id="remember"> Remember me</label>
                <span class="forgot" onclick="handleForgot()">Forgot password?</span>
            </div>

            <button type="button" class="btn" id="submit-btn" onclick="handleSubmit()">Log In</button>
        </form>

        <div class="switch">
            <span id="switch-text">Don't have an account? <a onclick="toggleForm()">Register</a></span>
        </div>
    </div>

    <!-- Trang Dashboard -->
    <div id="dashboard" style="display:none;">
        <div class="dashboard-header">
            <div class="logo">MarketModVn</div>
            <div class="user-profile">
                <span class="username" id="dash-username"></span>
                <img src="https://w7.pngwing.com/pngs/811/851/png-transparent-video-game-gamer-electronic-sports-avatar-gaming-game-face-video-game.png" alt="Avatar" class="avatar" onclick="alert('Profile: ' + localStorage.getItem('currentUser'))">
                <div class="logout-btn" onclick="logout()">Đăng xuất</div>
            </div>
        </div>
        <div class="dashboard-content">
            <h2>Chào mừng đến Shop!</h2>
            <p>Khám phá các acc, mod, hack game hot nhất</p>
            <div class="product-grid">
                <!-- Sản phẩm mẫu (có thể thêm nhiều) -->
                <div class="product">
                    <img src="https://placehold.co/250x150" alt="Product 1">
                    <h3>Acc Game VIP</h3>
                    <p>Acc full item, level cao, giá rẻ</p>
                    <span class="price">500.000 VNĐ</span>
                    <div class="buy-btn" onclick="alert('Mua thành công!')">Mua ngay</div>
                </div>
                <div class="product">
                    <img src="https://placehold.co/250x150" alt="Product 2">
                    <h3>Mod Hack Game</h3>
                    <p>Mod unlimited money, unlock all</p>
                    <span class="price">200.000 VNĐ</span>
                    <div class="buy-btn" onclick="alert('Mua thành công!')">Mua ngay</div>
                </div>
                <div class="product">
                    <img src="https://placehold.co/250x150" alt="Product 3">
                    <h3>Hack Tool Pro</h3>
                    <p>Công cụ hack an toàn, update mới</p>
                    <span class="price">300.000 VNĐ</span>
                    <div class="buy-btn" onclick="alert('Mua thành công!')">Mua ngay</div>
                </div>
                <!-- Thêm sản phẩm khác ở đây -->
            </div>
        </div>
    </div>

    <script>
        let isRegister = false;

        function toggleForm() {
            isRegister = !isRegister;
            document.getElementById('form-title').textContent = isRegister ? 'Register' : 'Login';
            document.getElementById('submit-btn').textContent = isRegister ? 'Register' : 'Log In';
            document.getElementById('username-field').style.display = isRegister ? 'block' : 'none';
            document.getElementById('confirm-field').style.display = isRegister ? 'block' : 'none';
            document.getElementById('switch-text').innerHTML = isRegister 
                ? 'Already have an account? <a onclick="toggleForm()">Log in</a>'
                : 'Don\'t have an account? <a onclick="toggleForm()">Register</a>';
            hideAlert();
        }

        function handleSubmit() {
            const username = isRegister ? document.getElementById('username').value.trim() : '';
            const email = document.getElementById('email').value.trim();
            const password = document.getElementById('password').value;
            const confirm = isRegister ? document.getElementById('confirm').value : '';

            // Validation chi tiết
            if (isRegister && username.length < 4) { showAlert('Username phải ít nhất 4 ký tự!'); return; }
            if (!email.match(/\S+@\S+\.\S+/)) { showAlert('Email không hợp lệ!'); return; }
            if (password.length < 6) { showAlert('Mật khẩu phải ít nhất 6 ký tự!'); return; }
            if (isRegister && password !== confirm) { showAlert('Mật khẩu không khớp!'); return; }

            let users = JSON.parse(localStorage.getItem('users')) || [];

            if (isRegister) {
                if (users.find(u => u.email === email)) { showAlert('Email đã tồn tại!'); return; }
                users.push({ username, email, password });
                localStorage.setItem('users', JSON.stringify(users));
                showAlert('Đăng ký thành công! Đăng nhập để tiếp tục.', 'success');
                toggleForm(); // Chuyển sang login sau đăng ký
            } else {
                const user = users.find(u => u.email === email && u.password === password);
                if (!user) { showAlert('Sai email hoặc mật khẩu!'); return; }
                localStorage.setItem('currentUser', JSON.stringify(user));
                if (document.getElementById('remember').checked) {
                    localStorage.setItem('rememberEmail', email);
                }
                enterDashboard(user.username);
            }
        }

        function handleForgot() {
            const email = prompt('Nhập email để khôi phục mật khẩu:');
            if (email) {
                const users = JSON.parse(localStorage.getItem('users')) || [];
                const user = users.find(u => u.email === email);
                if (user) {
                    alert('Mật khẩu của bạn là: ' + user.password + ' (Demo - thực tế gửi email)');
                } else {
                    alert('Email không tồn tại!');
                }
            }
        }

        function enterDashboard(username) {
            document.getElementById('auth-container').style.display = 'none';
            document.getElementById('dashboard').style.display = 'block';
            document.getElementById('dash-username').textContent = username;
        }

        function logout() {
            localStorage.removeItem('currentUser');
            localStorage.removeItem('rememberEmail');
            document.getElementById('auth-container').style.display = 'block';
            document.getElementById('dashboard').style.display = 'none';
            toggleForm(); // Reset về login
        }

        function showAlert(message, type = 'error') {
            const alertBox = document.getElementById('alert-box');
            alertBox.textContent = message;
            alertBox.style.background = type === 'success' ? 'rgba(0, 255, 0, 0.6)' : 'rgba(255, 0, 0, 0.6)';
            alertBox.style.display = 'block';
        }

        function hideAlert() {
            document.getElementById('alert-box').style.display = 'none';
        }

        window.onload = function() {
            const currentUser = localStorage.getItem('currentUser');
            if (currentUser) {
                const user = JSON.parse(currentUser);
                enterDashboard(user.username);
            } else {
                const rememberedEmail = localStorage.getItem('rememberEmail');
                if (rememberedEmail) {
                    document.getElementById('email').value = rememberedEmail;
                    document.getElementById('remember').checked = true;
                }
            }
        }
    </script>
</body>
</html>
