# Hari 9: Positioning: Relative, Absolute, Fixed

## Tujuan Pembelajaran
- Memahami konsep positioning dalam CSS
- Mengenal dan menggunakan berbagai jenis positioning: static, relative, absolute, fixed, dan sticky
- Memahami perbedaan dan kasus penggunaan masing-masing jenis positioning
- Membuat tombol mengambang di sudut layar menggunakan fixed positioning
- Menerapkan positioning dalam layout halaman web

## 1. Pengenalan CSS Positioning

### Apa itu CSS Positioning?
CSS Positioning adalah teknik untuk mengatur posisi elemen HTML di halaman web. Dengan positioning, kita dapat menempatkan elemen di mana saja pada halaman, terlepas dari aliran normal dokumen (normal flow).

### Properti position
Properti `position` dalam CSS memiliki lima nilai utama:
1. `static` (default)
2. `relative`
3. `absolute`
4. `fixed`
5. `sticky`

### Properti Offset
Setelah menentukan jenis positioning dengan properti `position`, kita dapat menggunakan properti offset untuk mengatur posisi elemen:
- `top`: Jarak dari tepi atas
- `right`: Jarak dari tepi kanan
- `bottom`: Jarak dari tepi bawah
- `left`: Jarak dari tepi kiri
- `z-index`: Mengatur tumpukan elemen (stacking order)

## 2. Jenis-jenis Positioning

### Static Positioning
`position: static` adalah nilai default untuk semua elemen HTML. Elemen dengan positioning static mengikuti aliran normal dokumen dan tidak terpengaruh oleh properti offset (top, right, bottom, left).

```css
.static-element {
    position: static;
    /* properti top, right, bottom, left tidak berpengaruh */
}
```

### Relative Positioning
`position: relative` memposisikan elemen relatif terhadap posisi normalnya. Elemen tetap berada dalam aliran normal dokumen, tetapi dapat digeser menggunakan properti offset.

```css
.relative-element {
    position: relative;
    top: 20px;    /* bergeser 20px ke bawah dari posisi normalnya */
    left: 30px;   /* bergeser 30px ke kanan dari posisi normalnya */
}
```

Karakteristik `position: relative`:
- Elemen tetap dalam aliran normal dokumen (tempat aslinya tetap "dipesan")
- Elemen digeser relatif terhadap posisi normalnya
- Elemen lain tidak terpengaruh oleh pergeseran ini
- Dapat menjadi container untuk elemen dengan `position: absolute`

### Absolute Positioning
`position: absolute` memposisikan elemen relatif terhadap ancestor terdekat yang memiliki positioning (selain static). Jika tidak ada ancestor dengan positioning, elemen akan diposisikan relatif terhadap dokumen HTML.

```css
.container {
    position: relative;  /* menjadi referensi untuk elemen absolute di dalamnya */
    width: 500px;
    height: 300px;
    border: 2px solid #333;
}

.absolute-element {
    position: absolute;
    top: 50px;    /* 50px dari tepi atas container */
    left: 100px;  /* 100px dari tepi kiri container */
    width: 200px;
    height: 100px;
    background-color: #f0f0f0;
}
```

Karakteristik `position: absolute`:
- Elemen dikeluarkan dari aliran normal dokumen (tidak ada tempat yang "dipesan")
- Elemen diposisikan relatif terhadap ancestor terdekat yang memiliki positioning
- Elemen lain akan mengabaikan keberadaannya dan dapat tumpang tindih
- Sering digunakan untuk overlay, popup, atau elemen yang perlu ditempatkan di posisi spesifik

### Fixed Positioning
`position: fixed` memposisikan elemen relatif terhadap viewport browser. Elemen akan tetap berada di posisi yang sama meskipun halaman di-scroll.

```css
.fixed-element {
    position: fixed;
    top: 20px;
    right: 20px;
    width: 100px;
    height: 100px;
    background-color: #ff9900;
}
```

Karakteristik `position: fixed`:
- Elemen dikeluarkan dari aliran normal dokumen
- Elemen diposisikan relatif terhadap viewport browser
- Elemen tetap di posisi yang sama saat halaman di-scroll
- Sering digunakan untuk header yang tetap, tombol kembali ke atas, atau elemen navigasi yang selalu terlihat

### Sticky Positioning
`position: sticky` adalah kombinasi dari `relative` dan `fixed`. Elemen berperilaku seperti `relative` sampai mencapai threshold tertentu saat di-scroll, kemudian berperilaku seperti `fixed`.

```css
.sticky-element {
    position: sticky;
    top: 0;       /* elemen akan "menempel" di bagian atas saat di-scroll */
    padding: 10px;
    background-color: #f0f0f0;
}
```

