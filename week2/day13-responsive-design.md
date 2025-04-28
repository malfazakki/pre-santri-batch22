# Hari 13: Responsive Design Basics (Media Queries)

## Tujuan Pembelajaran
- Memahami konsep dasar responsive web design
- Mempelajari penggunaan media queries untuk membuat layout responsif
- Memahami breakpoints dan cara menggunakannya
- Menerapkan prinsip mobile-first design
- Membuat halaman web yang responsif untuk berbagai ukuran layar

## 1. Pengenalan Responsive Web Design

### Apa itu Responsive Web Design?
Responsive Web Design (RWD) adalah pendekatan yang membuat website dapat beradaptasi dengan berbagai ukuran layar dan perangkat. Website responsif akan terlihat dan berfungsi dengan baik di desktop, tablet, maupun smartphone.

### Prinsip Dasar Responsive Design
1. **Fluid Grids**: Layout yang menggunakan ukuran relatif (%, vw, vh) bukan absolut (px)
2. **Flexible Images**: Gambar yang dapat menyesuaikan ukuran container
3. **Media Queries**: CSS rules yang diterapkan berdasarkan karakteristik device

### Viewport Meta Tag
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
Tag ini penting untuk memastikan website ditampilkan dengan benar di perangkat mobile.

## 2. Media Queries

### Sintaks Dasar
```css
@media [type] [and (condition)] {
    /* CSS rules */
}
```

### Tipe Media
- `all`: Semua device
- `screen`: Layar komputer, tablet, smartphone
- `print`: Printer atau print preview
- `speech`: Screen readers

### Contoh Media Queries

#### Berdasarkan Lebar Layar
```css
/* Styles untuk layar dengan lebar maksimal 768px */
@media screen and (max-width: 768px) {
    .container {
        width: 100%;
        padding: 0 15px;
    }
}

/* Styles untuk layar dengan lebar minimal 769px */
@media screen and (min-width: 769px) {
    .container {
        width: 750px;
        margin: 0 auto;
    }
}
```

#### Berdasarkan Orientasi
```css
/* Styles untuk orientasi landscape */
@media screen and (orientation: landscape) {
    .container {
        display: flex;
    }
}

/* Styles untuk orientasi portrait */
@media screen and (orientation: portrait) {
    .container {
        display: block;
    }
}
```

### Common Breakpoints
```css
/* Mobile First Approach */
/* Base styles untuk mobile */

/* Small devices (tablets) */
@media screen and (min-width: 576px) {
    /* tablet styles */
}

/* Medium devices (laptops) */
@media screen and (min-width: 768px) {
    /* laptop styles */
}

/* Large devices (desktops) */
@media screen and (min-width: 992px) {
    /* desktop styles */
}

/* Extra large devices */
@media screen and (min-width: 1200px) {
    /* large desktop styles */
}
```

## 3. Mobile-First Design

### Prinsip Mobile-First
1. Mulai dengan desain untuk layar kecil
2. Progressively enhance untuk layar yang lebih besar
3. Fokus pada konten penting
4. Optimasi performa

### Contoh Mobile-First CSS
```css
/* Base styles (mobile) */
.container {
    width: 100%;
    padding: 15px;
}

.nav {
    display: none; /* Menu tersembunyi di mobile */
}

.menu-toggle {
    display: block; /* Tombol menu hamburger ditampilkan */
}

/* Tablet and up */
@media screen and (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
    }

    .nav {
        display: block; /* Menu ditampilkan */
    }

    .menu-toggle {
        display: none; /* Tombol menu disembunyikan */
    }
}
```

## 4. Responsive Images

### Gambar yang Responsif
```css
.responsive-image {
    max-width: 100%;
    height: auto;
}
```

### Picture Element
```html
<picture>
    <source media="(min-width: 992px)" srcset="large.jpg">
    <source media="(min-width: 768px)" srcset="medium.jpg">
    <img src="small.jpg" alt="Responsive Image">
</picture>
```

### Background Images Responsif
```css
.header {
    background-image: url('small.jpg');
}

@media screen and (min-width: 768px) {
    .header {
        background-image: url('medium.jpg');
    }
}

@media screen and (min-width: 992px) {
    .header {
        background-image: url('large.jpg');
    }
}
```

## 5. Contoh Implementasi Responsive Design

