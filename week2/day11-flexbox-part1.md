# Hari 11: Flexbox Part 1 (Main Axis, Cross Axis)

## Tujuan Pembelajaran
- Memahami konsep dasar Flexbox dalam CSS
- Mengenal istilah-istilah penting dalam Flexbox: flex container, flex item, main axis, cross axis
- Mempelajari properti dasar Flexbox untuk container
- Memahami cara kerja main axis dan cross axis
- Membuat layout kolom sederhana menggunakan Flexbox

## 1. Pengenalan Flexbox

### Apa itu Flexbox?
Flexbox (Flexible Box Layout) adalah model layout satu dimensi dalam CSS yang dirancang untuk menyusun elemen dalam baris atau kolom. Flexbox memudahkan pembuatan layout yang responsif dan fleksibel tanpa menggunakan float atau positioning.

### Mengapa Menggunakan Flexbox?
- Menyederhanakan pembuatan layout yang kompleks
- Menyelaraskan dan mendistribusikan ruang antar item
- Mengubah urutan tampilan elemen tanpa mengubah HTML
- Membuat layout yang responsif dengan mudah
- Menangani ukuran elemen yang berbeda-beda dengan lebih baik

### Browser Support
Flexbox didukung oleh semua browser modern. Namun, beberapa browser lama mungkin memerlukan prefix vendor atau tidak mendukung semua fitur Flexbox.

## 2. Terminologi Flexbox

### Flex Container dan Flex Items
- **Flex Container**: Elemen parent yang memiliki `display: flex` atau `display: inline-flex`
- **Flex Items**: Elemen-elemen child langsung dari flex container

```html
<div class="flex-container">  <!-- Flex Container -->
    <div class="item">Item 1</div>  <!-- Flex Item -->
    <div class="item">Item 2</div>  <!-- Flex Item -->
    <div class="item">Item 3</div>  <!-- Flex Item -->
</div>
```

```css
.flex-container {
    display: flex;
}
```

### Main Axis dan Cross Axis
- **Main Axis**: Sumbu utama flex container, arahnya ditentukan oleh properti `flex-direction`
- **Cross Axis**: Sumbu yang tegak lurus dengan main axis

![Flexbox Axes](https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg)

### Main Start, Main End, Cross Start, Cross End
- **Main Start**: Titik awal main axis
- **Main End**: Titik akhir main axis
- **Cross Start**: Titik awal cross axis
- **Cross End**: Titik akhir cross axis

### Main Size dan Cross Size
- **Main Size**: Ukuran flex item sepanjang main axis (width atau height, tergantung flex-direction)
- **Cross Size**: Ukuran flex item sepanjang cross axis

## 3. Properti Flex Container

### display
Mendefinisikan elemen sebagai flex container.

```css
.container {
    display: flex; /* atau inline-flex */
}
```

- `flex`: Membuat flex container sebagai block
- `inline-flex`: Membuat flex container sebagai inline

### flex-direction
Menentukan arah main axis.

```css
.container {
    flex-direction: row | row-reverse | column | column-reverse;
}
```

- `row` (default): Dari kiri ke kanan
- `row-reverse`: Dari kanan ke kiri
- `column`: Dari atas ke bawah
- `column-reverse`: Dari bawah ke atas

