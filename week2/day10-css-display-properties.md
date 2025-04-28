# Hari 10: Display: Block, Inline, Inline-Block

## Tujuan Pembelajaran
- Memahami properti display dalam CSS
- Mengenal perbedaan antara display: block, inline, dan inline-block
- Memahami kasus penggunaan masing-masing nilai display
- Menerapkan properti display untuk mengatur layout elemen
- Menguji perbedaan display dengan contoh nyata

## 1. Pengenalan Properti Display

### Apa itu Properti Display?
Properti `display` dalam CSS menentukan bagaimana sebuah elemen HTML ditampilkan di halaman web. Properti ini mengontrol perilaku box model elemen dan bagaimana elemen tersebut berinteraksi dengan elemen lain di sekitarnya.

### Nilai-nilai Umum Properti Display
- `block`: Elemen mengambil seluruh lebar yang tersedia
- `inline`: Elemen hanya mengambil lebar sesuai kontennya
- `inline-block`: Kombinasi dari block dan inline
- `none`: Elemen tidak ditampilkan sama sekali
- `flex`: Elemen menjadi flex container
- `grid`: Elemen menjadi grid container
- `table`: Elemen berperilaku seperti tabel HTML

Pada pembelajaran hari ini, kita akan fokus pada tiga nilai utama: `block`, `inline`, dan `inline-block`.

## 2. Display: Block

### Karakteristik Display Block
- Mengambil seluruh lebar yang tersedia (100% dari parent container)
- Selalu dimulai pada baris baru
- Dapat diatur width, height, margin, dan padding
- Jika tidak diatur width, akan mengambil 100% lebar dari parent container
- Menghormati semua properti margin dan padding

### Elemen HTML yang Secara Default Bersifat Block
- `<div>`
- `<h1>` sampai `<h6>`
- `<p>`
- `<form>`
- `<header>`, `<footer>`, `<section>`, `<article>`, `<aside>`, `<nav>`
- `<ul>`, `<ol>`, `<li>`
- `<table>`
- `<hr>`
- `<blockquote>`
- `<pre>`

### Contoh Display Block

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Display Block</title>
    <style>
        .block-element {
            display: block;
            background-color: #f0f0f0;
            border: 2px solid #333;
            padding: 15px;
            margin: 10px 0;
            /* width: 50%; */ /* Uncomment untuk melihat efeknya */
        }
    </style>
</head>
<body>
    <h2>Contoh Display Block</h2>
    
    <div class="block-element">
        Ini adalah elemen block pertama. Elemen block mengambil seluruh lebar yang tersedia.
    </div>
    
    <div class="block-element">
        Ini adalah elemen block kedua. Perhatikan bahwa elemen ini selalu dimulai pada baris baru.
    </div>
    
    <div class="block-element">
        Ini adalah elemen block ketiga. Anda dapat mengatur width, height, margin, dan padding pada elemen block.
    </div>
</body>
</html>
```

## 3. Display: Inline

### Karakteristik Display Inline
- Hanya mengambil lebar sesuai dengan kontennya
- Tidak memulai baris baru
- Tidak dapat diatur width dan height
- Margin dan padding hanya berpengaruh secara horizontal (left dan right), tidak vertikal (top dan bottom)
- Elemen inline dapat berada dalam satu baris dengan elemen inline lainnya

### Elemen HTML yang Secara Default Bersifat Inline
- `<span>`
- `<a>`
- `<strong>`, `<em>`, `<b>`, `<i>`
- `<img>`
- `<button>`
- `<input>`, `<label>`, `<select>`, `<textarea>`
- `<code>`, `<cite>`, `<small>`
- `<sub>`, `<sup>`

### Contoh Display Inline

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Display Inline</title>
    <style>
        .inline-element {
            display: inline;
            background-color: #ffdddd;
            border: 2px solid #ff5555;
            padding: 5px;
            margin: 5px;
            /* width dan height tidak berpengaruh pada elemen inline */
            /* width: 100px; */
            /* height: 100px; */
        }
    </style>
</head>
<body>
    <h2>Contoh Display Inline</h2>
    
    <span class="inline-element">Ini adalah elemen inline pertama.</span>
    <span class="inline-element">Ini adalah elemen inline kedua.</span>
    <span class="inline-element">Ini adalah elemen inline ketiga.</span>
    
    <p>
        Perhatikan bahwa semua elemen inline di atas berada dalam satu baris yang sama.
        <span class="inline-element">Elemen inline</span> juga dapat berada di dalam paragraf
        dan akan mengalir dengan teks.
    </p>
</body>
</html>
```

