<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MyShop - Cửa hàng đẹp</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    *{margin:0;padding:0;box-sizing:border-box}
    body{font-family:'Poppins',sans-serif;background:#f4f4f9;color:#333;line-height:1.6}
    .container{max-width:1200px;margin:0 auto;padding:0 20px}
    .header{background:#fff;box-shadow:0 4px 10px rgba(0,0,0,0.1);position:fixed;width:100%;top:0;z-index:1000}
    .header .container{display:flex;justify-content:space-between;align-items:center;height:70px}
    .logo{font-size:1.8rem;font-weight:700;color:#6e07c8}
    .nav a{margin-left:20px;text-decoration:none;color:#333;font-weight:500;transition:color .3s}
    .nav a:hover{color:#6e07c8}
    .cart-icon{position:relative;font-size:1.5rem;cursor:pointer}
    .cart-count{position:absolute;top:-8px;right:-10px;background:#ff4757;color:white;font-size:0.8rem;width:18px;height:18px;border-radius:50%;display:flex;align-items:center;justify-content:center}
    .hero{background:linear-gradient(135deg,#6e07c8,#a777e6);color:white;text-align:center;padding:150px 20px 100px;margin-top:70px}
    .hero h2{font-size:2.8rem;margin-bottom:20px}
    .hero p{font-size:1.2rem;margin-bottom:30px;opacity:0.9}
    .btn-primary{background:#fff;color:#6e07c8;padding:12px 30px;border:none;border-radius:50px;font-weight:600;cursor:pointer;transition:all .3s;text-decoration:none;display:inline-block}
    .btn-primary:hover{transform:translateY(-3px);box-shadow:0 10px 20px rgba(0,0,0,0.2)}
    .products{padding:80px 0}
    .section-title{text-align:center;font-size:2.2rem;margin-bottom:50px;color:#333}
    .product-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:30px}
    .product-card{background:white;border-radius:15px;overflow:hidden;box-shadow:0 5px 15px rgba(0,0,0,0.08);transition:all .4s;cursor:pointer}
    .product-card:hover{transform:translateY(-10px);box-shadow:0 20px 30px rgba(0,0,0,0.15)}
    .product-card img{width:100%;height:220px;object-fit:cover}
    .product-info{padding:20px;text-align:center}
    .product-info h3{font-size:1.3rem;margin-bottom:10px}
    .price{font-size:1.4rem;font-weight:700;color:#6e07c8;margin:15px 0}
    .modal{display:none;position:fixed;z-index:2000;left:0;top:0;width:100%;height:100%;background:rgba(0,0,0,0.7);align-items:center;justify-content:center}
    .modal-content{background:white;border-radius:15px;max-width:500px;width:90%;overflow:hidden;animation:modalShow .4s}
    @keyframes modalShow{from{transform:scale(0.7);opacity:0}to{transform:scale(1);opacity:1}}
    .modal-content img{width:100%;height:300px;object-fit:cover}
    .modal-content h3{padding:20px 20px 10px;font-size:1.6rem}
    .modal-content p{padding:0 20px;margin-bottom:15px}
    .close{position:absolute;top:15px;right:25px;font-size:2rem;cursor:pointer;color:#aaa}
    .close:hover{color:#000}
    @media(max-width:768px){.nav{display:none}.hero h2{font-size:2.2rem}.product-grid{grid-template-columns:1fr 1fr}}
    @media(max-width:480px){.product-grid{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <header class="header">
    <div class="container">
      <h1 class="logo">MyShop</h1>
      <nav class="nav">
        <a href="#home">Trang chủ</a>
        <a href="#products">Sản phẩm</a>
        <a href="#contact">Liên hệ</a>
      </nav>
      <div class="cart-icon">
        <i class="fas fa-shopping-cart"></i>
        <span class="cart-count">0</span>
      </div>
    </div>
  </header>

  <section id="home" class="hero">
    <div class="hero-content">
      <h2>Chào mừng đến với MyShop</h2>
      <p>Khám phá các sản phẩm chất lượng cao với thiết kế hiện đại</p>
      <a href="#products" class="btn-primary">Mua ngay</a>
    </div>
  </section>

  <section id="products" class="products">
    <div class="container">
      <h2 class="section-title">Sản phẩm nổi bật</h2>
      <div class="product-grid" id="productGrid"></div>
    </div>
  </section>

  <div class="modal" id="productModal">
    <div class="modal-content">
      <span class="close">×</span>
      <img id="modalImg" src="" alt="">
      <h3 id="modalTitle"></h3>
      <p id="modalDesc"></p>
      <p class="price" id="modalPrice"></p>
      <button class="btn-primary" id="addToCartBtn" style="width:90%;margin:20px auto;display:block;">Thêm vào giỏ hàng</button>
    </div>
  </div>

  <script>
    const products = [
      {title:"Sản phẩm 1",price:"299.000đ",desc:"Mô tả chi tiết sản phẩm tuyệt vời, chất lượng cao.",img:"https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500"},
      {title:"Sản phẩm 2",price:"499.000đ",desc:"Thiết kế hiện đại, bền bỉ theo thời gian.",img:"https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500"},
      {title:"Sản phẩm 3",price:"199.000đ",desc:"Giá siêu tốt, số lượng có hạn.",img:"https://images.unsplash.com/photo-1571781926291-c477ebfd024b?w=500"},
      {title:"Sản phẩm 4",price:"799.000đ",desc:"Phiên bản đặc biệt, cao cấp nhất.",img:"https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=500"},
      {title:"Sản phẩm 5",price:"349.000đ",desc:"Bán chạy nhất tháng này.",img:"https://images.unsplash.com/photo-1560769629-975ec94e6a86?w=500"},
      {title:"Sản phẩm 6",price:"599.000đ",desc:"Được hàng ngàn khách hàng tin dùng.",img:"https://images.unsplash.com/photo-1600585154340-be6161a56a0c?w=500"}
    ];

    const productGrid = document.getElementById('productGrid');
    const modal = document.getElementById('productModal');
    const modalImg = document.getElementById('modalImg');
    const modalTitle = document.getElementById('modalTitle');
    const modalDesc = document.getElementById('modalDesc');
    const modalPrice = document.getElementById('modalPrice');
    const closeBtn = document.querySelector('.close');
    const cartCount = document.querySelector('.cart-count');
    let cartItems = 0;

    products.forEach(p => {
      const card = document.createElement('div');
      card.className = 'product-card';
      card.innerHTML = `
        <img src="\( {p.img}" alt=" \){p.title}">
        <div class="product-info">
          <h3>${p.title}</h3>
          <p class="price">${p.price}</p>
          <button class="btn-primary" style="padding:10px 20px;">Xem chi tiết</button>
        </div>
      `;
      card.onclick = () => {
        modalImg.src = p.img;
        modalTitle.textContent = p.title;
        modalDesc.textContent = p.desc;
        modalPrice.textContent = p.price;
        modal.style.display = 'flex';
      };
      productGrid.appendChild(card);
    });

    closeBtn.onclick = () => modal.style.display = 'none';
    window.onclick = e => { if(e.target === modal) modal.style.display = 'none'; };

    document.getElementById('addToCartBtn').onclick = () => {
      cartItems++;
      cartCount.textContent = cartItems;
      alert('Đã thêm vào giỏ hàng!');
    };
  </script>
</body>
</html>