![Flex Direction](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

### flex-wrap
Menentukan apakah flex items harus wrap (pindah baris/kolom) jika tidak cukup ruang.

```css
.container {
    flex-wrap: nowrap | wrap | wrap-reverse;
}
```

- `nowrap` (default): Semua flex items berada dalam satu baris/kolom
- `wrap`: Flex items akan wrap ke baris/kolom berikutnya jika perlu
- `wrap-reverse`: Seperti wrap tetapi dalam urutan terbalik

![Flex Wrap](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

### flex-flow
Shorthand untuk `flex-direction` dan `flex-wrap`.

```css
.container {
    flex-flow: row nowrap; /* default */
}
```

## 4. Main Axis dan Cross Axis Secara Detail

### Main Axis
Main axis adalah sumbu utama yang ditentukan oleh properti `flex-direction`. Arah main axis menentukan bagaimana flex items disusun dalam flex container.

#### Properti yang Bekerja pada Main Axis:
- `justify-content`: Mengatur alignment flex items sepanjang main axis

```css
.container {
    justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

- `flex-start` (default): Items diletakkan di awal main axis
- `flex-end`: Items diletakkan di akhir main axis
- `center`: Items diletakkan di tengah main axis
- `space-between`: Items didistribusikan merata; item pertama di awal, item terakhir di akhir
- `space-around`: Items didistribusikan merata dengan ruang yang sama di sekitarnya
- `space-evenly`: Items didistribusikan merata dengan ruang yang sama di antara dan sekitarnya

![Justify Content](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)

### Cross Axis
Cross axis adalah sumbu yang tegak lurus dengan main axis. Jika main axis horizontal, maka cross axis vertikal, dan sebaliknya.

#### Properti yang Bekerja pada Cross Axis:
- `align-items`: Mengatur alignment flex items sepanjang cross axis

```css
.container {
    align-items: stretch | flex-start | flex-end | center | baseline;
}
```

- `stretch` (default): Items diregangkan untuk mengisi container
- `flex-start`: Items diletakkan di awal cross axis
- `flex-end`: Items diletakkan di akhir cross axis
- `center`: Items diletakkan di tengah cross axis
- `baseline`: Items diletakkan sejajar dengan baseline mereka

![Align Items](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)

- `align-content`: Mengatur alignment baris/kolom flex items ketika ada ruang ekstra di cross axis (hanya bekerja jika ada multiple lines)

```css
.container {
    align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

![Align Content](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)

## 5. Contoh Praktis Main Axis dan Cross Axis

### Contoh 1: Row Direction (Default)

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox - Row Direction</title>
    <style>
        .container {
            display: flex;
            flex-direction: row; /* default */
            background-color: #f0f0f0;
            border: 2px solid #333;
            padding: 10px;
            height: 200px; /* untuk menunjukkan efek align-items */
        }
        
        .item {
            background-color: #4CAF50;
            color: white;
            padding: 20px;
            margin: 10px;
            font-size: 18px;
        }
        
        /* Untuk menunjukkan main axis */
        .main-axis {
            position: relative;
        }
        
        .main-axis::after {
            content: "Main Axis →";
            position: absolute;
            bottom: -30px;
            left: 0;
            right: 0;
            text-align: center;
            color: #ff5722;
            font-weight: bold;
        }
        
        /* Untuk menunjukkan cross axis */
        .cross-axis {
            position: relative;
        }
        
        .cross-axis::before {
            content: "↑";
            position: absolute;
            left: -30px;
            top: 50%;
            transform: translateY(-50%);
            color: #2196F3;
            font-weight: bold;
            font-size: 20px;
        }
        
        .cross-axis::after {
            content: "Cross Axis";
            position: absolute;
            left: -30px;
            top: 50%;
            transform: translateY(-50%) rotate(-90deg);
            transform-origin: right center;
            color: #2196F3;
            font-weight: bold;
            white-space: nowrap;
        }
    </style>
</head>
<body>
    <h1>Flexbox - Row Direction (Default)</h1>
    <p>Main Axis: Horizontal (left to right)</p>
    <p>Cross Axis: Vertical (top to bottom)</p>
    
    <div class="container main-axis cross-axis">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
</body>
</html>
```

### Contoh 2: Column Direction

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox - Column Direction</title>
    <style>
        .container {
            display: flex;
            flex-direction: column;
            background-color: #f0f0f0;
            border: 2px solid #333;
            padding: 10px;
            width: 300px; /* untuk menunjukkan efek align-items */
        }
        
        .item {
            background-color: #2196F3;
            color: white;
            padding: 20px;
            margin: 10px;
            font-size: 18px;
        }
        
        /* Untuk menunjukkan main axis */
        .main-axis {
            position: relative;
        }
        
        .main-axis::after {
            content: "↓";
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            color: #ff5722;
            font-weight: bold;
            font-size: 20px;
        }
        
        .main-axis::before {
            content: "Main Axis";
            position: absolute;
            top: 25px;
            left: 50%;
            transform: translateX(-50%);
            color: #ff5722;
            font-weight: bold;
        }
        
        /* Untuk menunjukkan cross axis */
        .cross-axis {
            position: relative;
        }
        
        .cross-axis::before {
            content: "Cross Axis →";
            position: absolute;
            left: -120px;
            top: 50%;
            transform: translateY(-50%);
            color: #4CAF50;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Flexbox - Column Direction</h1>
    <p>Main Axis: Vertical (top to bottom)</p>
    <p>Cross Axis: Horizontal (left to right)</p>
    
    <div class="container main-axis cross-axis">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
</body>
</html>
```

## 6. Praktik: Layout Kolom Sederhana dengan Flexbox

### Contoh Layout 2 Kolom

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout 2 Kolom dengan Flexbox</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .container {
            display: flex;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .sidebar {
            flex: 1;
            background-color: #f0f0f0;
            padding: 20px;
        }
        
        .content {
            flex: 3;
            padding: 20px;
        }
        
        .header {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        .footer {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar, .content {
                flex: auto;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>Layout 2 Kolom dengan Flexbox</h1>
    </div>
    
    <div class="container">
        <div class="sidebar">
            <h2>Sidebar</h2>
            <ul>
                <li><a href="#">Link 1</a></li>
                <li><a href="#">Link 2</a></li>
                <li><a href="#">Link 3</a></li>
                <li><a href="#">Link 4</a></li>
                <li><a href="#">Link 5</a></li>
            </ul>
        </div>
        
        <div class="content">
            <h2>Konten Utama</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
        </div>
    </div>
    
    <div class="footer">
        <p>&copy; 2023 Layout Flexbox. Hak Cipta Dilindungi.</p>
    </div>
</body>
</html>
```

### Contoh Layout 3 Kolom

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout 3 Kolom dengan Flexbox</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .container {
            display: flex;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .sidebar-left {
            flex: 1;
            background-color: #f0f0f0;
            padding: 20px;
        }
        
        .content {
            flex: 3;
            padding: 20px;
        }
        
        .sidebar-right {
            flex: 1;
            background-color: #e0e0e0;
            padding: 20px;
        }
        
        .header {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        .footer {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar-left, .content, .sidebar-right {
                flex: auto;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>Layout 3 Kolom dengan Flexbox</h1>
    </div>
    
    <div class="container">
        <div class="sidebar-left">
            <h2>Sidebar Kiri</h2>
            <ul>
                <li><a href="#">Link 1</a></li>
                <li><a href="#">Link 2</a></li>
                <li><a href="#">Link 3</a></li>
            </ul>
        </div>
        
        <div class="content">
            <h2>Konten Utama</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
        </div>
        
        <div class="sidebar-right">
            <h2>Sidebar Kanan</h2>
            <div class="widget">
                <h3>Widget 1</h3>
                <p>Informasi widget 1.</p>
            </div>
            <div class="widget">
                <h3>Widget 2</h3>
                <p>Informasi widget 2.</p>
            </div>
        </div>
    </div>
    
    <div class="footer">
        <p>&copy; 2023 Layout Flexbox. Hak Cipta Dilindungi.</p>
    </div>
</body>
</html>
```

## 7. Properti Flex Items

Meskipun fokus hari ini adalah pada main axis dan cross axis, penting juga untuk mengenal beberapa properti dasar untuk flex items:

### order
Mengontrol urutan flex items.

```css
.item {
    order: 0; /* default */
}
```

Nilai lebih tinggi berarti item akan muncul lebih belakang dalam urutan.

### flex-grow
Menentukan kemampuan item untuk tumbuh jika ada ruang ekstra.

```css
.item {
    flex-grow: 0; /* default */
}
```

### flex-shrink
Menentukan kemampuan item untuk menyusut jika tidak ada cukup ruang.

```css
.item {
    flex-shrink: 1; /* default */
}
```

### flex-basis
Menentukan ukuran default item sebelum distribusi ruang.

```css
.item {
    flex-basis: auto; /* default */
}
```

### flex
Shorthand untuk `flex-grow`, `flex-shrink`, dan `flex-basis`.

```css
.item {
    flex: 0 1 auto; /* default */
}
```

### align-self
Mengganti alignment yang ditentukan oleh `align-items` untuk item tertentu.

```css
.item {
    align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

## 8. Latihan: Membuat Layout Kolom Responsif

### Langkah-langkah:
1. Buat file HTML baru dengan nama `flexbox-columns.html`
2. Salin kode berikut
3. Buka file di browser
4. Ubah ukuran browser untuk melihat responsivitasnya

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout Kolom Responsif dengan Flexbox</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f5f5f5;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .row {
            display: flex;
            flex-wrap: wrap;
            margin: -10px; /* Kompensasi untuk padding pada kolom */
        }
        
        .column {
            flex: 1;
            padding: 10px;
            min-width: 300px; /* Lebar minimum kolom */
        }
        
        .card {
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            padding: 20px;
            height: 100%;
            box-sizing: border-box;
        }
        
        .card h2 {
            margin-top: 0;
            color: #333;
        }
        
        .card p {
            color: #666;
        }
        
        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 5px;
            margin-bottom: 15px;
        }
        
        @media (max-width: 768px) {
            .column {
                flex: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Layout Kolom Responsif dengan Flexbox</h1>
        
        <div class="row">
            <div class="column">
                <div class="card">
                    <img src="https://via.placeholder.com/400x200" alt="Gambar 1" class="card-image">
                    <h2>Kolom 1</h2>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
                </div>
            </div>
            
            <div class="column">
                <div class="card">
                    <img src="https://via.placeholder.com/400x200" alt="Gambar 2" class="card-image">
                    <h2>Kolom 2</h2>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
                </div>
            </div>
            
            <div class="column">
                <div class="card">
                    <img src="https://via.placeholder.com/400x200" alt="Gambar 3" class="card-image">
                    <h2>Kolom 3</h2>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel ultricies lacinia, nisl nisl aliquam nisl, eget aliquam nisl nisl sit amet nisl.</p>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

## 9. Latihan Mandiri

### Latihan 1: Membuat Layout 2 Kolom
Buat layout 2 kolom dengan sidebar di sebelah kiri dan konten utama di sebelah kanan. Pastikan layout responsif sehingga pada layar kecil, sidebar berada di atas konten.

### Latihan 2: Membuat Layout 3 Kolom
Buat layout 3 kolom dengan sidebar di kedua sisi dan konten utama di tengah. Pastikan layout responsif sehingga pada layar kecil, ketiga kolom tersusun secara vertikal.

### Latihan 3: Membuat Card Layout
Buat layout card dengan 3-4 card per baris. Pastikan layout responsif sehingga jumlah card per baris berkurang pada layar yang lebih kecil.

## Kesimpulan
- Flexbox adalah model layout satu dimensi yang memudahkan pembuatan layout yang responsif dan fleksibel
- Main axis dan cross axis adalah konsep penting dalam Flexbox yang menentukan bagaimana elemen disusun
- Properti seperti `flex-direction`, `flex-wrap`, `justify-content`, dan `align-items` mengontrol perilaku flex container
- Flexbox sangat berguna untuk membuat layout kolom, navigasi, card, dan banyak komponen UI lainnya
- Dengan memahami main axis dan cross axis, kita dapat membuat layout yang kompleks dengan lebih mudah

## Referensi Tambahan
- [MDN Web Docs - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - Game untuk belajar Flexbox
- [W3Schools - CSS Flexbox](https://www.w3schools.com/css/css3_flexbox.asp)