## 4. Display: Inline-Block

### Karakteristik Display Inline-Block
- Kombinasi dari karakteristik block dan inline
- Mengambil lebar sesuai kontennya seperti elemen inline
- Tidak memulai baris baru seperti elemen inline
- Dapat diatur width, height, margin, dan padding seperti elemen block
- Menghormati semua properti margin dan padding seperti elemen block
- Elemen inline-block dapat berada dalam satu baris dengan elemen inline atau inline-block lainnya

### Contoh Display Inline-Block

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Display Inline-Block</title>
    <style>
        .inline-block-element {
            display: inline-block;
            background-color: #ddffdd;
            border: 2px solid #55aa55;
            padding: 15px;
            margin: 10px;
            width: 150px;
            height: 100px;
            vertical-align: top; /* Untuk menyelaraskan elemen secara vertikal */
        }
    </style>
</head>
<body>
    <h2>Contoh Display Inline-Block</h2>
    
    <div class="inline-block-element">
        Elemen inline-block pertama.
    </div>
    
    <div class="inline-block-element">
        Elemen inline-block kedua.
    </div>
    
    <div class="inline-block-element">
        Elemen inline-block ketiga.
    </div>
    
    <p>
        Perhatikan bahwa elemen inline-block di atas berada dalam satu baris,
        tetapi dapat diatur width, height, margin, dan padding.
    </p>
</body>
</html>
```

## 5. Perbandingan Block, Inline, dan Inline-Block

### Tabel Perbandingan

| Properti | Block | Inline | Inline-Block |
|----------|-------|--------|--------------|
| Memulai baris baru | Ya | Tidak | Tidak |
| Mengambil lebar penuh | Ya | Tidak | Tidak |
| Dapat diatur width | Ya | Tidak | Ya |
| Dapat diatur height | Ya | Tidak | Ya |
| Margin (semua sisi) | Ya | Hanya left/right | Ya |
| Padding (semua sisi) | Ya | Visual saja, tidak memengaruhi layout | Ya |

### Contoh Perbandingan Visual

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perbandingan Display</title>
    <style>
        .container {
            border: 1px dashed #999;
            margin: 20px 0;
            padding: 10px;
        }
        
        .block {
            display: block;
            background-color: #f0f0f0;
            border: 2px solid #333;
            padding: 15px;
            margin: 10px 0;
            width: 50%;
        }
        
        .inline {
            display: inline;
            background-color: #ffdddd;
            border: 2px solid #ff5555;
            padding: 15px;
            margin: 10px;
            width: 50%; /* Tidak berpengaruh */
            height: 50px; /* Tidak berpengaruh */
        }
        
        .inline-block {
            display: inline-block;
            background-color: #ddffdd;
            border: 2px solid #55aa55;
            padding: 15px;
            margin: 10px;
            width: 30%;
            height: 50px;
            vertical-align: top;
        }
    </style>
</head>
<body>
    <h1>Perbandingan Display: Block, Inline, dan Inline-Block</h1>
    
    <h2>Display: Block</h2>
    <div class="container">
        <div class="block">Elemen Block 1</div>
        <div class="block">Elemen Block 2</div>
        <div class="block">Elemen Block 3</div>
    </div>
    
    <h2>Display: Inline</h2>
    <div class="container">
        <span class="inline">Elemen Inline 1</span>
        <span class="inline">Elemen Inline 2</span>
        <span class="inline">Elemen Inline 3</span>
    </div>
    
    <h2>Display: Inline-Block</h2>
    <div class="container">
        <div class="inline-block">Elemen Inline-Block 1</div>
        <div class="inline-block">Elemen Inline-Block 2</div>
        <div class="inline-block">Elemen Inline-Block 3</div>
    </div>
</body>
</html>
```