Karakteristik `position: sticky`:
- Elemen tetap dalam aliran normal dokumen sampai mencapai threshold
- Setelah mencapai threshold, elemen berperilaku seperti `fixed`
- Harus menentukan setidaknya satu properti offset (biasanya `top`)
- Sering digunakan untuk header section, navigasi, atau elemen yang perlu tetap terlihat dalam konteks tertentu

## 3. Properti z-index

Properti `z-index` mengontrol urutan tumpukan (stacking order) elemen yang tumpang tindih. Elemen dengan nilai `z-index` lebih tinggi akan muncul di atas elemen dengan nilai `z-index` lebih rendah.

```css
.element-1 {
    position: absolute;
    z-index: 1;
    /* elemen ini akan berada di bawah element-2 */
}

.element-2 {
    position: absolute;
    z-index: 2;
    /* elemen ini akan berada di atas element-1 */
}
```

Catatan penting tentang `z-index`:
- Hanya berlaku untuk elemen dengan positioning (selain static)
- Nilai bisa positif, negatif, atau nol
- Elemen tanpa `z-index` memiliki nilai default 0
- Elemen dengan `z-index` yang sama diurutkan berdasarkan urutan mereka dalam kode HTML
- `z-index` bekerja dalam konteks stacking context

## 4. Contoh Penggunaan Positioning

### Contoh 1: Overlay Text pada Gambar

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Overlay Text pada Gambar</title>
    <style>
        .image-container {
            position: relative;
            width: 400px;
            height: 300px;
        }
        
        .image {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .overlay-text {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 15px;
        }
        
        .overlay-text h3 {
            margin: 0 0 5px 0;
        }
        
        .overlay-text p {
            margin: 0;
        }
    </style>
</head>
<body>
    <div class="image-container">
        <img src="https://via.placeholder.com/400x300" alt="Placeholder Image" class="image">
        <div class="overlay-text">
            <h3>Judul Gambar</h3>
            <p>Deskripsi gambar yang menjelaskan konten gambar.</p>
        </div>
    </div>
</body>
</html>
```

### Contoh 2: Dropdown Menu

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dropdown Menu</title>
    <style>
        .dropdown {
            position: relative;
            display: inline-block;
        }
        
        .dropdown-button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 15px;
            border: none;
            cursor: pointer;
        }
        
        .dropdown-content {
            position: absolute;
            display: none;
            background-color: white;
            min-width: 160px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }
        
        .dropdown-content a {
            display: block;
            padding: 10px 15px;
            text-decoration: none;
            color: #333;
        }
        
        .dropdown-content a:hover {
            background-color: #f0f0f0;
        }
        
        .dropdown:hover .dropdown-content {
            display: block;
        }
    </style>
</head>
<body>
    <div class="dropdown">
        <button class="dropdown-button">Menu</button>
        <div class="dropdown-content">
            <a href="#">Opsi 1</a>
            <a href="#">Opsi 2</a>
            <a href="#">Opsi 3</a>
        </div>
    </div>
</body>
</html>
```

### Contoh 3: Modal/Popup

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modal/Popup</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        
        .modal-trigger {
            background-color: #4CAF50;
            color: white;
            padding: 10px 15px;
            border: none;
            cursor: pointer;
        }
        
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.5);
            display: none;
            justify-content: center;
            align-items: center;
        }
        
        .modal {
            position: relative;
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            width: 400px;
            max-width: 90%;
        }
        
        .modal-close {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 20px;
            cursor: pointer;
        }
        
        .show {
            display: flex;
        }
    </style>
</head>
<body>
    <button class="modal-trigger" onclick="document.getElementById('modal').classList.add('show')">Buka Modal</button>
    
    <div id="modal" class="modal-overlay">
        <div class="modal">
            <span class="modal-close" onclick="document.getElementById('modal').classList.remove('show')">&times;</span>
            <h2>Judul Modal</h2>
            <p>Ini adalah konten modal. Anda dapat menambahkan teks, gambar, atau elemen lain di sini.</p>
            <button onclick="document.getElementById('modal').classList.remove('show')">Tutup</button>
        </div>
    </div>
</body>
</html>
```

## 5. Praktik: Membuat Tombol Mengambang di Sudut Layar

Sekarang kita akan membuat tombol "Kembali ke Atas" yang mengambang di sudut kanan bawah layar. Tombol ini akan tetap terlihat saat pengguna men-scroll halaman.

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tombol Mengambang</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .content {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Gaya untuk tombol kembali ke atas */
        .back-to-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #4CAF50;
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            text-decoration: none;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
            transition: background-color 0.3s;
        }
        
        .back-to-top:hover {
            background-color: #45a049;
        }
        
        /* Gaya untuk ikon panah */
        .arrow-up {
            border: solid white;
            border-width: 0 3px 3px 0;
            display: inline-block;
            padding: 5px;
            transform: rotate(-135deg);
            -webkit-transform: rotate(-135deg);
        }
    </style>
</head>
<body>
    <div class="content">
        <h1>Tombol Mengambang dengan Fixed Positioning</h1>
        
        <!-- Konten dummy untuk membuat halaman panjang -->
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
        
        <!-- Ulangi paragraf beberapa kali untuk membuat halaman panjang -->
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
        
        <!-- Ulangi paragraf ini 10-15 kali untuk membuat halaman cukup panjang -->
        <!-- ... -->
        
    </div>
    
    <!-- Tombol kembali ke atas -->
    <a href="#" class="back-to-top" onclick="window.scrollTo({top: 0, behavior: 'smooth'}); return false;">
        <i class="arrow-up"></i>
    </a>
</body>
</html>
```

