<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shop Thời Trang - Đăng Nhập & Mua Sắm</title>
    
    <!-- Font Poppins đẹp -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Icon Font Awesome -->
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
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transition: background 0.5s;
        }

        .container {
            position: relative;
            width: 420px;
            backdrop-filter: blur(20px);
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px 35px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
            color: white;
        }

        h2 {
            font-size: 32px;
            margin-bottom: 30px;
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .input-box {
            position: relative;
            margin: 25px 0;
        }

        .input-box input {
            width: 100%;
            padding: 15px 20px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            outline: none;
            border-radius: 50px;
            color: white;
            font-size: 16px;
        }

        .input-box input::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }

        .input-box i {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: white;
            font-size: 20px;
        }

        button {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, #ff6b6b, #f06595);
            border: none;
            border-radius: 50px;
            color: white;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            transition: 0.4s;
            margin-top: 10px;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }

        .links {
            margin-top: 30px;
            color: rgba(255, 255, 255, 0.8);
        }

        .links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
        }

        .links a:hover {
            text-decoration: underline;
        }

        /* Trang shop */
        .shop {
            display: none;
        }

        header {
            margin-bottom: 30px;
        }

        .user-info {
            margin-top: 20px;
            font-size: 16px;
        }

        .logout-btn {
            width: auto;
            padding: 10px 20px;
            font-size: 14px;
            margin-left: 15px;
        }

        .products-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 20px;
            max-height: 60vh;
            overflow-y: auto;
            padding: 10px;
        }

        .product {
            background: rgba(255,255,255,0.15);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: 0.3s;
        }

        .product:hover {
            transform: scale(1.05);
            background: rgba(255,255,255,0.25);
        }

        .product img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            background: #ccc;
        }

        .product h3 {
            margin: 15px 0 10px;
            font-size: 18px;
        }

        .product p {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .cart-link {
            display: inline-block;
            margin-top: 20px;
            color: white;
            font-size: 18px;
        }
    </style>
</head>
<body>

    <!-- Trang Đăng Nhập / Đăng Ký -->
    <div class="container" id="auth-container">
        <div id="login-form">
            <h2>Đăng Nhập</h2>
            <div class="input-box">
                <input type="text" id="login-identifier" placeholder="Tên đăng nhập hoặc Email" required>
                <i class="fas fa-user"></i>
            </div>
            <div class="input-box">
                <input type="password" id="login-password" placeholder="Mật khẩu" required>
                <i class="fas fa-lock"></i>
            </div>
            <button onclick="handleLogin()">Đăng Nhập</button>
            <div class="links">
                <p>Chưa có tài khoản? <a href="#" onclick="showRegister()">Đăng ký ngay</a></p>
            </div>
        </div>

        <div id="register-form" style="display: none;">
            <h2>Đăng Ký</h2>
            <div class="input-box">
                <input type="text" id="reg-username" placeholder="Tên đăng nhập" required>
                <i class="fas fa-user"></i>
            </div>
            <div class="input-box">
                <input type="email" id="reg-email" placeholder="Email" required>
                <i class="fas fa-envelope"></i>
            </div>
            <div class="input-box">
                <input type="password" id="reg-password" placeholder="Mật khẩu" required>
                <i class="fas fa-lock"></i>
            </div>
            <div class="input-box">
                <input type="password" id="reg-confirm" placeholder="Xác nhận mật khẩu" required>
                <i class="fas fa-lock"></i>
            </div>
            <button onclick="handleRegister()">Đăng Ký</button>
            <div class="links">
                <p>Đã có tài khoản? <a href="#" onclick="showLogin()">Đăng nhập</a></p>
            </div>
        </div>
    </div>

    <!-- Trang Shop (ẩn lúc đầu) -->
    <div class="container shop" id="shop-container" style="display: none;">
        <header>
            <h2>🛒 Shop Thời Trang Đẹp</h2>
            <div class="user-info">
                Xin chào, <strong id="username-display"></strong>!
                <button class="logout-btn" onclick="logout()">Đăng xuất</button>
            </div>
        </header>

        <div class="products-container" id="products-list"></div>

        <a href="#" class="cart-link" onclick="alert('Giỏ hàng hiện có ' + getCartCount() + ' sản phẩm!')">Xem giỏ hàng (<span id="cart-count">0</span>)</a>
    </div>

    <script>
        // Dữ liệu sản phẩm mẫu
        const products = [
            { id: 1, name: "Áo Thun Trắng Cool", price: 250000, img: "https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?w=400" },
            { id: 2, name: "Quần Jeans Xanh", price: 450000, img: "https://images.unsplash.com/photo-1542272604-787c167f29fd?w=400" },
            { id: 3, name: "Giày Sneaker Đen", price: 800000, img: "https://images.unsplash.com/photo-1549298916-b41d501d3772?w=400" },
            { id: 4, name: "Túi Xách Da", price: 350000, img: "https://images.unsplash.com/photo-1553062407-98eeb964ef76?w=400" },
            { id: 5, name: "Đồng Hồ Thể Thao", price: 1200000, img: "https://images.unsplash.com/photo-1524592099759-9e9a54a055d2?w=400" },
            { id: 6, name: "Mũ Lưỡi Trai", price: 150000, img: "https://images.unsplash.com/photo-1588854337236-6889d6319048?w=400" }
        ];

        let cart = JSON.parse(localStorage.getItem('cart')) || [];

        // Xử lý đăng ký
        function handleRegister() {
            const username = document.getElementById('reg-username').value.trim();
            const email = document.getElementById('reg-email').value.trim();
            const password = document.getElementById('reg-password').value;
            const confirm = document.getElementById('reg-confirm').value;

            if (!username || !email || !password) {
                alert("Vui lòng điền đầy đủ!");
                return;
            }
            if (password !== confirm) {
                alert("Mật khẩu không trùng khớp!");
                return;
            }

            let users = JSON.parse(localStorage.getItem('users')) || [];
            if (users.find(u => u.username === username || u.email === email)) {
                alert("Tên đăng nhập hoặc email đã tồn tại!");
                return;
            }

            users.push({ username, email, password });
            localStorage.setItem('users', JSON.stringify(users));
            alert("Đăng ký thành công! Đang chuyển sang đăng nhập...");
            showLogin();
        }

        // Xử lý đăng nhập
        function handleLogin() {
            const identifier = document.getElementById('login-identifier').value.trim();
            const password = document.getElementById('login-password').value;

            let users = JSON.parse(localStorage.getItem('users')) || [];
            let user = users.find(u => (u.username === identifier || u.email === identifier) && u.password === password);

            if (user) {
                localStorage.setItem('currentUser', JSON.stringify(user));
                showShop(user.username);
            } else {
                alert("Sai tên đăng nhập/email hoặc mật khẩu!");
            }
        }

        // Hiển thị trang đăng ký
        function showRegister() {
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('register-form').style.display = 'block';
        }

        // Hiển thị trang đăng nhập
        function showLogin() {
            document.getElementById('register-form').style.display = 'none';
            document.getElementById('login-form').style.display = 'block';
        }

        // Hiển thị shop
        function showShop(username) {
            document.getElementById('auth-container').style.display = 'none';
            document.getElementById('shop-container').style.display = 'block';
            document.getElementById('username-display').textContent = username;

            displayProducts();
            updateCartCount();
        }

        // Đăng xuất
        function logout() {
            localStorage.removeItem('currentUser');
            document.getElementById('shop-container').style.display = 'none';
            document.getElementById('auth-container').style.display = 'block';
            showLogin();
            document.getElementById('login-identifier').value = '';
            document.getElementById('login-password').value = '';
        }

        // Hiển thị sản phẩm
        function displayProducts() {
            const container = document.getElementById('products-list');
            container.innerHTML = products.map(p => `
                <div class="product">
                    <img src="\( {p.img}" alt=" \){p.name}">
                    <h3>${p.name}</h3>
                    <p>${p.price.toLocaleString('vi-VN')} ₫</p>
                    <button onclick="addToCart(${p.id})">Thêm vào giỏ</button>
                </div>
            `).join('');
        }

        // Thêm vào giỏ
        function addToCart(id) {
            const product = products.find(p => p.id === id);
            const existing = cart.find(item => item.id === id);
            if (existing) existing.quantity += 1;
            else cart.push({ ...product, quantity: 1 });

            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartCount();
            alert("Đã thêm " + product.name + " vào giỏ hàng!");
        }

        // Cập nhật số lượng giỏ hàng
        function updateCartCount() {
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            document.getElementById('cart-count').textContent = count;
        }

        function getCartCount() {
            return cart.reduce((total, item) => total + item.quantity, 0);
        }

        // Kiểm tra nếu đã đăng nhập thì vào thẳng shop
        window.onload = function() {
            const currentUser = localStorage.getItem('currentUser');
            if (currentUser) {
                const user = JSON.parse(currentUser);
                showShop(user.username);
            }
        }
    </script>
</body>
</html>
