<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketModVn - Đăng Nhập & Đăng Ký</title>
    <!-- Font Roboto -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/9.6.10/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.6.10/firebase-auth.js"></script>
    <style>
        :root {
            --primary: #00ffaa;
            --secondary: #ffaa00;
            --bg-dark: #0f0c29;
            --text: #fff;
            --text-sec: #ccc;
            --glass: rgba(255, 255, 255, 0.08);
            --border: rgba(255, 255, 255, 0.15);
            --shadow: 0 10px 30px rgba(0,0,0,0.5);
            --trans: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', sans-serif;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, var(--bg-dark), #302b63, #24243e);
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        #particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .container {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--border);
            border-radius: 25px;
            padding: 50px;
            width: 420px;
            box-shadow: var(--shadow);
            text-align: center;
            animation: fadeIn 1s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .logo {
            font-size: 32px;
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 20px;
            text-shadow: 0 0 10px var(--primary);
        }

        h2 {
            font-size: 26px;
            color: var(--text);
            margin-bottom: 40px;
        }

        .input-box {
            position: relative;
            margin-bottom: 30px;
        }

        .input-box input {
            width: 100%;
            padding: 15px 45px 15px 50px;
            background: transparent;
            border: 1px solid var(--border);
            border-radius: 50px;
            color: var(--text);
            font-size: 16px;
            transition: var(--trans);
        }

        .input-box input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 15px rgba(0,255,170,0.3);
        }

        .input-box i {
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-sec);
        }

        .password-toggle {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-sec);
            cursor: pointer;
        }

        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            font-size: 14px;
        }

        .forgot {
            color: var(--text-sec);
            cursor: pointer;
        }

        .btn {
            width: 100%;
            padding: 15px;
            background: var(--primary);
            border: none;
            border-radius: 50px;
            color: #000;
            font-weight: 500;
            cursor: pointer;
            transition: var(--trans);
            margin-bottom: 20px;
        }

        .btn:hover {
            background: #00cc88;
            transform: translateY(-3px);
        }

        .social-btn {
            width: 100%;
            padding: 15px;
            border-radius: 50px;
            margin-bottom: 15px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text);
            transition: var(--trans);
        }

        .google { background: #4285f4; }
        .facebook { background: #1877f2; }
        .apple { background: #000; }

        .social-btn:hover { transform: translateY(-3px); }

        .switch {
            text-align: center;
            color: var(--text-sec);
        }

        .switch a {
            color: var(--primary);
            cursor: pointer;
        }

        #dashboard {
            display: none;
            text-align: center;
            color: var(--text);
            padding: 50px;
        }

        .alert {
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            display: none;
        }

        .error { background: rgba(255,0,0,0.3); }
        .success { background: rgba(0,255,0,0.3); }

        /* Responsive */
        @media (max-width: 480px) {
            .container {
                width: 90%;
                padding: 40px 30px;
            }
        }
    </style>
</head>
<body>

    <!-- Particles -->
    <canvas id="particles"></canvas>

    <!-- Auth Container -->
    <div class="container" id="auth">
        <div class="logo">MarketModVn</div>
        <h2 id="title">Đăng Nhập</h2>
        <div id="alert" class="alert"></div>

        <div class="input-box">
            <input type="text" id="username" placeholder=" " style="display:none;" required>
            <i class="fas fa-user"></i>
        </div>

        <div class="input-box">
            <input type="email" id="email" placeholder=" " required>
            <i class="fas fa-envelope"></i>
        </div>

        <div class="input-box">
            <input type="password" id="password" placeholder=" " required>
            <i class="fas fa-lock"></i>
            <i class="fas fa-eye-slash password-toggle" onclick="togglePass('password', this)"></i>
        </div>

        <div class="input-box" id="confirm-box" style="display:none;">
            <input type="password" id="confirm" placeholder=" " required>
            <i class="fas fa-lock"></i>
            <i class="fas fa-eye-slash password-toggle" onclick="togglePass('confirm', this)"></i>
        </div>

        <div class="options">
            <label><input type="checkbox" id="remember"> Nhớ tài khoản</label>
            <span class="forgot" onclick="forgotPass()">Quên mật khẩu?</span>
        </div>

        <button class="btn" id="auth-btn" onclick="handleAuth()">Đăng Nhập</button>

        <button class="social-btn google" onclick="loginWith('google')">
            <i class="fab fa-google"></i> Google
        </button>
        <button class="social-btn facebook" onclick="loginWith('facebook')">
            <i class="fab fa-facebook-f"></i> Facebook
        </button>
        <button class="social-btn apple" onclick="loginWith('apple')">
            <i class="fab fa-apple"></i> Apple
        </button>

        <div class="switch">
            Chưa có tài khoản? <a onclick="switchForm()">Đăng ký</a>
        </div>
    </div>

    <!-- Dashboard Demo -->
    <div id="dashboard" style="display:none;">
        <h2>Chào mừng, <span id="user-name"></span>!</h2>
        <p>Bạn đã đăng nhập thành công. Đây là dashboard.</p>
        <button class="btn" onclick="logout()">Đăng xuất</button>
    </div>

    <script>
        // Firebase config (tùy chỉnh với project của bạn)
        const firebaseConfig = {
            apiKey: "AIzaSyB6wO5W1Y3gY8x7Q3qO4y5r6Y7s8t9u0v", // Thay bằng API Key của bạn
            authDomain: "your-project.firebaseapp.com",
            projectId: "your-project",
            storageBucket: "your-project.appspot.com",
            messagingSenderId: "1234567890",
            appId: "1:1234567890:web:abcde1234567890"
        };
        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth();

        let isRegister = false;

        function switchForm() {
            isRegister = !isRegister;
            document.getElementById('title').textContent = isRegister ? 'Đăng Ký' : 'Đăng Nhập';
            document.getElementById('auth-btn').textContent = isRegister ? 'Đăng Ký' : 'Đăng Nhập';
            document.getElementById('username').style.display = isRegister ? 'block' : 'none';
            document.getElementById('confirm-box').style.display = isRegister ? 'block' : 'none';
            document.getElementById('switch').innerHTML = isRegister 
                ? 'Đã có tài khoản? <a onclick="switchForm()">Đăng nhập</a>'
                : 'Chưa có tài khoản? <a onclick="switchForm()">Đăng ký</a>';
            hideAlert();
        }

        function togglePass(id, icon) {
            const field = document.getElementById(id);
            if (field.type === 'password') {
                field.type = 'text';
                icon.classList.replace('fa-eye-slash', 'fa-eye');
            } else {
                field.type = 'password';
                icon.classList.replace('fa-eye', 'fa-eye');
            }
        }

        function handleAuth() {
            const username = isRegister ? document.getElementById('username').value.trim() : '';
            const email = document.getElementById('email').value.trim();
            const password = document.getElementById('password').value;
            const confirm = isRegister ? document.getElementById('confirm').value : '';

            if (isRegister && username.length < 4) return showAlert('Username ít nhất 4 ký tự!');
            if (!email || !/^\S+@\S+\.\S+$/.test(email)) return showAlert('Email không hợp lệ!');
            if (!password || password.length < 6) return showAlert('Mật khẩu ít nhất 6 ký tự!');
            if (isRegister && password !== confirm) return showAlert('Mật khẩu không khớp!');

            if (isRegister) {
                auth.createUserWithEmailAndPassword(email, password)
                    .then(userCredential => {
                        userCredential.user.updateProfile({ displayName: username });
                        showAlert('Đăng ký thành công!', 'success');
                        switchForm();
                    })
                    .catch(error => showAlert(error.message));
            } else {
                auth.signInWithEmailAndPassword(email, password)
                    .then(userCredential => {
                        showAlert('Đăng nhập thành công!', 'success');
                        showDashboard(userCredential.user);
                    })
                    .catch(error => showAlert(error.message));
            }
        }

        function loginWith(providerName) {
            let provider;
            if (providerName === 'google') provider = new firebase.auth.GoogleAuthProvider();
            else if (providerName === 'facebook') provider = new firebase.auth.FacebookAuthProvider();
            else if (providerName === 'apple') provider = new firebase.auth.OAuthProvider('apple.com');
            else return;

            auth.signInWithPopup(provider)
                .then(userCredential => {
                    showAlert('Đăng nhập thành công!', 'success');
                    showDashboard(userCredential.user);
                })
                .catch(error => showAlert(error.message));
        }

        function forgotPass() {
            const email = prompt('Nhập email để reset mật khẩu:');
            if (email && /^\S+@\S+\.\S+$/.test(email)) {
                auth.sendPasswordResetEmail(email)
                    .then(() => showAlert('Link reset đã gửi đến email!', 'success'))
                    .catch(error => showAlert(error.message));
            } else {
                showAlert('Email không hợp lệ!');
            }
        }

        function showDashboard(user) {
            document.getElementById('auth').style.display = 'none';
            document.getElementById('dashboard').style.display = 'block';
            document.getElementById('user-name').textContent = user.displayName || user.email.split('@')[0];
        }

        function logout() {
            auth.signOut().then(() => {
                document.getElementById('dashboard').style.display = 'none';
                document.getElementById('auth').style.display = 'block';
                showAlert('Đăng xuất thành công!', 'success');
            }).catch(error => showAlert(error.message));
        }

        function showAlert(msg, type = 'error') {
            const alert = document.getElementById('alert');
            alert.className = 'alert ' + type;
            alert.textContent = msg;
            alert.style.display = 'block';
            setTimeout(() => alert.style.display = 'none', 3000);
        }

        function hideAlert() {
            document.getElementById('alert').style.display = 'none';
        }

        // Particles
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
                ctx.fillStyle = 'rgba(0, 255, 170, 0.8)';
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

        // Remember me
        if (localStorage.getItem('rememberEmail')) {
            document.getElementById('email').value = localStorage.getItem('rememberEmail');
            document.getElementById('remember').checked = true;
        }
    </script>
</body>
</html>
