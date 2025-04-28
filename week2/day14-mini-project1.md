# Hari 14: Mini Project 1 - Landing Page Sederhana

## Tujuan Project
- Mengaplikasikan semua konsep HTML dan CSS yang telah dipelajari
- Membuat landing page responsif untuk produk/toko
- Menerapkan prinsip mobile-first design
- Menggunakan Flexbox untuk layout
- Implementasi media queries untuk responsivitas

## 1. Perencanaan Project

### Komponen Landing Page
1. Navigation Bar
2. Hero Section
3. Features/Products Section
4. About Section
5. Contact Form
6. Footer

### Struktur File
```plaintext
landing-page/
├── index.html
├── css/
│   ├── style.css
│   └── responsive.css
└── images/
    ├── hero.jpg
    ├── product1.jpg
    ├── product2.jpg
    └── product3.jpg
```

## 2. Implementasi

### HTML Structure (index.html)

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toko Online - Landing Page</title>
    <link rel="stylesheet" href="css/style.css">
    <link rel="stylesheet" href="css/responsive.css">
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">
                <h1>TokoKita</h1>
            </div>
            <div class="menu-toggle" id="mobile-menu">
                <span></span>
                <span></span>
                <span></span>
            </div>
            <ul class="nav-menu">
                <li><a href="#home">Beranda</a></li>
                <li><a href="#products">Produk</a></li>
                <li><a href="#about">Tentang</a></li>
                <li><a href="#contact">Kontak</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Selamat Datang di TokoKita</h1>
            <p>Temukan produk berkualitas dengan harga terbaik</p>
            <a href="#products" class="cta-button">Lihat Produk</a>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products">
        <div class="container">
            <h2>Produk Unggulan</h2>
            <div class="product-grid">
                <div class="product-card">
                    <img src="images/product1.jpg" alt="Product 1">
                    <h3>Produk 1</h3>
                    <p>Deskripsi produk yang menarik dan informatif.</p>
                    <p class="price">Rp 199.000</p>
                    <button class="buy-button">Beli Sekarang</button>
                </div>
                <div class="product-card">
                    <img src="images/product2.jpg" alt="Product 2">
                    <h3>Produk 2</h3>
                    <p>Deskripsi produk yang menarik dan informatif.</p>
                    <p class="price">Rp 299.000</p>
                    <button class="buy-button">Beli Sekarang</button>
                </div>
                <div class="product-card">
                    <img src="images/product3.jpg" alt="Product 3">
                    <h3>Produk 3</h3>
                    <p>Deskripsi produk yang menarik dan informatif.</p>
                    <p class="price">Rp 399.000</p>
                    <button class="buy-button">Beli Sekarang</button>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2>Tentang Kami</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>TokoKita adalah toko online terpercaya yang menyediakan berbagai produk berkualitas. Kami berkomitmen untuk memberikan pelayanan terbaik kepada pelanggan.</p>
                    <p>Dengan pengalaman lebih dari 5 tahun, kami telah melayani ribuan pelanggan dengan tingkat kepuasan yang tinggi.</p>
                </div>
                <div class="about-features">
                    <div class="feature">
                        <i class="icon">🚚</i>
                        <h3>Pengiriman Cepat</h3>
                        <p>Pengiriman ke seluruh Indonesia</p>
                    </div>
                    <div class="feature">
                        <i class="icon">💰</i>
                        <h3>Harga Terbaik</h3>
                        <p>Jaminan harga termurah</p>
                    </div>
                    <div class="feature">
                        <i class="icon">🛡️</i>
                        <h3>Garansi Produk</h3>
                        <p>Garansi uang kembali</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2>Hubungi Kami</h2>
            <div class="contact-content">
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Nama</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Pesan</label>
                            <textarea id="message" name="message" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="submit-button">Kirim Pesan</button>
                    </form>
                </div>
                <div class="contact-info">
                    <h3>Informasi Kontak</h3>
                    <p>📍 Jl. Contoh No. 123, Kota</p>
                    <p>📞 +62 123-456-7890</p>
                    <p>✉️ info@tokokita.com</p>
                    <div class="social-links">
                        <a href="#" class="social-link">Facebook</a>
                        <a href="#" class="social-link">Instagram</a>
                        <a href="#" class="social-link">Twitter</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>TokoKita</h3>
                    <p>Toko online terpercaya dengan produk berkualitas.</p>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#home">Beranda</a></li>
                        <li><a href="#products">Produk</a></li>
                        <li><a href="#about">Tentang</a></li>
                        <li><a href="#contact">Kontak</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Newsletter</h3>
                    <form class="newsletter-form">
                        <input type="email" placeholder="Email Anda">
                        <button type="submit">Subscribe</button>
                    </form>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 TokoKita. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        document.getElementById('mobile-menu').addEventListener('click', function() {
            this.classList.toggle('active');
            document.querySelector('.nav-menu').classList.toggle('active');
        });
    </script>
