# Hari 12: Flexbox Part 2 (Justify, Align)

## Tujuan Pembelajaran
- Memahami secara mendalam properti justify-content dan align-items
- Mempelajari berbagai nilai dan penggunaan properti justify dan align
- Membuat layout dengan berbagai jenis perataan dan distribusi ruang
- Menerapkan kombinasi justify dan align untuk layout yang kompleks
- Membuat layout center, space-between, dan variasi lainnya

## 1. Pendalaman Justify Content

### Properti justify-content
Properti `justify-content` mengatur bagaimana browser mendistribusikan ruang antara dan di sekitar item-item flex sepanjang main axis container.

### Nilai-nilai justify-content

#### 1. flex-start (default)
```css
.container {
    display: flex;
    justify-content: flex-start;
}
```
- Items diletakkan di awal container
- Tidak ada ruang di awal items
- Semua ruang ekstra di akhir items

#### 2. flex-end
```css
.container {
    display: flex;
    justify-content: flex-end;
}
```
- Items diletakkan di akhir container
- Tidak ada ruang di akhir items
- Semua ruang ekstra di awal items

#### 3. center
```css
.container {
    display: flex;
    justify-content: center;
}
```
- Items diletakkan di tengah container
- Ruang ekstra dibagi rata di awal dan akhir items

#### 4. space-between
```css
.container {
    display: flex;
    justify-content: space-between;
}
```
- Item pertama di awal container
- Item terakhir di akhir container
- Ruang ekstra didistribusikan merata di antara items

#### 5. space-around
```css
.container {
    display: flex;
    justify-content: space-around;
}
```
- Ruang didistribusikan merata di sekitar setiap item
- Ruang di antara items dua kali lebih besar dari ruang di pinggir

#### 6. space-evenly
```css
.container {
    display: flex;
    justify-content: space-evenly;
}
```
- Ruang didistribusikan merata di antara dan di sekitar items
- Semua ruang memiliki ukuran yang sama

### Contoh Implementasi justify-content

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demonstrasi justify-content</title>
    <style>
        .container {
            margin: 20px;
            padding: 10px;
            background-color: #f0f0f0;
            border: 2px solid #333;
            min-height: 100px;
            display: flex;
        }

        .item {
            padding: 20px;
            background-color: #4CAF50;
            color: white;
            margin: 5px;
            text-align: center;
        }

        .flex-start { justify-content: flex-start; }
        .flex-end { justify-content: flex-end; }
        .center { justify-content: center; }
        .space-between { justify-content: space-between; }
        .space-around { justify-content: space-around; }
        .space-evenly { justify-content: space-evenly; }
    </style>
</head>
<body>
    <h2>flex-start</h2>
    <div class="container flex-start">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>

    <h2>flex-end</h2>
    <div class="container flex-end">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>

    <h2>center</h2>
    <div class="container center">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>

    <h2>space-between</h2>
    <div class="container space-between">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>

    <h2>space-around</h2>
    <div class="container space-around">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>

    <h2>space-evenly</h2>
    <div class="container space-evenly">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
    </div>
</body>
</html>
```

## 2. Pendalaman Align Items

### Properti align-items
Properti `align-items` mengatur bagaimana flex items diletakkan sepanjang cross axis container.

### Nilai-nilai align-items

#### 1. stretch (default)
```css
.container {
    display: flex;
    align-items: stretch;
}
```
- Items diregangkan untuk mengisi container
- Height items menyesuaikan tinggi container

#### 2. flex-start
```css
.container {
    display: flex;
    align-items: flex-start;
}
```
- Items diletakkan di awal cross axis
- Height items sesuai konten

#### 3. flex-end
```css
.container {
    display: flex;
    align-items: flex-end;
}
```
- Items diletakkan di akhir cross axis
- Height items sesuai konten

#### 4. center
```css
.container {
    display: flex;
    align-items: center;
}
```
- Items diletakkan di tengah cross axis
- Height items sesuai konten

#### 5. baseline
```css
.container {
    display: flex;
    align-items: baseline;
}
```
- Items diletakkan sejajar dengan baseline text mereka

### Contoh Implementasi align-items

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demonstrasi align-items</title>
    <style>
        .container {
            margin: 20px;
            padding: 10px;
            background-color: #f0f0f0;
            border: 2px solid #333;
            height: 200px;
            display: flex;
        }

        .item {
            padding: 20px;
            background-color: #2196F3;
            color: white;
            margin: 5px;
            text-align: center;
        }

        .item.tall { padding: 40px; }
        .item.short { padding: 10px; }

        .stretch { align-items: stretch; }
        .flex-start { align-items: flex-start; }
        .flex-end { align-items: flex-end; }
        .center { align-items: center; }
        .baseline { align-items: baseline; }
    </style>
</head>
<body>
    <h2>stretch</h2>
    <div class="container stretch">
        <div class="item">1</div>
        <div class="item tall">2</div>
        <div class="item short">3</div>
    </div>

    <h2>flex-start</h2>
    <div class="container flex-start">
        <div class="item">1</div>
        <div class="item tall">2</div>
        <div class="item short">3</div>
    </div>

    <h2>flex-end</h2>
    <div class="container flex-end">
        <div class="item">1</div>
        <div class="item tall">2</div>
        <div class="item short">3</div>
    </div>

    <h2>center</h2>
    <div class="container center">
        <div class="item">1</div>
        <div class="item tall">2</div>
        <div class="item short">3</div>
    </div>

    <h2>baseline</h2>
    <div class="container baseline">
        <div class="item">1</div>
        <div class="item tall">2</div>
        <div class="item short">3</div>
    </div>
</body>
</html>
```

