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
            letter-spacing: 1px;
        }
        .input-group {
            position: relative;
            margin-bottom: 25px;
            text-align: left;
        }
        .input-group label {
            display: block;
            font-size: 14px;
            color: rgba(255,255,255,0.8);
            margin-bottom: 8px;
            transition: color 0.3s;
        }
        .input-group input {
            width: 100%;
            padding: 12px 40px 12px 15px;
            background: transparent;
            border: none;
            border-bottom: 1px solid rgba(255, 255, 255, 0.6);
            color: #fff;
            font-size: 16px;
            transition: border-bottom 0.3s;
        }
        .input-group input:focus {
            border-bottom: 2px solid #fff;
            outline: none;
        }
        .input-group input::placeholder { 
            color: rgba(255, 255, 255, 0.7); 
        }
        .input-icon {
            position: absolute;
            left: 0;
            bottom: 12px;
            color: rgba(255,255,255,0.7);
            font-size: 18px;
        }
        .toggle-password {
            position: absolute;
            right: 0;
            bottom: 12px;
            color: rgba(255,255,255,0.7);
            cursor: pointer;
            font-size: 18px;
            transition: color 0.3s;
        }
        .toggle-password:hover {
            color: #fff;
        }
        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 20px 0 30px;
            font-size: 14px;
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
        .forgot { 
            color: rgba(255,255,255,0.8); 
            text-decoration: none; 
            cursor: pointer; 
        }
        .forgot:hover { 
            text-decoration: underline; 
            color: #fff; 
        }
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
            transition: background 0.3s, transform 0.3s, box-shadow 0.3s;
        }
        .btn:hover { 
            background: #f0f0f0; 
            transform: translateY(-2px); 
            box-shadow: 0 5px 15px rgba(0,0,0,0.2); 
        }
        .btn:disabled {
            background: #ccc;
            cursor: not-allowed;
        }
        .switch {
            margin-top: 25px;
            font-size: 14px;
        }
        .switch a { 
            color: #fff; 
            text-decoration: none; 
            font-weight: 500; 
            cursor: pointer; 
        }
        .switch a:hover { 
            text-decoration: underline; 
            color: #ddd; 
        }

        /* Trang Dashboard */
        #dashboard {
            display: none;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
            position: fixed;
            top: 0; 
            left: 0;
            overflow-y: auto;
            animation: fadeInDashboard 0.8s ease;
        }
        @keyframes fadeInDashboard {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: rgba(0, 0, 0, 0.5);
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
            position: sticky;
            top: 0;
            z-index: 10;
        }
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: #fff;
            letter-spacing: 1px;
            cursor: pointer;
            transition: color 0.3s;
        }
        .logo:hover {
            color: #00ffaa;
        }
        .user-profile {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        .avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            border: 3px solid #00ffaa;
            box-shadow: 0 0 15px rgba(0, 255, 170, 0.5);
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .avatar:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px rgba(0, 255, 170, 0.7);
        }
        .username {
            font-size: 18px;
            font-weight: 500;
            color: #fff;
            text-shadow: 0 0 5px #000;
            cursor: pointer;
        }
        .logout-btn {
            background: #ff4d4d;
            padding: 10px 25px;
            border-radius: 25px;
            color: #fff;
            cursor: pointer;
            font-size: 14px;
            transition: background 0.3s, transform 0.3s;
        }
        .logout-btn:hover { 
            background: #ff1a1a; 
            transform: translateY(-2px); 
        }
        .dashboard-content {
            padding: 60px 40px;
            color: #fff;
            text-align: center;
        }
        .dashboard-content h2 {
            font-size: 42px;
            margin-bottom: 30px;
            letter-spacing: 1px;
            text-shadow: 0 0 10px #000;
        }
        .dashboard-content p {
            font-size: 18px;
            margin-bottom: 40px;
            color: #ddd;
        }
        .search-bar {
            width: 60%;
            margin: 0 auto 40px;
            position: relative;
        }
        .search-bar input {
            width: 100%;
            padding: 15px 20px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 30px;
            color: #fff;
            font-size: 16px;
            transition: border 0.3s;
        }
        .search-bar input:focus {
            border: 1px solid #00ffaa;
            outline: none;
        }
        .search-bar i {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: #ddd;
            cursor: pointer;
        }
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 40px;
            margin-top: 50px;
            padding: 0 20px;
        }
        .product {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 25px;
            text-align: left;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .product:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
        }
        .product img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 15px;
            margin-bottom: 20px;
            transition: transform 0.3s;
        }
        .product img:hover {
            transform: scale(1.05);
        }
        .product h3 { 
            font-size: 22px; 
            margin-bottom: 15px; 
            color: #fff; 
        }
        .product p { 
            font-size: 15px; 
            color: #ccc; 
            margin-bottom: 20px; 
        }
        .product .price { 
            font-size: 20px; 
            font-weight: 600; 
            color: #00ffaa; 
            margin-bottom: 15px; 
        }
        .buy-btn {
            background: #00ffaa;
            color: #000;
            padding: 12px 25px;
            border-radius: 25px;
            text-align: center;
            cursor: pointer;
            font-weight: 500;
            transition: background 0.3s, transform 0.3s;
        }
        .buy-btn:hover { 
            background: #00cc88; 
            transform: translateY(-2px); 
        }
        .add-to-cart {
            background: #ffaa00;
            color: #000;
            padding: 12px 25px;
            border-radius: 25px;
            text-align: center;
            cursor: pointer;
            font-weight: 500;
            margin-top: 10px;
            transition: background 0.3s, transform 0.3s;
        }
        .add-to-cart:hover { 
            background: #ff8800; 
            transform: translateY(-2px); 
        }
        /* Trang Profile */
        #profile-page {
            display: none;
            padding: 80px 40px;
            color: #fff;
        }
        .profile-header {
            text-align: center;
            margin-bottom: 50px;
        }
        .profile-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid #00ffaa;
            box-shadow: 0 0 20px rgba(0, 255, 170, 0.5);
            margin-bottom: 20px;
        }
        .profile-username {
            font-size: 32px;
            margin-bottom: 10px;
        }
        .profile-email {
            font-size: 18px;
            color: #ccc;
        }
        .profile-form {
            max-width: 500px;
            margin: 0 auto;
        }
        .profile-input {
            margin-bottom: 30px;
        }
        .profile-input label {
            display: block;
            font-size: 16px;
            margin-bottom: 10px;
        }
        .profile-input input {
            width: 100%;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            color: #fff;
            font-size: 16px;
        }
        .save-profile {
            background: #00ffaa;
            color: #000;
            padding: 15px;
            border: none;
            border-radius: 10px;
            width: 100%;
            font-size: 18px;
            cursor: pointer;
            transition: background 0.3s;
        }
        .save-profile:hover {
            background: #00cc88;
        }
        /* Trang Giỏ Hàng */
        #cart-page {
            display: none;
            padding: 80px 40px;
            color: #fff;
        }
        .cart-header {
            text-align: center;
            margin-bottom: 50px;
            font-size: 36px;
        }
        .cart-item {
            display: flex;
            justify-content: space-between;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        .cart-item img {
            width: 100px;
            height: 100px;
            object-fit: cover;
            border-radius: 10px;
        }
        .cart-details {
            flex: 1;
            margin-left: 20px;
        }
        .cart-details h3 {
            font-size: 20px;
            margin-bottom: 10px;
        }
        .cart-details p {
            font-size: 16px;
            color: #ccc;
        }
        .cart-price {
            font-size: 18px;
            color: #00ffaa;
            margin-right: 20px;
        }
        .remove-cart {
            background: #ff4d4d;
            padding: 10px 20px;
            border-radius: 20px;
            color: #fff;
            cursor: pointer;
        }
        .remove-cart:hover {
            background: #ff1a1a;
        }
        .total {
            text-align: right;
            font-size: 24px;
            margin-top: 30px;
        }
        .checkout-btn {
            background: #00ffaa;
            color: #000;
            padding: 15px 30px;
            border-radius: 30px;
            cursor: pointer;
            display: block;
            width: 200px;
            margin: 20px auto 0;
            text-align: center;
        }
        .checkout-btn:hover {
            background: #00cc88;
        }
        /* Trang Quên Mật Khẩu */
        #forgot-page {
            display: none;
            padding: 80px 40px;
            color: #fff;
            text-align: center;
        }
        .forgot-form {
            max-width: 400px;
            margin: 0 auto;
        }
        .forgot-input {
            margin-bottom: 30px;
        }
        .forgot-input input {
            width: 100%;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            color: #fff;
        }
        .send-reset {
            background: #ffaa00;
            color: #000;
            padding: 15px;
            border: none;
            border-radius: 10px;
            width: 100%;
            font-size: 18px;
            cursor: pointer;
        }
        .send-reset:hover {
            background: #ff8800;
        }
        .back-login {
            margin-top: 20px;
            color: #ccc;
            cursor: pointer;
        }
        .back-login:hover {
            color: #fff;
        }
        /* Trang Admin (nếu là admin) */
        #admin-page {
            display: none;
            padding: 80px 40px;
            color: #fff;
        }
        .admin-header {
            text-align: center;
            margin-bottom: 50px;
            font-size: 36px;
        }
        .admin-section {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 40px;
        }
        .admin-section h3 {
            font-size: 24px;
            margin-bottom: 20px;
        }
        .add-product-form {
            max-width: 600px;
            margin: 0 auto;
        }
        .add-product-input {
            margin-bottom: 20px;
        }
        .add-product-input label {
            display: block;
            margin-bottom: 10px;
        }
        .add-product-input input, .add-product-input textarea {
            width: 100%;
            padding: 15px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            color: #fff;
        }
        .add-product-btn {
            background: #00ffaa;
            color: #000;
            padding: 15px;
            border: none;
            border-radius: 10px;
            width: 100%;
            cursor: pointer;
        }
        .add-product-btn:hover {
            background: #00cc88;
        }
        .user-list {
            list-style: none;
        }
        .user-item {
            background: rgba(0, 0, 0, 0.2);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .delete-user {
            background: #ff4d4d;
            padding: 10px 20px;
            border-radius: 20px;
            color: #fff;
            cursor: pointer;
        }
        .delete-user:hover {
            background: #ff1a1a;
        }
        /* Alert box */
        .alert-box {
            background: rgba(255, 0, 0, 0.6);
            color: #fff;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            display: none;
            font-size: 14px;
            text-align: left;
            animation: shake 0.5s;
        }
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }
        .success { background: rgba(0, 255, 0, 0.6); }
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
                <label for="username">Username (4-20 ký tự, chữ cái, số, _)</label>
                <input type="text" id="username" placeholder="Enter your username" required>
            </div>
            <div class="input-group">
                <label for="email">Email (hợp lệ)</label>
                <input type="email" id="email" placeholder="Enter your email" required>
            </div>
            <div class="input-group">
                <label for="password">Password (ít nhất 6 ký tự, có chữ hoa, số)</label>
                <input type="password" id="password" placeholder="Enter your password" required>
                <i class="fas fa-eye-slash toggle-password" onclick="togglePassword('password')"></i>
            </div>
            <div id="confirm-field" class="input-group" style="display:none;">
                <label for="confirm">Confirm Password</label>
                <input type="password" id="confirm" placeholder="Confirm your password" required>
                <i class="fas fa-eye-slash toggle-password" onclick="togglePassword('confirm')"></i>
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

    <!-- Trang Quên Mật Khẩu -->
    <div id="forgot-page" class="container" style="display:none;">
        <h1>Khôi Phục Mật Khẩu</h1>
        <div id="forgot-alert" class="alert-box"></div>
        <div class="forgot-form"