### Responsive Navigation Bar

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Navigation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
        }

        .navbar {
            background-color: #333;
            padding: 1rem;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: white;
            font-size: 1.5rem;
            font-weight: bold;
        }

        .menu-toggle {
            display: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .nav-links {
            display: flex;
            gap: 1rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            padding: 0.5rem 1rem;
        }

        .nav-links a:hover {
            background-color: #555;
            border-radius: 4px;
        }

        /* Mobile Styles */
        @media screen and (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-links {
                display: none;
                width: 100%;
                position: absolute;
                top: 70px;
                left: 0;
                background-color: #333;
                flex-direction: column;
                padding: 1rem;
            }

            .nav-links.active {
                display: flex;
            }

            .nav-links a {
                padding: 1rem;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">Logo</div>
            <div class="menu-toggle" onclick="toggleMenu()">☰</div>
            <div class="nav-links">
                <a href="#">Home</a>
                <a href="#">About</a>
                <a href="#">Services</a>
                <a href="#">Contact</a>
            </div>
        </div>
    </nav>

    <script>
        function toggleMenu() {
            document.querySelector('.nav-links').classList.toggle('active');
        }
    </script>
</body>
</html>
```

### Responsive Grid Layout

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Grid</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }

        .grid-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .grid-item {
            flex: 1;
            min-width: 300px;
            background-color: #f0f0f0;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .grid-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 4px;
            margin-bottom: 15px;
        }

        .grid-item h2 {
            margin-bottom: 10px;
            color: #333;
        }

        .grid-item p {
            color: #666;
            line-height: 1.6;
        }

        /* Tablet Styles */
        @media screen and (max-width: 992px) {
            .grid-item {
                flex: 0 0 calc(50% - 10px);
            }
        }

        /* Mobile Styles */
        @media screen and (max-width: 576px) {
            .grid-item {
                flex: 0 0 100%;
            }
        }
    </style>
</head>
<body>
    <div class="grid-container">
        <div class="grid-item">
            <img src="https://via.placeholder.com/400x200" alt="Item 1">
            <h2>Item 1</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        </div>
        <div class="grid-item">
            <img src="https://via.placeholder.com/400x200" alt="Item 2">
            <h2>Item 2</h2>
            <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
        </div>
        <div class="grid-item">
            <img src="https://via.placeholder.com/400x200" alt="Item 3">
            <h2>Item 3</h2>
            <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
        </div>
        <div class="grid-item">
            <img src="https://via.placeholder.com/400x200" alt="Item 4">
            <h2>Item 4</h2>
            <p>Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>
    </div>
</body>
</html>
```

### Responsive Form

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Form</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background-color: #f5f5f5;
        }

        .form-container {
            max-width: 600px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            color: #333;
            font-weight: bold;
        }

        input[type="text"],
        input[type="email"],
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }

        .form-row {
            display: flex;
            gap: 20px;
        }

        .form-row .form-group {
            flex: 1;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
        }

        button:hover {
            background-color: #45a049;
        }

        /* Mobile Styles */
        @media screen and (max-width: 576px) {
            .form-container {
                padding: 20px;
            }

            .form-row {
                flex-direction: column;
                gap: 0;
            }

            input[type="text"],
            input[type="email"],
            textarea {
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2 style="margin-bottom: 20px;">Contact Form</h2>
        <form>
            <div class="form-row">
                <div class="form-group">
                    <label for="firstName">First Name</label>
                    <input type="text" id="firstName" name="firstName" required>
                </div>
                <div class="form-group">
                    <label for="lastName">Last Name</label>
                    <input type="text" id="lastName" name="lastName" required>
                </div>
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" required>
            </div>
            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" name="message" rows="5" required></textarea>
            </div>
            <button type="submit">Send Message</button>
        </form>
    </div>
</body>
</html>
```

## 6. Best Practices

### 1. Gunakan Relative Units
```css
/* Hindari */
.container {
    width: 960px;
}

/* Lebih baik */
.container {
    width: 90%;
    max-width: 960px;
}
```

### 2. Flexible Images
```css
img {
    max-width: 100%;
    height: auto;
}
```

### 3. Mobile-First Approach
```css
/* Base styles (mobile) */
.element {
    width: 100%;
}

/* Tablet styles */
@media (min-width: 768px) {
    .element {
        width: 50%;
    }
}

/* Desktop styles */
@media (min-width: 992px) {
    .element {
        width: 33.33%;
    }
}
```

### 4. Breakpoint Consistency
```css
/* Define breakpoints as variables */
:root {
    --mobile: 576px;
    --tablet: 768px;
    --desktop: 992px;
    --large: 1200px;
}

@media (min-width: 768px) {
    /* tablet styles */
}
```

### 5. Testing
- Gunakan Chrome DevTools Device Toolbar
- Test di berbagai perangkat nyata
- Verifikasi pada berbagai browser

## 7. Latihan Mandiri

### Latihan 1: Responsive Header
Buat header yang responsif dengan logo dan menu navigasi yang berubah menjadi menu hamburger di mobile.

### Latihan 2: Responsive Card Layout
Buat layout card yang menampilkan 3 kolom di desktop, 2 kolom di tablet, dan 1 kolom di mobile.

### Latihan 3: Responsive Form
Buat form kontak yang responsif dengan field yang tersusun berbeda di mobile dan desktop.

## Kesimpulan
- Responsive design adalah kunci untuk membuat website yang dapat diakses di berbagai perangkat
- Media queries memungkinkan kita menerapkan style berbeda berdasarkan karakteristik device
- Mobile-first approach adalah praktik terbaik dalam pengembangan modern
- Penggunaan relative units dan flexible images penting untuk responsivitas
- Testing di berbagai perangkat dan browser adalah bagian penting dari proses development

## Referensi Tambahan
- [MDN Web Docs - Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
- [CSS-Tricks - A Complete Guide to CSS Media Queries](https://css-tricks.com/a-complete-guide-to-css-media-queries/)
- [Google Web Fundamentals - Responsive Web Design Basics](https://developers.google.com/web/fundamentals/design-and-ux/responsive)
- [Smashing Magazine - Responsive Web Design Guidelines and Tutorials](https://www.smashingmagazine.com/category/responsive-web-design/)