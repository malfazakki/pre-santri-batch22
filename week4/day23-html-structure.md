# Hari 23: Setup Struktur HTML Dasar Semua Halaman

## Tujuan Pembelajaran
- Membuat struktur HTML dasar untuk semua halaman
- Memahami penggunaan semantic HTML
- Membuat navigasi antar halaman
- Menyiapkan struktur Home, About, dan Contact
- Memastikan konsistensi struktur antar halaman

## 1. Struktur Dasar Template

### Base Template (base.html)
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Your website description">
    <title>Website Name - Page Title</title>
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/images/favicon.ico">
    
    <!-- CSS Files -->
    <link rel="stylesheet" href="/css/style.css">
    <link rel="stylesheet" href="/css/responsive.css">
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <nav class="navbar">
                <a href="/" class="logo">
                    <img src="/images/logo.png" alt="Website Logo">
                </a>
                
                <button class="nav-toggle" aria-label="Toggle Navigation">
                    <span class="hamburger"></span>
                </button>
                
                <ul class="nav-menu">
                    <li><a href="/" class="nav-link">Home</a></li>
                    <li><a href="/about.html" class="nav-link">About</a></li>
                    <li><a href="/services.html" class="nav-link">Services</a></li>
                    <li><a href="/contact.html" class="nav-link">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Main Content -->
    <main>
        <!-- Content will be different for each page -->
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>About Us</h3>
                    <p>Short description about your company or website.</p>
                </div>
                
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="/">Home</a></li>
                        <li><a href="/about.html">About</a></li>
                        <li><a href="/services.html">Services</a></li>
                        <li><a href="/contact.html">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <p>Email: info@example.com</p>
                    <p>Phone: (123) 456-7890</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                    </div>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2023 Your Website. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript Files -->
    <script src="/js/main.js"></script>
</body>
</html>
```

## 2. Homepage Structure (index.html)

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <!-- Include head from base template -->
</head>
<body>
    <!-- Include header from base template -->

    <main>
        <!-- Hero Section -->
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <h1>Welcome to Our Website</h1>
                    <p>Your compelling tagline goes here</p>
                    <a href="/contact.html" class="cta-button">Get Started</a>
                </div>
            </div>
        </section>

        <!-- Features Section -->
        <section class="features">
            <div class="container">
                <h2 class="section-title">Our Features</h2>
                <div class="features-grid">
                    <div class="feature-card">
                        <i class="fas fa-rocket"></i>
                        <h3>Feature 1</h3>
                        <p>Description of feature 1</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-cog"></i>
                        <h3>Feature 2</h3>
                        <p>Description of feature 2</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-chart-line"></i>
                        <h3>Feature 3</h3>
                        <p>Description of feature 3</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Preview Section -->
        <section class="about-preview">
            <div class="container">
                <div class="about-content">
                    <div class="about-text">
                        <h2>About Us</h2>
                        <p>Brief description about your company or service.</p>
                        <a href="/about.html" class="read-more">Learn More</a>
                    </div>
                    <div class="about-image">
                        <img src="/images/about-preview.jpg" alt="About Us Preview">
                    </div>
                </div>
            </div>
        </section>

        <!-- Services Preview -->
        <section class="services-preview">
            <div class="container">
                <h2 class="section-title">Our Services</h2>
                <div class="services-grid">
                    <div class="service-card">
                        <img src="/images/service1.jpg" alt="Service 1">
                        <h3>Service 1</h3>
                        <p>Description of service 1</p>
                    </div>
                    <div class="service-card">
                        <img src="/images/service2.jpg" alt="Service 2">
                        <h3>Service 2</h3>
                        <p>Description of service 2</p>
                    </div>
                    <div class="service-card">
                        <img src="/images/service3.jpg" alt="Service 3">
                        <h3>Service 3</h3>
                        <p>Description of service 3</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Call to Action -->
        <section class="cta">
            <div class="container">
                <h2>Ready to Get Started?</h2>
                <p>Contact us today to learn more about our services.</p>
                <a href="/contact.html" class="cta-button">Contact Us</a>
            </div>
        </section>
    </main>

    <!-- Include footer from base template -->
</body>
</html>
```