</body>
</html>
```

### Main CSS (style.css)

```css
/* Reset and Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

/* Navigation */
.navbar {
    background-color: #fff;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    max-width: 1200px;
    margin: 0 auto;
}

.logo h1 {
    font-size: 1.5rem;
    color: #333;
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-menu a {
    text-decoration: none;
    color: #333;
    font-weight: 500;
    transition: color 0.3s;
}

.nav-menu a:hover {
    color: #4CAF50;
}

.menu-toggle {
    display: none;
}

/* Hero Section */
.hero {
    height: 100vh;
    background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('../images/hero.jpg');
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    text-align: center;
    color: white;
    padding-top: 80px;
}

.hero-content {
    width: 100%;
    padding: 0 20px;
}

.hero h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.hero p {
    font-size: 1.2rem;
    margin-bottom: 2rem;
}

.cta-button {
    display: inline-block;
    padding: 1rem 2rem;
    background-color: #4CAF50;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    transition: background-color 0.3s;
}

.cta-button:hover {
    background-color: #45a049;
}

/* Products Section */
.products {
    padding: 80px 0;
    background-color: #f9f9f9;
}

.products h2 {
    text-align: center;
    margin-bottom: 40px;
}

.product-grid {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
}

.product-card {
    flex: 1;
    min-width: 300px;
    background: white;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    transition: transform 0.3s;
}

.product-card:hover {
    transform: translateY(-5px);
}

.product-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.product-card h3 {
    padding: 15px;
    margin: 0;
}

.product-card p {
    padding: 0 15px;
    color: #666;
}

.product-card .price {
    font-size: 1.2rem;
    font-weight: bold;
    color: #4CAF50;
    padding: 15px;
}

.buy-button {
    width: 100%;
    padding: 15px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s;
}

.buy-button:hover {
    background-color: #45a049;
}

/* About Section */
.about {
    padding: 80px 0;
}

.about-content {
    display: flex;
    gap: 40px;
    align-items: center;
}

.about-text {
    flex: 1;
}

.about-features {
    flex: 1;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.feature {
    flex: 1;
    min-width: 200px;
    text-align: center;
    padding: 20px;
    background: #f9f9f9;
    border-radius: 8px;
}

.feature .icon {
    font-size: 2rem;
    margin-bottom: 10px;
}

/* Contact Section */
.contact {
    padding: 80px 0;
    background-color: #f9f9f9;
}

.contact-content {
    display: flex;
    gap: 40px;
}

.contact-form {
    flex: 2;
}

.contact-info {
    flex: 1;
}

.form-group {
    margin-bottom: 20px;
}

.form-group label {
    display: block;
    margin-bottom: 5px;
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
}

.submit-button {
    background-color: #4CAF50;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.submit-button:hover {
    background-color: #45a049;
}

.social-links {
    margin-top: 20px;
}

.social-link {
    margin-right: 10px;
    color: #333;
    text-decoration: none;
}

/* Footer */
.footer {
    background-color: #333;
    color: white;
    padding: 40px 0 20px;
}

.footer-content {
    display: flex;
    gap: 40px;
    margin-bottom: 20px;
}

.footer-section {
    flex: 1;
}

.footer-section h3 {
    margin-bottom: 20px;
}

.footer-section ul {
    list-style: none;
}

.footer-section ul li {
    margin-bottom: 10px;
}

.footer-section a {
    color: white;
    text-decoration: none;
}

.newsletter-form {
    display: flex;
    gap: 10px;
}

.newsletter-form input {
    flex: 1;
    padding: 10px;
    border: none;
    border-radius: 4px;
}

.newsletter-form button {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.footer-bottom {
    text-align: center;
    padding-top: 20px;
    border-top: 1px solid #555;
}
```

### Responsive CSS (responsive.css)

```css
/* Tablet Styles */
@media screen and (max-width: 992px) {
    .product-grid {
        gap: 20px;
    }

    .product-card {
        min-width: calc(50% - 10px);
    }

    .about-content {
        flex-direction: column;
    }

    .contact-content {
        flex-direction: column;
    }

    .footer-content {
        flex-wrap: wrap;
    }

    .footer-section {
        flex: 1 1 calc(50% - 20px);
    }
}

/* Mobile Styles */
@media screen and (max-width: 768px) {
    .menu-toggle {
        display: block;
        cursor: pointer;
    }

    .menu-toggle span {
        display: block;
        width: 25px;
        height: 3px;
        background-color: #333;
        margin: 5px 0;
        transition: 0.3s;
    }

    .menu-toggle.active span:nth-child(1) {
        transform: rotate(-45deg) translate(-5px, 6px);
    }

    .menu-toggle.active span:nth-child(2) {
        opacity: 0;
    }

    .menu-toggle.active span:nth-child(3) {
        transform: rotate(45deg) translate(-5px, -6px);
    }

    .nav-menu {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        background-color: white;
        padding: 20px;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        flex-direction: column;
        gap: 1rem;
    }

    .nav-menu.active {
        display: flex;
    }

    .hero h1 {
        font-size: 2rem;
    }

    .hero p {
        font-size: 1rem;
    }

    .product-card {
        min-width: 100%;
    }

    .feature {
        min-width: 100%;
    }

    .footer-section {
        flex: 1 1 100%;
    }

    .newsletter-form {
        flex-direction: column;
    }

    .newsletter-form button {
        width: 100%;
    }
}

/* Small Mobile Styles */
@media screen and (max-width: 576px) {
    .container {
        width: 95%;
    }

    .hero {
        padding-top: 60px;
    }

    .about-features {
        gap: 10px;
    }

    .form-row {
        flex-direction: column;
    }
}
```

## 3. Testing dan Optimasi

### Checklist Testing
1. Responsivitas pada berbagai ukuran layar
2. Fungsi menu hamburger di mobile
3. Gambar yang responsif
4. Form validation
5. Smooth scrolling untuk navigasi
6. Loading performance

### Optimasi
1. Kompresi gambar
2. Minify CSS
3. Lazy loading untuk gambar
4. Browser caching
5. Optimasi font loading

## 4. Pengembangan Lanjutan

### Fitur Tambahan yang Bisa Ditambahkan
1. Animasi scroll
2. Image slider untuk produk
3. Filter produk
4. Shopping cart preview
5. Live chat widget
6. Back to top button

## Kesimpulan
- Landing page ini menggabungkan semua konsep yang telah dipelajari
- Menggunakan pendekatan mobile-first design
- Memanfaatkan Flexbox untuk layout
- Menerapkan media queries untuk responsivitas
- Memperhatikan user experience di berbagai device

## Referensi
- [MDN Web Docs - Landing Page Examples](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Practical_positioning_examples)
- [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Google Web Fundamentals - Responsive Web Design](https://developers.google.com/web/fundamentals/design-and-ux/responsive)
- [Smashing Magazine - Building Better Landing Pages](https://www.smashingmagazine.com/category/landing-pages/)