## 6. Kasus Penggunaan

### Kapan Menggunakan Display Block
- Untuk elemen yang harus mengambil seluruh lebar yang tersedia
- Untuk elemen yang harus dimulai pada baris baru
- Untuk elemen struktural seperti header, footer, section, article
- Untuk paragraf, heading, dan elemen teks lainnya yang memerlukan baris baru

### Kapan Menggunakan Display Inline
- Untuk elemen teks yang harus mengalir dengan teks lainnya
- Untuk link, span, dan elemen lain yang tidak memerlukan baris baru
- Untuk elemen yang tidak memerlukan pengaturan width dan height
- Untuk elemen yang harus berada dalam satu baris dengan elemen lainnya

### Kapan Menggunakan Display Inline-Block
- Untuk membuat layout multi-kolom sederhana
- Untuk membuat navigasi horizontal
- Untuk elemen yang harus berada dalam satu baris tetapi memerlukan pengaturan width dan height
- Untuk elemen yang memerlukan margin dan padding pada semua sisi

## 7. Contoh Praktis

### Contoh 1: Navigasi Horizontal dengan Inline-Block

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Navigasi Horizontal</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .nav {
            background-color: #333;
            padding: 10px;
            text-align: center;
        }
        
        .nav-item {
            display: inline-block;
            padding: 10px 15px;
            margin: 0 5px;
            background-color: #444;
            color: white;
            text-decoration: none;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        
        .nav-item:hover {
            background-color: #666;
        }
    </style>
</head>
<body>
    <div class="nav">
        <a href="#" class="nav-item">Beranda</a>
        <a href="#" class="nav-item">Tentang</a>
        <a href="#" class="nav-item">Layanan</a>
        <a href="#" class="nav-item">Portofolio</a>
        <a href="#" class="nav-item">Kontak</a>
    </div>
</body>
</html>
```

### Contoh 2: Grid Sederhana dengan Inline-Block

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Sederhana</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        
        .grid-container {
            text-align: center; /* Untuk mengatasi masalah spasi antar elemen inline-block */
            margin: 0 -10px; /* Kompensasi margin pada grid-item */
        }
        
        .grid-item {
            display: inline-block;
            width: calc(33.33% - 20px); /* 3 kolom dengan margin */
            margin: 10px;
            padding: 20px;
            background-color: #f0f0f0;
            border-radius: 4px;
            box-sizing: border-box;
            vertical-align: top;
            text-align: left;
        }
        
        .grid-item img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 4px;
        }
        
        .grid-item h3 {
            margin-top: 10px;
            margin-bottom: 5px;
        }
        
        .grid-item p {
            color: #666;
        }
    </style>
</head>
<body>
    <h1>Grid Sederhana dengan Inline-Block</h1>
    
    <div class="grid-container">
        <div class="grid-item">
            <img src="https://via.placeholder.com/300x150" alt="Item 1">
            <h3>Item 1</h3>
            <p>Deskripsi item 1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        
        <div class="grid-item">
            <img src="https://via.placeholder.com/300x150" alt="Item 2">
            <h3>Item 2</h3>
            <p>Deskripsi item 2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        
        <div class="grid-item">
            <img src="https://via.placeholder.com/300x150" alt="Item 3">
            <h3>Item 3</h3>
            <p>Deskripsi item 3. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        
        <div class="grid-item">
            <img src="https://via.placeholder.com/300x150" alt="Item 4">
            <h3>Item 4</h3>
            <p>Deskripsi item 4. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        
        <div class="grid-item">
            <img src="https://via.placeholder.com/300x150" alt="Item 5">
            <h3>Item 5</h3>
            <p>Deskripsi item 5. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
        
        <div class="grid-item">
            <img src="https://via.placeholder.com/300x150" alt="Item 6">
            <h3>Item 6</h3>
            <p>Deskripsi item 6. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
    </div>
</body>
</html>
```

### Contoh 3: Mengubah Elemen Inline Menjadi Block

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mengubah Display</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        
        /* Mengubah link (inline) menjadi block */
        .block-link {
            display: block;
            background-color: #f0f0f0;
            padding: 10px;
            margin: 5px 0;
            text-decoration: none;
            color: #333;
            border-left: 3px solid #4CAF50;
            transition: background-color 0.3s;
        }
        
        .block-link:hover {
            background-color: #e0e0e0;
        }
        
        /* Mengubah div (block) menjadi inline */
        .inline-div {
            display: inline;
            background-color: #ffdddd;
            padding: 5px;
            border: 1px solid #ff5555;
        }
    </style>
</head>
<body>
    <h1>Mengubah Properti Display</h1>
    
    <h2>Link (Inline) Menjadi Block</h2>
    <a href="#" class="block-link">Link 1</a>
    <a href="#" class="block-link">Link 2</a>
    <a href="#" class="block-link">Link 3</a>
    
    <h2>Div (Block) Menjadi Inline</h2>
    <p>
        Ini adalah paragraf dengan 
        <div class="inline-div">div yang diubah menjadi inline</div>
        di tengah paragraf.
    </p>
</body>
</html>
```

## 8. Tantangan dan Solusi

### Tantangan dengan Display Inline-Block
1. **Spasi antar elemen**: Secara default, ada spasi kecil antara elemen inline-block yang disebabkan oleh whitespace dalam HTML.

#### Solusi:
- Menghapus whitespace dalam HTML (tidak disarankan karena mengurangi keterbacaan)
- Mengatur `font-size: 0` pada parent dan mengembalikan `font-size` pada child
- Menggunakan margin negatif
- Menggunakan `float` (alternatif lain, tetapi memiliki tantangan tersendiri)
- Menggunakan Flexbox atau Grid (solusi modern yang lebih baik)

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Solusi Spasi Inline-Block</title>
    <style>
        .container {
            border: 1px solid #999;
            margin: 20px 0;
            padding: 10px;
        }
        
        .item {
            display: inline-block;
            width: 100px;
            height: 100px;
            background-color: #f0f0f0;
            border: 1px solid #333;
            text-align: center;
            line-height: 100px;
        }
        
        /* Solusi 1: font-size: 0 */
        .solution-1 {
            font-size: 0;
        }
        
        .solution-1 .item {
            font-size: 16px;
        }
        
        /* Solusi 2: margin negatif */
        .solution-2 .item {
            margin-right: -4px;
        }
        
        /* Solusi 3: float */
        .solution-3::after {
            content: "";
            display: table;
            clear: both;
        }
        
        .solution-3 .item {
            float: left;
        }
        
        /* Solusi 4: flexbox */
        .solution-4 {
            display: flex;
        }
    </style>
</head>
<body>
    <h1>Solusi untuk Spasi antar Elemen Inline-Block</h1>
    
    <h2>Masalah: Spasi Default</h2>
    <div class="container">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
    
    <h2>Solusi 1: font-size: 0</h2>
    <div class="container solution-1">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
    
    <h2>Solusi 2: margin negatif</h2>
    <div class="container solution-2">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
    
    <h2>Solusi 3: float</h2>
    <div class="container solution-3">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
    
    <h2>Solusi 4: flexbox</h2>
    <div class="container solution-4">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
</body>
</html>
```

## 9. Praktik: Uji Beda Display dengan Contoh Nyata

### Langkah-langkah:
1. Buat file HTML baru dengan nama `display-test.html`
2. Salin kode HTML berikut
3. Buka file di browser
4. Uji dan amati perbedaan antara display block, inline, dan inline-block

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Uji Beda Display</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        
        .container {
            border: 1px dashed #999;
            margin: 20px 0;
            padding: 10px;
        }
        
        .controls {
            margin-bottom: 20px;
        }
        
        .btn {
            padding: 8px 12px;
            margin-right: 5px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        
        .element {
            background-color: #f0f0f0;
            border: 2px solid #333;
            padding: 15px;
            margin: 10px;
            width: 200px;
            height: 100px;
        }
        
        .block {
            display: block;
        }
        
        .inline {
            display: inline;
        }
        
        .inline-block {
            display: inline-block;
        }
        
        .highlight {
            background-color: #ffff99;
        }
    </style>
</head>
<body>
    <h1>Uji Beda Display: Block, Inline, dan Inline-Block</h1>
    
    <div class="controls">
        <button class="btn" onclick="setDisplay('block')">Set Block</button>
        <button class="btn" onclick="setDisplay('inline')">Set Inline</button>
        <button class="btn" onclick="setDisplay('inline-block')">Set Inline-Block</button>
    </div>
    
    <div class="container">
        <div class="element" id="element1">
            Elemen 1
        </div>
        <div class="element" id="element2">
            Elemen 2
        </div>
        <div class="element" id="element3">
            Elemen 3
        </div>
    </div>
    
    <div class="info">
        <h3>Informasi Display Saat Ini: <span id="current-display">block</span></h3>
        <p id="display-info">
            Elemen dengan display: block mengambil seluruh lebar yang tersedia dan selalu dimulai pada baris baru.
        </p>
    </div>
    
    <script>
        function setDisplay(displayType) {
            const elements = document.querySelectorAll('.element');
            const currentDisplay = document.getElementById('current-display');
            const displayInfo = document.getElementById('display-info');
            
            elements.forEach(element => {
                element.className = 'element ' + displayType;
            });
            
            currentDisplay.textContent = displayType;
            
            if (displayType === 'block') {
                displayInfo.textContent = 'Elemen dengan display: block mengambil seluruh lebar yang tersedia dan selalu dimulai pada baris baru.';
            } else if (displayType === 'inline') {
                displayInfo.textContent = 'Elemen dengan display: inline hanya mengambil lebar sesuai kontennya dan tidak dapat diatur width dan height.';
            } else if (displayType === 'inline-block') {
                displayInfo.textContent = 'Elemen dengan display: inline-block mengambil lebar sesuai kontennya tetapi dapat diatur width dan height.';
            }
        }
    </script>
</body>
</html>
```

## 10. Latihan Mandiri

### Latihan 1: Membuat Menu Navigasi
Buat menu navigasi horizontal menggunakan display inline-block.

### Latihan 2: Membuat Gallery Foto
Buat gallery foto dengan grid menggunakan display inline-block.

### Latihan 3: Mengubah Tampilan List
Ubah tampilan list `<ul>` dan `<li>` menggunakan properti display.

## Kesimpulan
- Properti `display` mengontrol bagaimana elemen HTML ditampilkan di halaman web
- `display: block` membuat elemen mengambil seluruh lebar yang tersedia dan selalu dimulai pada baris baru
- `display: inline` membuat elemen hanya mengambil lebar sesuai kontennya dan tidak dapat diatur width dan height
- `display: inline-block` adalah kombinasi dari block dan inline, mengambil lebar sesuai kontennya tetapi dapat diatur width dan height
- Pemilihan nilai display yang tepat sangat penting untuk membuat layout yang sesuai dengan kebutuhan
- Meskipun ada teknologi layout modern seperti Flexbox dan Grid, pemahaman tentang display block, inline, dan inline-block tetap penting sebagai dasar CSS

## Referensi Tambahan
- [MDN Web Docs - display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
- [CSS-Tricks - Almanac: display](https://css-tricks.com/almanac/properties/d/display/)
- [W3Schools - CSS Layout - The display Property](https://www.w3schools.com/css/css_display_visibility.asp)
- [Smashing Magazine - Understanding CSS Display](https://www.smashingmagazine.com/2019/04/display-two-value/)