## 3. About Page Structure (about.html)

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <!-- Include head from base template -->
</head>
<body>
    <!-- Include header from base template -->

    <main>
        <!-- Page Header -->
        <section class="page-header">
            <div class="container">
                <h1>About Us</h1>
                <nav aria-label="breadcrumb">
                    <ol class="breadcrumb">
                        <li><a href="/">Home</a></li>
                        <li>About</li>
                    </ol>
                </nav>
            </div>
        </section>

        <!-- Company Story -->
        <section class="company-story">
            <div class="container">
                <div class="story-content">
                    <div class="story-text">
                        <h2>Our Story</h2>
                        <p>Detailed description of your company's history and mission.</p>
                    </div>
                    <div class="story-image">
                        <img src="/images/company-story.jpg" alt="Our Story">
                    </div>
                </div>
            </div>
        </section>

        <!-- Team Section -->
        <section class="team">
            <div class="container">
                <h2 class="section-title">Our Team</h2>
                <div class="team-grid">
                    <div class="team-member">
                        <img src="/images/team1.jpg" alt="Team Member 1">
                        <h3>John Doe</h3>
                        <p>CEO</p>
                    </div>
                    <div class="team-member">
                        <img src="/images/team2.jpg" alt="Team Member 2">
                        <h3>Jane Smith</h3>
                        <p>Creative Director</p>
                    </div>
                    <div class="team-member">
                        <img src="/images/team3.jpg" alt="Team Member 3">
                        <h3>Mike Johnson</h3>
                        <p>Lead Developer</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Values Section -->
        <section class="values">
            <div class="container">
                <h2 class="section-title">Our Values</h2>
                <div class="values-grid">
                    <div class="value-card">
                        <i class="fas fa-heart"></i>
                        <h3>Passion</h3>
                        <p>Description of this value</p>
                    </div>
                    <div class="value-card">
                        <i class="fas fa-handshake"></i>
                        <h3>Integrity</h3>
                        <p>Description of this value</p>
                    </div>
                    <div class="value-card">
                        <i class="fas fa-lightbulb"></i>
                        <h3>Innovation</h3>
                        <p>Description of this value</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Include footer from base template -->
</body>
</html>
```

## 4. Contact Page Structure (contact.html)

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <!-- Include head from base template -->
</head>
<body>
    <!-- Include header from base template -->

    <main>
        <!-- Page Header -->
        <section class="page-header">
            <div class="container">
                <h1>Contact Us</h1>
                <nav aria-label="breadcrumb">
                    <ol class="breadcrumb">
                        <li><a href="/">Home</a></li>
                        <li>Contact</li>
                    </ol>
                </nav>
            </div>
        </section>

        <!-- Contact Information -->
        <section class="contact-info">
            <div class="container">
                <div class="info-grid">
                    <div class="info-card">
                        <i class="fas fa-map-marker-alt"></i>
                        <h3>Address</h3>
                        <p>123 Street Name<br>City, Country</p>
                    </div>
                    <div class="info-card">
                        <i class="fas fa-phone"></i>
                        <h3>Phone</h3>
                        <p>(123) 456-7890</p>
                    </div>
                    <div class="info-card">
                        <i class="fas fa-envelope"></i>
                        <h3>Email</h3>
                        <p>info@example.com</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Form -->
        <section class="contact-form">
            <div class="container">
                <div class="form-container">
                    <h2>Send us a Message</h2>
                    <form id="contactForm" action="/submit" method="POST">
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" name="subject" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" name="message" rows="5" required></textarea>
                        </div>
                        
                        <button type="submit" class="submit-button">Send Message</button>
                    </form>
                </div>
            </div>
        </section>

        <!-- Map Section -->
        <section class="map">
            <div class="container">
                <div class="map-container">
                    <!-- Replace with your map embed code -->
                    <iframe 
                        src="https://www.google.com/maps/embed?pb=..."
                        width="100%" 
                        height="450" 
                        style="border:0;" 
                        allowfullscreen="" 
                        loading="lazy">
                    </iframe>
                </div>
            </div>
        </section>
    </main>

    <!-- Include footer from base template -->
</body>
</html>
```

## 5. Best Practices

### 1. Semantic HTML
- Gunakan tag yang sesuai dengan kontennya
- Manfaatkan struktur heading yang benar (h1-h6)
- Gunakan landmark elements (header, nav, main, footer)

### 2. Accessibility
- Tambahkan atribut alt pada gambar
- Gunakan ARIA labels jika diperlukan
- Pastikan kontras warna yang cukup

### 3. SEO
- Gunakan meta descriptions
- Struktur heading yang benar
- URL yang SEO-friendly

### 4. Performance
- Optimize gambar
- Minify CSS dan JavaScript
- Lazy loading untuk gambar

## 6. Latihan

### Latihan 1: Header & Footer
Buat header dan footer yang konsisten untuk semua halaman

### Latihan 2: Homepage
Implementasi struktur homepage sesuai wireframe

### Latihan 3: About & Contact
Buat halaman About dan Contact dengan form yang berfungsi

## Kesimpulan
- Struktur HTML yang baik adalah fondasi website yang solid
- Konsistensi antar halaman penting untuk UX
- Semantic HTML membantu SEO dan accessibility
- Modular structure memudahkan maintenance

## Referensi Tambahan
- [MDN HTML Guide](https://developer.mozilla.org/en-US/docs/Learn/HTML)
- [HTML5 Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)
- [Web Accessibility Initiative](https://www.w3.org/WAI/)
- [HTML Best Practices](https://github.com/hail2u/html-best-practices)