## 3. Kombinasi Justify dan Align

### Centering Perfect
Salah satu penggunaan paling umum dari kombinasi justify-content dan align-items adalah untuk membuat elemen berada tepat di tengah container.

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perfect Centering dengan Flexbox</title>
    <style>
        .container {
            height: 400px;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .centered-box {
            padding: 50px;
            background-color: #4CAF50;
            color: white;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="centered-box">
            <h2>Perfectly Centered</h2>
            <p>Menggunakan justify-content: center dan align-items: center</p>
        </div>
    </div>
</body>
</html>
```

### Layout Card dengan Space-Between

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout Card dengan Space-Between</title>
    <style>
        .container {
            display: flex;
            justify-content: space-between;
            align-items: stretch;
            gap: 20px;
            padding: 20px;
        }

        .card {
            flex: 1;
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 4px;
        }

        .card-content {
            flex-grow: 1;
            padding: 15px 0;
        }

        .card-footer {
            border-top: 1px solid #eee;
            padding-top: 15px;
            text-align: right;
        }

        .button {
            background-color: #4CAF50;
            color: white;
            padding: 8px 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <img src="https://via.placeholder.com/400x200" alt="Card 1" class="card-image">
            <div class="card-content">
                <h3>Card 1</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
            </div>
            <div class="card-footer">
                <button class="button">Learn More</button>
            </div>
        </div>

        <div class="card">
            <img src="https://via.placeholder.com/400x200" alt="Card 2" class="card-image">
            <div class="card-content">
                <h3>Card 2</h3>
                <p>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
            </div>
            <div class="card-footer">
                <button class="button">Learn More</button>
            </div>
        </div>

        <div class="card">
            <img src="https://via.placeholder.com/400x200" alt="Card 3" class="card-image">
            <div class="card-content">
                <h3>Card 3</h3>
                <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco.</p>
            </div>
            <div class="card-footer">
                <button class="button">Learn More</button>
            </div>
        </div>
    </div>
</body>
</html>
```

## 4. Kasus Penggunaan Umum

### 1. Navigation Bar

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Navigation Bar dengan Flexbox</title>
    <style>
        .navbar {
            background-color: #333;
            padding: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: white;
            font-size: 1.5rem;
            font-weight: bold;
        }

        .nav-links {
            display: flex;
            gap: 1rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: background-color 0.3s;
        }

        .nav-links a:hover {
            background-color: #555;
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="logo">Logo</div>
        <div class="nav-links">
            <a href="#">Home</a>
            <a href="#">About</a>
            <a href="#">Services</a>
            <a href="#">Contact</a>
        </div>
    </nav>
</body>
</html>
```

### 2. Hero Section

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hero Section dengan Flexbox</title>
    <style>
        .hero {
            height: 80vh;
            background-color: #f8f9fa;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
        }

        .hero-content {
            max-width: 800px;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #666;
        }

        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
        }

        .button {
            padding: 1rem 2rem;
            border-radius: 4px;
            text-decoration: none;
            font-weight: bold;
            transition: transform 0.3s;
        }

        .button:hover {
            transform: translateY(-2px);
        }

        .primary {
            background-color: #4CAF50;
            color: white;
        }

        .secondary {
            background-color: transparent;
            color: #4CAF50;
            border: 2px solid #4CAF50;
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="hero-content">
            <h1>Welcome to Our Website</h1>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
            <div class="cta-buttons">
                <a href="#" class="button primary">Get Started</a>
                <a href="#" class="button secondary">Learn More</a>
            </div>
        </div>
    </section>
</body>
</html>
```

## 5. Latihan Mandiri

### Latihan 1: Membuat Footer dengan Kolom
Buat footer responsif dengan beberapa kolom menggunakan kombinasi justify-content dan align-items.

### Latihan 2: Membuat Grid Gallery
Buat gallery foto dengan grid menggunakan Flexbox, dengan gambar-gambar yang tersusun rapi dan responsif.

### Latihan 3: Membuat Form Login Center
Buat form login yang berada tepat di tengah halaman menggunakan teknik centering dengan Flexbox.

## Kesimpulan
- Properti justify-content dan align-items adalah kunci untuk mengatur tata letak elemen dalam Flexbox
- Kombinasi kedua properti ini memungkinkan berbagai jenis layout yang kompleks
- Flexbox membuat proses centering elemen menjadi sangat mudah
- Penggunaan space-between dan space-around sangat berguna untuk distribusi ruang yang merata
- Pemahaman yang baik tentang justify dan align memungkinkan pembuatan layout yang lebih fleksibel dan responsif

## Referensi Tambahan
- [MDN Web Docs - justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
- [MDN Web Docs - align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
- [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - Game interaktif untuk belajar Flexbox