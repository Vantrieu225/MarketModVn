<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NeoGear Ultimate - Gaming Shop Pro</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&family=Rajdhani:wght@500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
  <style>
    :root {
      --bg: #0a0a14;
      --card: #15152a;
      --accent: #00ffff;
      --accent2: #ff00ff;
      --text: #e0e0e0;
      --gold: #ffd700;
    }
    * { margin:0; padding:0; box-sizing:border-box; }
    body { background:var(--bg); color:var(--text); font-family:'Rajdhani',sans-serif; min-height:100vh; position:relative; }
    canvas#particles { position:fixed; top:0; left:0; z-index:-1; width:100%; height:100%; }
    header { position:fixed; top:0; left:0; right:0; background:rgba(10,10,20,0.95); backdrop-filter:blur(10px); z-index:1000; padding:1rem 5%; display:flex; align-items:center; justify-content:space-between; }
    .logo { font-family:'Orbitron',sans-serif; font-size:2.2rem; color:var(--accent); text-shadow:0 0 20px var(--accent); }
    nav ul { display:flex; gap:2rem; list-style:none; }
    nav a { color:var(--text); font-weight:600; transition:0.3s; }
    nav a:hover { color:var(--accent); text-shadow:0 0 10px var(--accent); }
    .user-menu { display:flex; gap:1rem; align-items:center; }
    .rank-badge { background:var(--accent2); padding:0.3rem 0.8rem; border-radius:20px; font-size:0.9rem; }
    .cart-icon { position:relative; font-size:1.8rem; cursor:pointer; }
    .cart-badge { position:absolute; top:-10px; right:-10px; background:var(--accent2); color:#000; width:26px; height:26px; border-radius:50%; display:flex; align-items:center; justify-content:center; }
    .hero { height:100vh; display:flex; flex-direction:column; align-items:center; justify-content:center; text-align:center; }
    .hero h1 { font-family:'Orbitron',sans-serif; font-size:5rem; background:linear-gradient(45deg,var(--accent),var(--accent2)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; }
    .search-bar { margin:2rem 5%; display:flex; max-width:600px; }
    .search-bar input { flex:1; padding:1rem; background:var(--card); border:none; color:var(--text); border-radius:30px 0 0 30px; }
    .search-bar button { padding:1rem 2rem; background:var(--accent); border:none; border-radius:0 30px 30px 0; cursor:pointer; }
    .tabs { display:flex; justify-content:center; gap:1rem; margin:2rem 0; flex-wrap:wrap; }
    .tab-btn { padding:0.8rem 2rem; background:var(--card); border:2px solid var(--accent); border-radius:30px; cursor:pointer; transition:0.3s; }
    .tab-btn.active { background:var(--accent); color:#000; }
    .products-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); gap:2rem; padding:0 5%; }
    .product-card { background:var(--card); border-radius:15px; overflow:hidden; transition:0.5s; cursor:pointer; position:relative; }
    .product-card:hover { transform:translateY(-20px) scale(1.05); box-shadow:0 0 50px rgba(0,255,255,0.5); }
    .product-card::after { content:''; position:absolute; inset:0; background:linear-gradient(45deg,transparent,var(--accent),transparent); opacity:0; transition:0.5s; pointer-events:none; }
    .product-card:hover::after { opacity:0.3; animation:glitch 2s infinite; }
    @keyframes glitch { 0% { transform:translate(0); } 20% { transform:translate(-5px,5px); } 40% { transform:translate(5px,-5px); } 60% { transform:translate(-5px,-5px); } 80% { transform:translate(5px,5px); } }
    .product-img { width:100%; height:300px; object-fit:cover; transition:0.5s; }
    .product-card:hover .product-img { transform:scale(1.1); }
    .rating { color:#ffd700; }
    .modal { display:none; position:fixed; inset:0; background:rgba(0,0,0,0.95); z-index:2000; align-items:center; justify-content:center; }
    .modal-content { background:var(--card); padding:2rem; border-radius:20px; width:90%; max-width:800px; max-height:90vh; overflow-y:auto; }
    #liveChat { position:fixed; bottom:20px; right:20px; width:380px; background:var(--card); border-radius:15px; box-shadow:0 0 20px var(--accent); display:none; flex-direction:column; }
    #chatHeader { background:var(--accent); padding:1rem; color:#000; font-weight:bold; border-radius:15px 15px 0 0; cursor:pointer; }
    #chatMessages { flex:1; padding:1rem; overflow-y:auto; max-height:400px; }
    #chatInput { display:flex; padding:1rem; background:var(--card); border-radius:0 0 15px 15px; }
    #chatInput input { flex:1; padding:1rem; background:transparent; border:1px solid var(--accent); border-radius:30px; color:var(--text); }
    #chatInput button { margin-left:1rem; padding:0 1.5rem; background:var(--accent); border:none; border-radius:30px; cursor:pointer; }
    .giveaway-btn { position:fixed; bottom:80px; left:20px; background:var(--accent2); padding:1.5rem; border-radius:50px; cursor:pointer; animation:pulse 2s infinite; font-size:1.5rem; }
    @keyframes pulse { 0% { box-shadow:0 0 0 0 rgba(255,0,255,0.7); } 70% { box-shadow:0 0 0 30px rgba(255,0,255,0); } }
  </style>
</head>
<body>
  <canvas id="particles"></canvas>

  <header>
    <div class="logo">NeoGear Ultimate</div>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#shop">Shop</a></li>
        <li><a href="#giveaway">Giveaway</a></li>
      </ul>
    </nav>
    <div class="user-menu" id="userMenu"></div>
    <div class="cart-icon" id="cartIcon"><i class="fas fa-shopping-cart"></i><span class="cart-badge" id="cartBadge">0</span></div>
  </header>

  <section class="hero" id="home">
    <h1>NEO GEAR ULTIMATE</h1>
    <p>Shop gaming pro nhất Việt Nam - Member exclusive, live chat, giveaway hàng ngày!</p>
  </section>

  <div class="search-bar">
    <input type="text" id="searchInput" placeholder="Tìm kiếm sản phẩm...">
    <button onclick="searchProducts()"><i class="fas fa-search"></i></button>
  </div>

  <div class="tabs" id="categoryTabs"></div>

  <section class="products-grid" id="productsGrid"></section>

  <!-- Modals -->
  <div class="modal" id="authModal"></div>
  <div class="modal" id="productModal"></div>
  <div class="modal" id="cartModal"></div>
  <div class="modal" id="checkoutModal"></div>
  <div class="modal" id="profileModal"></div>
  <div class="modal" id="adminModal"></div>
  <div class="modal" id="giveawayModal"></div>

  <!-- Live Chat -->
  <div id="liveChat">
    <div id="chatHeader" onclick="toggleChat()">Live Chat Gaming <i class="fas fa-times" style="float:right;"></i></div>
    <div id="chatMessages"></div>
    <div id="chatInput">
      <input type="text" id="chatText" placeholder="Chat với anh em gamer...">
      <button onclick="sendMessage()"><i class="fas fa-paper-plane"></i></button>
    </div>
  </div>

  <div class="giveaway-btn" onclick="toggleChat()"><i class="fas fa-comment-dots"></i></div>
  <div class="giveaway-btn" style="bottom:140px; background:var(--accent);" onclick="openGiveaway()"><i class="fas fa-gift"></i> Giveaway</div>

  <!-- Firebase -->
  <script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-auth-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-firestore-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-database-compat.js"></script>

  <script>
    // === THAY CONFIG CỦA BẠN VÀO ĐÂY ===
    const firebaseConfig = {
      apiKey: "YOUR_API_KEY",
      authDomain: "YOUR_PROJECT.firebaseapp.com",
      projectId: "YOUR_PROJECT",
      storageBucket: "YOUR_PROJECT.appspot.com",
      messagingSenderId: "YOUR_SENDER_ID",
      appId: "YOUR_APP_ID"
    };
    firebase.initializeApp(firebaseConfig);
    const db = firebase.firestore();
    const rtdb = firebase.database();
    const auth = firebase.auth();

    let currentUser = null;
    let allProducts = [];
    const categories = ["Tất cả", "Chuột", "Bàn phím", "Tai nghe", "Ghế gaming", "Merchandise"];

    // Particles
    const canvas = document.getElementById('particles');
    canvas.width = innerWidth; canvas.height = innerHeight;
    const ctx = canvas.getContext('2d');
    const particles = [];
    for(let i=0;i<150;i++) particles.push({x:Math.random()*canvas.width,y:Math.random()*canvas.height,r:Math.random()*4+1,s:Math.random()*0.5+0.2,c:`hsl(${Math.random()*360},100%,50%)`});
    function animate(){ ctx.clearRect(0,0,canvas.width,canvas.height); particles.forEach(p=>{ p.y += p.s; if(p.y>canvas.height) p.y=0; ctx.fillStyle=p.c; ctx.beginPath(); ctx.arc(p.x,p.y,p.r,0,Math.PI*2); ctx.fill(); }); requestAnimationFrame(animate); }
    animate();

    // Sounds
    const sounds = {
      click: new Audio('https://assets.mixkit.co/sfx/preview/mixkit-arcade-game-jump-coin-216.mp3'),
      add: new Audio('https://assets.mixkit.co/sfx/preview/mixkit-winning-a-coin-video-game-2069.mp3'),
      win: new Audio('https://assets.mixkit.co/sfx/preview/mixkit-arcade-retro-winning-2077.mp3')
    };

    // Auth
    auth.onAuthStateChanged(user => {
      currentUser = user;
      updateUserMenu();
      loadCartCount();
      renderProducts();
      if(user) loadUserRank();
    });

    function updateUserMenu(){
      const menu = document.getElementById('userMenu');
      if(currentUser){
        menu.innerHTML = `
          <span id="userName">${currentUser.email.split('@')[0]}</span>
          <span class="rank-badge" id="rankBadge">Bronze</span>
          <button onclick="openProfile()">Profile</button>
          <button onclick="openAdmin()" id="adminBtn" style="display:none;">Admin</button>
          <button onclick="auth.signOut()">Logout</button>
        `;
        db.collection('users').doc(currentUser.uid).get().then(doc=>{
          if(doc.exists && doc.data().role === 'admin') document.getElementById('adminBtn').style.display='inline-block';
        });
      } else {
        menu.innerHTML = `<button onclick="openAuth('login')">Login</button> <button onclick="openAuth('register')">Register</button>`;
      }
    }

    function openAuth(mode){
      sounds.click.play();
      const modal = document.getElementById('authModal');
      modal.style.display = 'flex';
      modal.innerHTML = `<div class="modal-content">
        <h2 style="color:var(--accent);text-align:center;">${mode==='login'?'Đăng nhập':'Đăng ký'}</h2>
        <input type="email" id="authEmail" placeholder="Email"><br><br>
        <input type="password" id="authPass" placeholder="Password"><br><br>
        <button style="background:var(--accent);padding:1rem;width:100%;" onclick="\( {mode==='login'?'login()':'register()'}"> \){mode==='login'?'Login':'Register'}</button>
        <button style="background:#e74c3c;margin-top:0.5rem;width:100%;" onclick="closeModal('authModal')">Đóng</button>
      </div>`;
    }

    function login(){ 
      const email = document.getElementById('authEmail').value;
      const pass = document.getElementById('authPass').value;
      auth.signInWithEmailAndPassword(email,pass).catch(err=>alert(err.message));
    }

    function register(){ 
      const email = document.getElementById('authEmail').value;
      const pass = document.getElementById('authPass').value;
      auth.createUserWithEmailAndPassword(email,pass)
        .then(cred => db.collection('users').doc(cred.user.uid).set({role:'member',points:0,totalSpent:0,rank:'Bronze'}))
        .catch(err=>alert(err.message));
    }

    // Tabs & Products
    function renderTabs(){
      const tabs = document.getElementById('categoryTabs');
      tabs.innerHTML = '';
      categories.forEach(cat => {
        tabs.innerHTML += `<button class="tab-btn \( {cat==='Tất cả'?'active':''}" onclick="filterCategory(' \){cat}')">${cat}</button>`;
      });
    }
    renderTabs();

    function renderProducts(filter = 'Tất cả', search = ''){
      db.collection('products').onSnapshot(snapshot => {
        allProducts = snapshot.docs.map(doc => ({id: doc.id, ...doc.data()}));
        const grid = document.getElementById('productsGrid');
        grid.innerHTML = '';
        allProducts
          .filter(p => (filter === 'Tất cả' || p.category === filter) && p.name.toLowerCase().includes(search.toLowerCase()))
          .forEach(p => {
            const card = document.createElement('div');
            card.className = 'product-card';
            card.onclick = () => openProductDetail(p);
            card.innerHTML = `
              <img src="${p.img}" class="product-img">
              <div style="padding:1.5rem;">
                <h3>${p.name}</h3>
                <p style="color:var(--accent);font-size:1.6rem;">${p.price.toLocaleString()}₫</p>
                <div class="rating">\( {'★'.repeat(Math.round(p.rating||0))} ( \){p.reviewCount||0})</div>
                <button style="background:var(--accent);color:#000;padding:0.8rem;width:100%;margin-top:1rem;border-radius:30px;" onclick="event.stopPropagation(); addToCart('${p.id}')">Add to Cart</button>
              </div>
            `;
            grid.appendChild(card);
          });
      });
    }
    renderProducts();

    function filterCategory(cat){
      document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
      event.target.classList.add('active');
      renderProducts(cat, document.getElementById('searchInput').value);
    }

    function searchProducts(){
      const query = document.getElementById('searchInput').value;
      const activeCat = document.querySelector('.tab-btn.active').textContent;
      renderProducts(activeCat, query);
    }

    // Product Detail
    function openProductDetail(p){
      sounds.click.play();
      const modal = document.getElementById('productModal');
      modal.style.display = 'flex';
      modal.innerHTML = `<div class="modal-content">
        <h2 style="color:var(--accent)">${p.name}</h2>
        <img src="${p.img}" style="width:100%;max-height:400px;object-fit:contain;border-radius:15px;">
        <p style="margin:1rem 0;">${p.description || 'Sản phẩm gaming cao cấp, chất lượng đỉnh cao!'}</p>
        <p style="font-size:2rem;color:var(--accent)">${p.price.toLocaleString()}₫</p>
        <button style="background:var(--accent);padding:1rem;width:100%;" onclick="addToCart('${p.id}')">Add to Cart</button>
        <div id="reviews-${p.id}"></div>
        \( {currentUser ? `<div style="margin-top:1rem;"><select id="rating- \){p.id}"><option value="5">★★★★★</option><option value="4">★★★★</option><option value="3">★★★</option><option value="2">★★</option><option value="1">★</option></select>
        <input placeholder="Viết review..." id="reviewText-\( {p.id}"><button onclick="addReview(' \){p.id}')">Gửi</button></div>` : ''}
        <button style="background:#e74c3c;margin-top:1rem;width:100%;" onclick="closeModal('productModal')">Đóng</button>
      </div>`;
      loadReviews(p.id);
    }

    // Reviews
    function addReview(productId){
      if(!currentUser) return alert('Đăng nhập để review');
      const text = document.getElementById(`reviewText-${productId}`).value;
      const rating = Number(document.getElementById(`rating-${productId}`).value);
      db.collection('reviews').add({
        productId, text, rating, userId: currentUser.uid, userEmail: currentUser.email, timestamp: firebase.firestore.FieldValue.serverTimestamp()
      }).then(() => {
        db.collection('products').doc(productId).update({
          rating: firebase.firestore.FieldValue.increment(rating),
          reviewCount: firebase.firestore.FieldValue.increment(1)
        });
      });
    }

    function loadReviews(productId){
      const div = document.getElementById(`reviews-${productId}`) || document.createElement('div');
      div.innerHTML = '<h3>Reviews</h3>';
      db.collection('reviews').where('productId','==',productId).orderBy('timestamp','desc').onSnapshot(snap => {
        div.innerHTML = '<h3>Reviews</h3>';
        snap.forEach(doc => {
          const r = doc.data();
          div.innerHTML += `<div style="background:rgba(0,255,255,0.1);padding:1rem;margin:0.5rem 0;border-radius:10px;">
            <strong>${r.userEmail}</strong> - \( {'★'.repeat(r.rating)}<br> \){r.text}</div>`;
        });
      });
    }

    // Cart
    function addToCart(id){
      sounds.add.play();
      if(!currentUser) return alert('Đăng nhập để thêm giỏ');
      db.collection('cart').doc(currentUser.uid).collection('items').doc(id).set({
        productId: id,
        qty: firebase.firestore.FieldValue.increment(1)
      }, {merge: true});
    }

    function loadCartCount(){
      if(!currentUser) return;
      db.collection('cart').doc(currentUser.uid).collection('items').onSnapshot(snap => {
        document.getElementById('cartBadge').textContent = snap.size;
      });
    }

    document.getElementById('cartIcon').onclick = () => {
      if(!currentUser) return alert('Đăng nhập để xem giỏ');
      sounds.click.play();
      const modal = document.getElementById('cartModal');
      modal.style.display = 'flex';
      modal.innerHTML = `<div class="modal-content"><h2 style="color:var(--accent)">Giỏ hàng</h2><div id="cartItemsList"></div>
        <h3 id="cartTotal">Tổng: 0₫</h3>
        <button style="background:var(--accent);width:100%;padding:1rem;margin-top:1rem;" onclick="openCheckout()">Thanh toán</button>
        <button style="background:#e74c3c;margin-top:0.5rem;width:100%;" onclick="closeModal('cartModal')">Đóng</button></div>`;
      loadCartItems();
    };

    function loadCartItems(){
      db.collection('cart').doc(currentUser.uid).collection('items').get().then(snap => {
        const list = document.getElementById('cartItemsList');
        let total = 0;
        list.innerHTML = '';
        snap.forEach(doc => {
          const item = doc.data();
          db.collection('products').doc(item.productId).get().then(pdoc => {
            const p = pdoc.data();
            total += p.price * item.qty;
            list.innerHTML += `<div style="display:flex;align-items:center;gap:1rem;padding:1rem 0;border-bottom:1px solid #333;">
              <img src="${p.img}" style="width:80px;border-radius:10px;">
              <div style="flex:1;"><h4>\( {p.name}</h4><p>x \){item.qty}</p></div>
              <p>${(p.price*item.qty).toLocaleString()}₫</p>
              <button style="background:#e74c3c;" onclick="removeCartItem('${doc.id}')">Xóa</button>
            </div>`;
            document.getElementById('cartTotal').textContent = `Tổng: ${total.toLocaleString()}₫`;
          });
        });
      });
    }

    function removeCartItem(id){
      db.collection('cart').doc(currentUser.uid).collection('items').doc(id).delete();
      loadCartItems();
    }

    // Checkout
    function openCheckout(){
      closeModal('cartModal');
      const modal = document.getElementById('checkoutModal');
      modal.style.display = 'flex';
      modal.innerHTML = `<div class="modal-content">
        <h2 style="color:var(--accent)">Thanh toán</h2>
        <p>Đây là demo - Order sẽ được lưu vào lịch sử!</p>
        <button style="background:var(--accent);width:100%;padding:1rem;" onclick="placeOrder()">Xác nhận đặt hàng</button>
        <button style="background:#e74c3c;margin-top:0.5rem;width:100%;" onclick="closeModal('checkoutModal')">Hủy</button>
      </div>`;
    }

    function placeOrder(){
      db.collection('cart').doc(currentUser.uid).collection('items').get().then(snap => {
        let total = 0;
        const items = [];
        snap.forEach(doc => {
          items.push({productId: doc.id, qty: doc.data().qty});
          db.collection('products').doc(doc.id).get().then(p => total += p.data().price * doc.data().qty);
        });
        db.collection('orders').add({
          userId: currentUser.uid,
          items,
          total,
          statu
