<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketModVn - Shop Buôn Bán Acc, Mod, Hack Game</title>
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
            transition: background 1s ease;
        }
        body::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.45); z-index: -1;
            transition: background 1s ease;
        }
        /* Hiệu ứng particle background mượt */
        #particles-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            pointer-events: none;
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
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
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
        .logo { font-size: 24px; font-weight: 700; color: #fff; }
        .user-profile { display: flex; align-items: center; gap: 15px; }
        .avatar { width: 50px; height: 50px; border-radius: 50%; border: 3px solid #00ffaa; box-shadow: 0 0 15px rgba(0, 255, 170, 0.5); }
        .username { font-size: 18px; color: #fff; }
        .logout-btn { background: #ff4d4d; padding: 10px 20px; border-radius: 20px; color: #fff; cursor: pointer; }
        .dashboard-content { padding: 60px 40px; color: #fff; text-align: center; }
        .product-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 30px; margin-top: 50px; }
        .product { background: rgba(255, 255, 255, 0.1); border-radius: 15px; padding: 20px; transition: 0.3s; }
        .product:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
        .product img { width: 100%; height: 150px; object-fit: cover; border-radius: 10px; }
        .product h3 { margin: 15px 0 10px; }
        .product .price { font-size: 20px; font-weight: 600; color: #00ffaa; }
        .buy-btn, .add-to-cart { padding: 10px; border-radius: 10px; cursor: pointer; margin-top: 10px; }
        .buy-btn { background: #00ffaa; color: #000; }
        .add-to-cart { background: #ffaa00; color: #000; }

        /* Trang Thanh Toán */
        #payment-page {
            display: none;
            padding: 80px 40px;
            color: #fff;
            max-width: 800px;
            margin: 0 auto;
        }
        .payment-header {
            text-align: center;
            margin-bottom: 40px;
            font-size: 36px;
        }
        .payment-summary {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 40px;
        }
        .payment-items {
            max-height: 300px;
            overflow-y: auto;
            margin-bottom: 20px;
        }
        .payment-item {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            border-bottom: 1px solid rgba(255,255,255,0.2);
        }
        .payment-total {
            font-size: 24px;
            text-align: right;
            margin-top: 20px;
        }
        .payment-methods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 40px;
        }
        .method {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s;
            border: 2px solid transparent;
        }
        .method:hover, .method.selected {
            border: 2px solid #00ffaa;
            background: rgba(0, 255, 170, 0.2);
        }
        .method i {
            font-size: 40px;
            margin-bottom: 15px;
        }
        .payment-form {
            display: none;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-top: 20px;
        }
        .qr-code {
            width: 200px;
            height: 200px;
            margin: 20px auto;
            background: #fff;
            border-radius: 10px;
        }
        .confirm-payment {
            background: #4caf50;
            color: #fff;
            padding: 15px;
            border: none;
            border-radius: 30px;
            width: 100%;
            font-size: 18px;
            cursor: pointer;
            margin-top: 30px;
        }
        .confirm-payment:hover {
            background: #3e8e41;
        }
        .back-cart {
            margin-top: 20px;
            color: #ccc;
            cursor: pointer;
        }
        .back-cart:hover {
            color: #fff;
        }
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
                <span class="forgot" onclick="showForgotPage()">Forgot password?</span>
            </div>

            <button type="button" class="btn" id="submit-btn" onclick="handleSubmit()">Log In</button>
        </form>

        <div class="switch">
            <span id="switch-text">Don't have an account? <a onclick="toggleForm()">Register</a></span>
        </div>
    </div>

    <!-- Trang Forgot Password -->
    <div class="container" id="forgot-page" style="display:none;">
        <h1>Khôi Phục Mật Khẩu</h1>
        <div id="forgot-alert" class="alert-box"></div>

        <form id="forgot-form">
            <div class="input-group">
                <input type="email" id="forgot-email" placeholder="Enter your email" required>
            </div>
            <button type="button" class="btn" onclick="handleForgot()">Gửi</button>
        </form>

        <div class="switch">
            <span><a onclick="backToLogin()">Quay lại login</a></span>
        </div>
    </div>

    <!-- Trang Dashboard -->
    <div id="dashboard" style="display:none;">
        <div class="dashboard-header">
            <div class="logo">MarketModVn</div>
            <div class="user-profile">
                <span class="username" id="dash-username"></span>
                <img src="https://w7.pngwing.com/pngs/811/851/png-transparent-video-game-gamer-electronic-sports-avatar-gaming-game-face-video-game.png" alt="Avatar" class="avatar">
                <div class="logout-btn" onclick="logout()">Đăng xuất</div>
            </div>
        </div>
        <div class="dashboard-content">
            <h2>Chào mừng đến Shop!</h2>
            <p>Khám phá các acc, mod, hack game hot nhất</p>
            <div class="product-grid" id="product-grid"></div>
        </div>
    </div>

    <script>
        let isRegister = false;
        let users = JSON.parse(localStorage.getItem('users')) || [];

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

            if (isRegister) {
                if (username.length < 4) { showAlert('Username ít nhất 4 ký tự!'); return; }
                if (users.find(u => u.username === username)) { showAlert('Username đã tồn tại!'); return; }
            }
            if (!email.match(/\S+@\S+\.\S+/)) { showAlert('Email không hợp lệ!'); return; }
            if (users.find(u => u.email === email && !isRegister)) { showAlert('Sai thông tin!'); return; }
            if (password.length < 6) { showAlert('Mật khẩu ít nhất 6 ký tự!'); return; }
            if (isRegister && password !== confirm) { showAlert('Mật khẩu không khớp!'); return; }

            if (isRegister) {
                users.push({ username, email, password });
                localStorage.setItem('users', JSON.stringify(users));
                showAlert('Đăng ký thành công!', 'success');
                toggleForm();
            } else {
                const user = users.find(u => u.email === email && u.password === password);
                if (!user) { showAlert('Sai email hoặc mật khẩu!'); return; }
                localStorage.setItem('currentUser', JSON.stringify(user));
                if (document.getElementById('remember').checked) localStorage.setItem('remember', 'true');
                showDashboard();
            }
        }

        function showForgotPage() {
            document.getElementById('auth-container').style.display = 'none';
            document.getElementById('forgot-page').style.display = 'block';
        }

        function handleForgot() {
            const email = document.getElementById('forgot-email').value.trim();
            if (!email.match(/\S+@\S+\.\S+/)) { showAlert('Email không hợp lệ!'); return; }

            const user = users.find(u => u.email === email);
            if (!user) { showAlert('Email không tồn tại!'); return; }

            const newPass = prompt('Nhập mật khẩu mới:');
            if (newPass && newPass.length >= 6) {
                user.password = newPass;
                localStorage.setItem('users', JSON.stringify(users));
                showAlert('Reset thành công!', 'success');
                backToLogin();
            } else {
                showAlert('Mật khẩu mới không hợp lệ!');
            }
        }

        function backToLogin() {
            document.getElementById('forgot-page').style.display = 'none';
            document.getElementById('auth-container').style.display = 'block';
        }

        function showAlert(msg, type = '') {
            const box = document.getElementById('alert-box');
            box.textContent = msg;
            box.classList.toggle('success', type === 'success');
            box.style.display = 'block';
            setTimeout(() => box.style.display = 'none', 3000);
        }

        function hideAlert() {
            document.getElementById('alert-box').style.display = 'none';
        }

        function showDashboard() {
            document.getElementById('auth-container').style.display = 'none';
            document.getElementById('dashboard').style.display = 'block';
            const user = JSON.parse(localStorage.getItem('currentUser'));
            document.getElementById('dash-username').textContent = user.username;
            renderProducts();
        }

        function logout() {
            localStorage.removeItem('currentUser');
            localStorage.removeItem('remember');
            document.getElementById('dashboard').style.display = 'none';
            document.getElementById('auth-container').style.display = 'block';
        }

        function renderProducts() {
            const grid = document.getElementById('product-grid');
            grid.innerHTML = '';
            products.forEach(p => {
                grid.innerHTML += `
                    <div class="product">
                        <img src="\( {p.img}" alt=" \){p.name}">
                        <h3>${p.name}</h3>
                        <span class="price">${p.price.toLocaleString('vi-VN')} VNĐ</span>
                        <div class="buy-btn" onclick="alert('Mua thành công!')">Mua Ngay</div>
                        <div class="add-to-cart" onclick="addToCart(${p.id})">Thêm Vào Giỏ</div>
                    </div>
                `;
            });
        }

        window.onload = () => {
            const remember = localStorage.getItem('remember');
            if (remember) {
                const user = localStorage.getItem('currentUser');
                if (user) showDashboard();
            }
        };
    </script>
</body>
</html>
