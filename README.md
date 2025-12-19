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
            transition: background 0.5s ease;
        }
        body::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.45); z-index: -1;
            transition: background 0.5s ease;
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
            animation: fadeIn 0.8s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
        h1 {
            font-size: 36px;
            font-weight: 500;
            margin-bottom: 40px;
            letter-spacing: 1px;
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        .input-group {
            position: relative;
            margin-bottom: 30px;
            text-align: left;
            animation: slideIn 0.5s ease forwards;
            opacity: 0;
        }
        .input-group:nth-child(1) { animation-delay: 0.1s; }
        .input-group:nth-child(2) { animation-delay: 0.2s; }
        .input-group:nth-child(3) { animation-delay: 0.3s; }
        .input-group:nth-child(4) { animation-delay: 0.4s; }
        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }
        .input-group label {
            display: block;
            font-size: 14px;
            color: rgba(255,255,255,0.8);
            margin-bottom: 8px;
            transition: color 0.3s ease;
        }
        .input-group input {
            width: 100%;
            padding: 12px 45px 12px 40px;
            background: transparent;
            border: none;
            border-bottom: 1px solid rgba(255, 255, 255, 0.6);
            color: #fff;
            font-size: 16px;
            transition: border-bottom 0.3s ease, padding-bottom 0.3s ease;
        }
        .input-group input:focus {
            border-bottom: 2px solid #fff;
            padding-bottom: 11px;
            outline: none;
        }
        .input-group input::placeholder { color: rgba(255, 255, 255, 0.7); font-style: italic; }
        .input-icon {
            position: absolute;
            left: 0;
            bottom: 12px;
            color: rgba(255,255,255,0.7);
            font-size: 18px;
            transition: color 0.3s ease;
        }
        .input-group input:focus + .input-icon {
            color: #fff;
        }
        .toggle-password {
            position: absolute;
            right: 0;
            bottom: 12px;
            color: rgba(255,255,255,0.7);
            cursor: pointer;
            font-size: 18px;
            transition: color 0.3s ease, transform 0.3s ease;
        }
        .toggle-password:hover {
            color: #fff;
            transform: scale(1.1);
        }
        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 20px 0 30px;
            font-size: 14px;
            animation: fadeIn 0.5s ease 0.5s forwards;
            opacity: 0;
        }
        .options label { display: flex; align-items: center; cursor: pointer; transition: color 0.3s ease; }
        .options label:hover { color: #ddd; }
        .options input[type="checkbox"] { margin-right: 8px; accent-color: #fff; transition: transform 0.3s ease; }
        .options input[type="checkbox"]:checked { transform: scale(1.1); }
        .forgot { color: rgba(255,255,255,0.8); text-decoration: none; cursor: pointer; transition: color 0.3s ease, text-decoration 0.3s ease; }
        .forgot:hover { color: #fff; text-decoration: underline; }
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
            transition: background 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeIn 0.5s ease 0.6s forwards;
            opacity: 0;
        }
        .btn:hover { background: #f0f0f0; transform: translateY(-3px); box-shadow: 0 5px 15px rgba(255,255,255,0.3); }
        .switch {
            margin-top: 25px;
            font-size: 14px;
            animation: fadeIn 0.5s ease 0.7s forwards;
            opacity: 0;
        }
        .switch a { color: #fff; text-decoration: none; font-weight: 500; cursor: pointer; transition: color 0.3s ease; }
        .switch a:hover { color: #ddd; text-decoration: underline; }

        /* Trang Dashboard */
        #dashboard {
            display: none;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
            position: fixed;
            top: 0; left: 0;
            overflow-y: auto;
            animation: fadeIn 0.8s ease;
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
            transition: background 0.3s ease;
        }
        .dashboard-header:hover { background: rgba(0, 0, 0, 0.6); }
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: #fff;
            letter-spacing: 1px;
            cursor: pointer;
            transition: color 0.3s ease, transform 0.3s ease;
        }
        .logo:hover { color: #00ffaa; transform: scale(1.05); }
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
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .avatar:hover { transform: rotate(360deg); box-shadow: 0 0 20px rgba(0, 255, 170, 0.7); }
        .username {
            font-size: 18px;
            font-weight: 500;
            color: #fff;
            text-shadow: 0 0 5px #000;
            cursor: pointer;
            transition: color 0.3s ease;
        }
        .username:hover { color: #00ffaa; }
        .logout-btn {
            background: #ff4d4d;
            padding: 10px 25px;
            border-radius: 25px;
            color: #fff;
            cursor: pointer;
            font-size: 14px;
            transition: background 0.3s ease, transform 0.3s ease;
        }
        .logout-btn:hover { background: #ff1a1a; transform: scale(1.05); }
        .dashboard-content {
            padding: 60px 40px;
            color: #fff;
            text-align: center;
            animation: slideUp 0.5s ease;
        }
        @keyframes slideUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .dashboard-content h2 {
            font-size: 42px;
            margin-bottom: 30px;
            letter-spacing: 1px;
            text-shadow: 0 0 10px #000;
            animation: glow 2s ease infinite alternate;
        }
        @keyframes glow {
            from { text-shadow: 0 0 10px #000; }
            to { text-shadow: 0 0 20px #00ffaa; }
        }
        .dashboard-content p {
            font-size: 18px;
            margin-bottom: 40px;
            color: #ddd;
            transition: color 0.3s ease;
        }
        .dashboard-content p:hover { color: #fff; }
        .search-bar {
            width: 60%;
            margin: 0 auto 40px;
            position: relative;
            animation: fadeIn 0.5s ease 0.2s forwards;
            opacity: 0;
        }
        .search-bar input {
            width: 100%;
            padding: 15px 50px 15px 20px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 30px;
            color: #fff;
            font-size: 16px;
            transition: border 0.3s ease, box-shadow 0.3s ease;
        }
        .search-bar input:focus {
            border: 1px solid #00ffaa;
            box-shadow: 0 0 15px rgba(0, 255, 170, 0.3);
            outline: none;
        }
        .search-bar i {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: #ddd;
            cursor: pointer;
            transition: color 0.3s ease;
        }
        .search-bar i:hover { color: #00ffaa; }
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
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: productFadeIn 0.5s ease forwards;
            opacity: 0;
        }
        .product:nth-child(1) { animation-delay: 0.1s; }
        .product:nth-child(2) { animation-delay: 0.2s; }
        .product:nth-child(3) { animation-delay: 0.3s; }
        @keyframes productFadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
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
            transition: transform 0.3s ease;
        }
        .product img:hover {
            transform: scale(1.05);
        }
        .product h3 { 
            font-size: 22px; 
            margin-bottom: 15px; 
            color: #fff; 
            transition: color 0.3s ease;
        }
        .product h3:hover { color: #00ffaa; }
        .product p { 
            font-size: 15px; 
            color: #ccc; 
            margin-bottom: 20px; 
            line-height: 1.5;
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
            cursor: pointer;
            font-weight: 500;
            transition: background 0.3s ease, transform 0.3s ease;
        }
        .buy-btn:hover { 
            background: #00cc88; 
            transform: scale(1.05); 
        }
        .add-to-cart {
            background: #ffaa00;
            color: #000;
            padding: 12px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 500;
            margin-top: 10px;
            transition: background 0.3s ease, transform 0.3s ease;
        }
        .add-to-cart:hover { 
            background: #ff8800; 
            transform: scale(1.05); 
        }
        .wishlist-btn {
            background: #ff69b4;
            color: #000;
            padding: 12px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 500;
            margin-top: 10px;
            transition: background 0.3s ease, transform 0.3s ease;
        }
        .wishlist-btn:hover { 
            background: #ff1493; 
            transform: scale(1.05); 
        }
        .review-section {
            margin-top: 20px;
        }
        .review-input {
            width: 100%;
            padding: 10px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            color: #fff;
            margin-bottom: 10px;
        }
        .submit-review {
            background: #4caf50;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
        }
        .submit-review:hover { background: #3e8e41; }
        .reviews-list {
            margin-top: 15px;
            max-height: 200px;
            overflow-y: auto;
        }
        .review {
            background: rgba(0, 0, 0, 0.2);
            padding: 10px;
            border-radius: 10px;
            margin-bottom: 10px;
        }
        .review p { margin: 0; color: #ddd; }
        /* Trang Thanh Toán */
        #payment-page {
            display: none;
            padding: 80px 40px;
            color: #fff;
            max-width: 900px;
            margin: 0 auto;
            animation: fadeIn 0.5s ease;
        }
        .payment-header {
            text-align: center;
            margin-bottom: 50px;
            font-size: 36px;
            text-shadow: 0 0 10px #000;
        }
        .payment-summary {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 50px;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.2);
        }
        .payment-items {
            max-height: 400px;
            overflow-y: auto;
            margin-bottom: 30px;
            padding-right: 20px;
        }
        .payment-item {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            border-bottom: 1px solid rgba(255,255,255,0.2);
            transition: background 0.3s ease;
        }
        .payment-item:hover {
            background: rgba(255,255,255,0.05);
        }
        .payment-item span:first-child {
            flex: 2;
            font-size: 18px;
        }
        .payment-item span:last-child {
            font-size: 18px;
            color: #00ffaa;
        }
        .payment-total {
            font-size: 28px;
            text-align: right;
            margin-top: 20px;
            color: #00ffaa;
            text-shadow: 0 0 5px #000;
        }
        .payment-methods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }
        .method {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            cursor: pointer;
            transition: border 0.3s ease, background 0.3s ease, transform 0.3s ease;
            border: 2px solid transparent;
            animation: methodFadeIn 0.5s ease forwards;
            opacity: 0;
        }
        .method:nth-child(1) { animation-delay: 0.1s; }
        .method:nth-child(2) { animation-delay: 0.2s; }
        .method:nth-child(3) { animation-delay: 0.3s; }
        @keyframes methodFadeIn {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }
        .method:hover, .method.selected {
            border: 2px solid #00ffaa;
            background: rgba(0, 255, 170, 0.15);
            transform: translateY(-5px);
        }
        .method i {
            font-size: 48px;
            margin-bottom: 20px;
            transition: color 0.3s ease;
        }
        .method:hover i {
            color: #00ffaa;
        }
        .method p {
            font-size: 18px;
            font-weight: 500;
        }
        .payment-form {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px;
            margin-top: 20px;
            display: none;
            animation: formFadeIn 0.5s ease;
        }
        @keyframes formFadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .qr-code {
            width: 220px;
            height: 220px;
            margin: 30px auto;
            background: #fff url('https://api.qrserver.com/v1/create-qr-code/?size=220x220&data=ExamplePayment') center/cover;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            transition: transform 0.3s ease;
        }
        .qr-code:hover {
            transform: scale(1.05);
        }
        .payment-info p {
            margin-bottom: 15px;
            font-size: 16px;
            color: #ddd;
        }
        .payment-info strong {
            color: #fff;
        }
        .copy-btn {
            background: #00ffaa;
            color: #000;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            margin-left: 10px;
            font-size: 14px;
            transition: background 0.3s ease;
        }
        .copy-btn:hover { background: #00cc88; }
        .confirm-payment {
            background: #4caf50;
            color: #fff;
            padding: 18px;
            border: none;
            border-radius: 30px;
            width: 100%;
            font-size: 18px;
            cursor: pointer;
            transition: background 0.3s ease, transform 0.3s ease;
            margin-top: 40px;
        }
        .confirm-payment:hover {
            background: #3e8e41;
            transform: translateY(-3px);
        }
        .back-cart {
            margin-top: 30px;
            color: #ccc;
            cursor: pointer;
            font-size: 16px;
            transition: color 0.3s ease;
        }
        .back-cart:hover {
            color: #fff;
            text-decoration: underline;
        }
        /* Modal Xác Nhận Thanh Toán */
        #payment-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 100;
            justify-content: center;
            align-items: center;
            animation: modalFadeIn 0.5s ease;
        }
        @keyframes modalFadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .modal-content {
            background: #fff;
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            color: #222;
            max-width: 500px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.4);
            animation: modalScaleIn 0.5s ease;
        }
        @keyframes modalScaleIn {
          