### Penjelasan Kode:
1. Tombol menggunakan `position: fixed` agar tetap terlihat di posisi yang sama saat halaman di-scroll
2. Properti `bottom: 20px` dan `right: 20px` menempatkan tombol di sudut kanan bawah viewport
3. Tombol dibuat berbentuk lingkaran dengan `border-radius: 50%`
4. Ikon panah dibuat menggunakan border CSS dengan transform rotate
5. Saat diklik, tombol akan menggulir halaman ke atas dengan smooth scrolling menggunakan JavaScript

## 6. Contoh Lanjutan: Sticky Header

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sticky Header</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .header {
            background-color: #333;
            color: white;
            padding: 10px 20px;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
        }
        
        .menu {
            list-style: none;
            display: flex;
            margin: 0;
            padding: 0;
        }
        
        .menu li {
            margin-left: 20px;
        }
        
        .menu a {
            color: white;
            text-decoration: none;
        }
        
        .content {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .section {
            min-height: 500px;
            padding: 20px;
            margin-bottom: 20px;
            background-color: #f0f0f0;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <header class="header">
        <nav class="nav">
            <div class="logo">Logo</div>
            <ul class="menu">
                <li><a href="#section1">Bagian 1</a></li>
                <li><a href="#section2">Bagian 2</a></li>
                <li><a href="#section3">Bagian 3</a></li>
                <li><a href="#section4">Bagian 4</a></li>
            </ul>
        </nav>
    </header>
    
    <div class="content">
        <section id="section1" class="section">
            <h2>Bagian 1</h2>
            <p>Konten bagian 1...</p>
        </section>
        
        <section id="section2" class="section">
            <h2>Bagian 2</h2>
            <p>Konten bagian 2...</p>
        </section>
        
        <section id="section3" class="section">
            <h2>Bagian 3</h2>
            <p>Konten bagian 3...</p>
        </section>
        
        <section id="section4" class="section">
            <h2>Bagian 4</h2>
            <p>Konten bagian 4...</p>
        </section>
    </div>
</body>
</html>
```

## 7. Latihan Mandiri

### Latihan 1: Membuat Card dengan Badge
Buat sebuah card produk dengan badge "Sale" di sudut kanan atas.

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Card dengan Badge</title>
    <style>
        /* Tulis CSS Anda di sini */
        .card {
            position: relative;
            width: 300px;
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
        }
        
        .badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: #ff5722;
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-weight: bold;
        }
        
        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .card-content {
            padding: 15px;
        }
    </style>
</head>
<body>
    <div class="card">
        <div class="badge">Sale</div>
        <img src="https://via.placeholder.com/300x200" alt="Product Image" class="card-image">
        <div class="card-content">
            <h3>Nama Produk</h3>
            <p>Deskripsi produk singkat di sini.</p>
            <p><strong>Rp 199.000</strong> <s>Rp 250.000</s></p>
        </div>
    </div>
</body>
</html>
```

### Latihan 2: Membuat Navigasi Sticky dengan Dropdown
Buat navigasi sticky di bagian atas halaman dengan dropdown menu.

### Latihan 3: Membuat Tooltip
Buat elemen dengan tooltip yang muncul saat hover.

## Kesimpulan
- CSS Positioning memungkinkan kita mengatur posisi elemen di halaman web
- Ada lima jenis positioning: static, relative, absolute, fixed, dan sticky
- Setiap jenis positioning memiliki karakteristik dan kasus penggunaan yang berbeda
- Properti offset (top, right, bottom, left) digunakan untuk mengatur posisi elemen
- Properti z-index mengontrol urutan tumpukan elemen yang tumpang tindih
- Positioning sangat berguna untuk membuat layout kompleks, overlay, dropdown, modal, dan elemen UI lainnya

## Referensi Tambahan
- [MDN Web Docs - position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [CSS-Tricks - Position](https://css-tricks.com/almanac/properties/p/position/)
- [W3Schools - CSS Layout - The position Property](https://www.w3schools.com/css/css_positioning.asp)
- [Learn CSS Positioning in Ten Steps](http://www.barelyfitz.com/screencast/html-training/css/positioning/)