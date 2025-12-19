<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketModVn - Shop Buôn Bán Acc, Mod, Hack Game</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
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
            background: url('https://images.pexels.com/photos/206359/pexels-photo-206359.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1') no-repeat center center/cover;
            position: relative;
            transition: background 1s ease;
        }
        body::before {
            content: ''; 
            position: absolute; 
            top: 0; 
            left: 0; 
            width: 100%; 
            height: 100%;
            background: rgba(0, 0, 0, 0.45); 
            z-index: -1;
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
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 50px 45px;
            width: 440px;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.25);
            text-align: center;
            color: #fff;
            opacity: 0;
            transform: translateY(50px) scale(0.95);
            animation: containerEnter 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
        }
        @keyframes containerEnter {
            0% { opacity: 0; transform: translateY(50px) scale(0.95); }
            100% { opacity: 1; transform: translateY(0) scale(1); }
        }
        h1 {
            font-size: 38px;
            font-weight: 500;
            margin-bottom: 50px;
            letter-spacing: 2px;
            opacity: 0;
            animation: titleFade 1s ease 0.5s forwards;
        }
        @keyframes titleFade {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .input-group {
            position: relative;
            margin-bottom: 35px;
            text-align: left;
            opacity: 0;
            transform: translateX(-30px);
        }
        .input-group:nth-child(1) { animation: inputSlide 0.8s ease forwards 0.7s; }
        .input-group:nth-child(2) { animation: inputSlide 0.8s ease forwards 0.9s; }
        .input-group:nth-child(3) { animation: inputSlide 0.8s ease forwards 1.1s; }
        .input-group:nth-child(4) { animation: inputSlide 0.8s ease forwards 1.3s; }
        @keyframes inputSlide {
            from { opacity: 0; transform: translateX(-30px); }
            to { opacity: 1; transform: translateX(0); }
        }
        .input-group label {
            display: block;
            font-size: 15px;
            color: rgba(255,255,255,0.85);
            margin-bottom: 10px;
            transition: color 0.4s ease;
        }
        .input-group input {
            width: 100%;
            padding: 14px 50px 14px 45px;
            background: transparent;
            border: none;
            border-bottom: 2px solid rgba(255, 255, 255, 0.6);
            color: #fff;
            font-size: 17px;
            transition: border-bottom 0.5s ease, padding-bottom 0.5s ease, box-shadow 0.5s ease;
        }
        .input-group input:focus {
            border-bottom: 2px solid #fff;
            padding-bottom: 13px;
            box-shadow: 0 10px 20px rgba(255,255,255,0.1);
            outline: none;
        }
        .input-group input::placeholder { 
            color: rgba(255, 255, 255, 0.6); 
            font-style: italic; 
            transition: color 0.4s ease;
        }
        .input-group input:focus::placeholder { color: rgba(255,255,255,0.8); }
        .input-icon {
            position: absolute;
            left: 0;
            bottom: 15px;
            color: rgba(255,255,255,0.7);
            font-size: 20px;
            transition: color 0.4s ease, transform 0.4s ease;
        }
        .input-group input:focus + .input-icon {
            color: #fff;
            transform: scale(1.1);
        }
        .toggle-password {
            position: absolute;
            right: 0;
            bottom: 15px;
            color: rgba(255,255,255,0.7);
            cursor: pointer;
            font-size: 20px;
            transition: color 0.4s ease, transform 0.4s ease;
        }
        .toggle-password:hover {
            color: #fff;
            transform: rotate(360deg);
        }
        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 25px 0 35px;
            font-size: 15px;
            opacity: 0;
            animation: fadeIn 1s ease 1.5s forwards;
        }
        .options label { 
            display: flex; 
            align-items: center; 
            cursor: pointer; 
            transition: color 0.4s ease; 
        }
        .options label:hover { color: #ddd; }
        .options input[type="checkbox"] { 
            margin-right: 10px; 
            accent-color: #fff; 
            transform: scale(1.2);
            transition: transform 0.3s ease;
        }
        .options input[type="checkbox"]:checked { transform: scale(1.4); }
        .forgot { 
            color: rgba(255,255,255,0.85); 
            text-decoration: none; 
            cursor: pointer; 
            transition: color 0.4s ease, text-shadow 0.4s ease; 
        }
        .forgot:hover { 
            color: #fff; 
            text-decoration: underline; 
            text-shadow: 0 0 10px rgba(255,255,255,0.5);
        }
        .btn {
            width: 100%;
            padding: 16px;
            background: linear-gradient(45deg, #fff, #f0f0f0);
            border: none;
            border-radius: 35px;
            color: #222;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            opacity: 0;
            animation: btnEnter 0.8s ease 1.7s forwards;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }
        @keyframes btnEnter {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .btn:hover { 
            background: #fff;
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        }
        .switch {
            margin-top: 30px;
            font-size: 15px;
            opacity: 0;
            animation: fadeIn 1s ease 1.9s forwards;
        }
        .switch a { 
            color: #fff; 
            text-decoration: none; 
            font-weight: 600; 
            cursor: pointer; 
            transition: all 0.4s ease;
        }
        .switch a:hover { 
            color: #00ffaa; 
            text-shadow: 0 0 10px rgba(0,255,170,0.5);
        }

        /* Trang Dashboard với animation mượt */
        #dashboard {
            display: none;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
            position: fixed;
            top: 0; left: 0;
            overflow-y: auto;
            opacity: 0;
            animation: dashboardEnter 1.5s ease forwards;
        }
        @keyframes dashboardEnter {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 50px;
            background: rgba(0, 0, 0, 0.6);
            box-shadow: 0 5px 20px rgba(0,0,0,0.4);
            position: sticky;
            top: 0;
            z-index: 10;
            animation: headerSlide 1s ease;
        }
        @keyframes headerSlide {
            from { transform: translateY(-100px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: #fff;
            letter-spacing: 2px;
            transition: all 0.5s ease;
        }
        .logo:hover { color: #00ffaa; text-shadow: 0 0 15px rgba(0,255,170,0.6); }
        .user-profile {
            display: flex;
            align-items: center;
            gap: 25px;
        }
        .avatar {
            width: 55px;
            height: 55px;
            border-radius: 50%;
            border: 4px solid #00ffaa;
            box-shadow: 0 0 20px rgba(0, 255, 170, 0.6);
            transition: all 0.6s ease;
        }
        .avatar:hover { transform: rotate(360deg) scale(1.1); box-shadow: 0 0 30px rgba(0, 255, 170, 0.8); }
        .username {
            font-size: 20px;
            font-weight: 500;
            color: #fff;
            transition: color 0.4s ease;
        }
        .username:hover { color: #00ffaa; }
        .logout-btn {
            background: #ff4d4d;
            padding: 12px 30px;
            border-radius: 30px;
            color: #fff;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.5s ease;
        }
        .logout-btn:hover { 
            background: #ff1a1a; 
            transform: translateY(-5px) scale(1.05); 
            box-shadow: 0 10px 20px rgba(255,77,77,0.5);
        }
        .dashboard-content {
            padding: 80px 50px;
            color: #fff;
            text-align: center;
        }
        .dashboard-content h2 {
            font-size: 48px;
            margin-bottom: 40px;
            animation: glowText 3s ease infinite alternate;
        }
        @keyframes glowText {
            from { text-shadow: 0 0 10px #00ffaa; }
            to { text-shadow: 0 0 30px #00ffaa, 0 0 40px #00ffaa; }
        }
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 50px;
            margin-top: 60px;
        }
        .product {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(15px);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: all 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            opacity: 0;
            transform: translateY(50px);
        }
        .product.visible {
            opacity: 1;
            transform: translateY(0);
        }
        .product:hover {
            transform: translateY(-20px) scale(1.05);
            box-shadow: 0 20px 50px rgba(0, 255, 170, 0.4);
        }
        .product img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 20px;
            margin-bottom: 25px;
            transition: transform 0.6s ease;
        }
        .product:hover img {
            transform: scale(1.1);
        }
        .product h3 { font-size: 24px; margin-bottom: 15px; transition: color 0.4s ease; }
        .product:hover h3 { color: #00ffaa; }
        .product .price { font-size: 22px; font-weight: 600; color: #00ffaa; margin: 20px 0; }
        .buy-btn, .add-to-cart {
            padding: 14px 30px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.5s ease;
            margin: 10px;
        }
        .buy-btn { background: #00ffaa; color: #000; }
        .buy-btn:hover { background: #00cc88; transform: scale(1.1); }
        .add-to-cart { background: #ffaa00; color: #000; }
        .add-to-cart:hover { background: #ff8800; transform: scale(1.1); }

        /* Alert box animation */
        .alert-box {
            background: rgba(255, 0, 0, 0.7);
            color: #fff;
            padding: 18px;
            border-radius: 15px;
            margin-bottom: 25px;
            display: none;
            font-size: 16px;
            animation: alertPulse 0.8s ease;
            box-shadow: 0 5px 20px rgba(255,0,0,0.4);
        }
        @keyframes alertPulse {
            0% { transform: scale(0.9); opacity: 0; }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); opacity: 1; }
        }
        .success { background: rgba(0, 255, 0, 0.7); box-shadow: 0 5px 20px rgba(0,255,0,0.4); }

        /* Cart count badge */
        #cart-count {
            background: #ff4d4d;
            color: #fff;
            border-radius: 50%;
            padding: 5px 10px;
            font-size: 14px;
            margin-left: 10px;
            animation: bounce 2s infinite;
        }
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
    </style>
</head>
<body>

    <!-- Particle Background -->
    <canvas id="particles-bg"></canvas>

    <!-- Trang Login / Register -->
    <div class="container" id="auth-container">
        <h1 id="form-title">Login</h1>
        <div id="alert-box" class="alert-box"></div>

        <form id="auth-form">
            <div id="username-field" class="input-group" style="display:none;">
                <label for="username">Username</label>
                <input type="text" id="username" placeholder="Nhập username của bạn" required>
                <i class="fas fa-user input-icon"></i>
            </div>
            <div class="input-group">
                <label for="email">Email</label>
                <input type="email" id="email" placeholder="Nhập email của bạn" required>
                <i class="fas fa-envelope input-icon"></i>
            </div>
            <div class="input-group">
                <label for="password">Mật khẩu</label>
                <input type="password" id="password" placeholder="Nhập mật khẩu" required>
                <i class="fas fa-lock input-icon"></i>
                <i class="fas fa-eye-slash toggle-password" onclick="togglePassword('password', this)"></i>
            </div>
            <div id="confirm-field" class="input-group" style="display:none;">
                <label for="confirm">Xác nhận mật khẩu</label>
                <input type="password" id="confirm" placeholder="Nhập lại mật khẩu" required>
                <i class="fas fa-lock input-icon"></i>
                <i class="fas fa-eye-slash toggle-password" onclick="togglePassword('confirm', this)"></i>
            </div>

            <div class="options">
                <label><input type="checkbox" id="remember"> Remember me</label>
                <span class="forgot" onclick="alert('Liên hệ admin để reset')">Quên mật khẩu?</span>
            </div>

            <button type="button" class="btn" id="submit-btn" onclick="handleSubmit()">Log In</button>
        </form>

        <div class="switch">
            <span id="switch-text">Chưa có tài khoản? <a onclick="toggleForm()">Đăng ký</a></span>
        </div>
    </div>

    <!-- Trang Dashboard -->
    <div id="dashboard">
        <div class="dashboard-header">
            <div class="logo">MarketModVn</div>
            <div class="user-profile">
                <span class="username" id="dash-username"></span>
                <img src="https://w7.pngwing.com/pngs/811/851/png-transparent-video-game-gamer-electronic-sports-avatar-gaming-game-face-video-game.png" alt="Avatar" class="avatar">
                <span id="cart-count">0</span>
                <div class="logout-btn" onclick="logout()">Đăng xuất</div>
            </div>
        </div>
        <div class="dashboard-content">
            <h2>Chào mừng quay lại!</h2>
            <p>Khám phá các sản phẩm hot nhất</p>
            <div class="product-grid" id="product-grid"></div>
        </div>
    </div>

    <script>
        // Particle background mượt mà
        const canvas = document.getElementById('particles-bg');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        let particles = [];
        const numParticles = 80;

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 3 + 1;
                this.speedX = Math.random() * 1 - 0.5;
                this.speedY = Math.random() * 1 - 0.5;
                this.opacity = Math.random() * 0.5 + 0.3;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.x > canvas.width || this.x < 0) this.speedX = -this.speedX;
                if (this.y > canvas.height || this.y < 0) this.speedY = -this.speedY;
            }
            draw() {
                ctx.fillStyle = `rgba(0, 255, 170, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particles = [];
            for (let i = 0; i < numParticles; i++) {
                particles.push(new Particle());
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
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

        let isRegister = false;
        let users = JSON.parse(localStorage.getItem('users')) || [];
        let cart = JSON.parse(localStorage.getItem('cart')) || [];
        let products = [
            { id: 1, name: "Acc VIP Free Fire", price: 500000, img: "https://placehold.co/300x200" },
            { id: 2, name: "Mod Menu PUBG", price: 300000, img: "https://placehold.co/300x200" },
            { id: 3, name: "Hack Liên Quân", price: 400000, img: "https://placehold.co/300x200" },
            { id: 4, name: "Tool Auto Farm", price: 250000, img: "https://placehold.co/300x200" },
            { id: 5, name: "Mod God Mode", price: 450000, img: "https://placehold.co/300x200" },
            { id: 6, name: "Acc Level Max", price: 1000000, img: "https://placehold.co/300x200" }
        ];

        function toggleForm() {
            isRegister = !isRegister;
            document.getElementById('form-title').textContent = isRegister ? 'Register' : 'Login';
            document.getElementById('submit-btn').textContent = isRegister ? 'Register' : 'Log In';
            document.getElementById('username-field').style.display = isRegister ? 'block' : 'none';
            document.getElementById('confirm-field').style.display = isRegister ? 'block' : 'none';
            document.getElementById('switch-text').innerHTML = isRegister 
                ? 'Đã có tài khoản? <a onclick="toggleForm()">Đăng nhập</a>'
                : 'Chưa có tài khoản? <a onclick="toggleForm()">Đăng ký</a>';
            hideAlert();
        }

        function togglePassword(id, icon) {
            const input = document
