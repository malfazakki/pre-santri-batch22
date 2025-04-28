# Hari 5: CSS Intro: Selektor dan Properti Dasar

## Tujuan Pembelajaran
- Memahami apa itu CSS dan perannya dalam pengembangan web
- Mengenal cara menghubungkan CSS dengan HTML
- Mempelajari berbagai jenis selektor CSS
- Mengenal properti-properti dasar CSS
- Mewarnai halaman web dengan CSS eksternal

## 1. Pengenalan CSS

### Apa itu CSS?
CSS (Cascading Style Sheets) adalah bahasa yang digunakan untuk mendeskripsikan tampilan dan format dokumen HTML. CSS memisahkan konten (HTML) dari presentasi (tampilan), sehingga memudahkan pengembangan dan pemeliharaan website.

### Mengapa CSS Penting?
- **Pemisahan Konten dan Tampilan**: Memungkinkan perubahan tampilan tanpa mengubah struktur HTML
- **Konsistensi**: Memastikan tampilan yang konsisten di seluruh halaman website
- **Efisiensi**: Satu file CSS dapat digunakan untuk mengatur tampilan seluruh website
- **Responsif**: Memungkinkan website tampil baik di berbagai perangkat dan ukuran layar
- **Aksesibilitas**: Meningkatkan aksesibilitas dengan pemisahan konten dan tampilan

### Sejarah Singkat CSS
- CSS1 diperkenalkan tahun 1996
- CSS2 dirilis tahun 1998
- CSS3 mulai dikembangkan tahun 1999 dan terus berkembang hingga sekarang
- CSS modern menggunakan pendekatan modular dengan berbagai modul yang dikembangkan secara terpisah

## 2. Cara Menghubungkan CSS dengan HTML

Ada tiga cara untuk menambahkan CSS ke dokumen HTML:

### 1. Inline CSS
Menggunakan atribut `style` pada elemen HTML.

```html
<h1 style="color: blue; font-size: 24px;">Judul dengan Inline CSS</h1>
<p style="color: red; margin-left: 20px;">Paragraf dengan Inline CSS</p>
```

**Kelebihan**:
- Cepat untuk perubahan kecil
- Prioritas tertinggi dalam cascading

**Kekurangan**:
- Sulit untuk dikelola pada website besar
- Mencampur konten dan tampilan
- Tidak dapat digunakan kembali

### 2. Internal CSS
Menggunakan tag `<style>` di dalam bagian `<head>` dokumen HTML.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Contoh Internal CSS</title>
    <style>
        h1 {
            color: blue;
            font-size: 24px;
        }
        p {
            color: red;
            margin-left: 20px;
        }
    </style>
</head>
<body>
    <h1>Judul dengan Internal CSS</h1>
    <p>Paragraf dengan Internal CSS</p>
</body>
</html>
```

**Kelebihan**:
- Tidak perlu file tambahan
- Aturan CSS hanya berlaku untuk halaman tersebut

**Kekurangan**:
- Meningkatkan ukuran halaman HTML
- Tidak dapat digunakan kembali di halaman lain
- Sulit dikelola pada website besar

### 3. External CSS (Direkomendasikan)
Membuat file CSS terpisah dan menghubungkannya dengan tag `<link>` di bagian `<head>` dokumen HTML.

File HTML (index.html):
```html
<!DOCTYPE html>
<html>
<head>
    <title>Contoh External CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Judul dengan External CSS</h1>
    <p>Paragraf dengan External CSS</p>
</body>
</html>
```

File CSS (styles.css):
```css
h1 {
    color: blue;
    font-size: 24px;
}
p {
    color: red;
    margin-left: 20px;
}
```

**Kelebihan**:
- Pemisahan konten dan tampilan
- Satu file CSS dapat digunakan untuk banyak halaman HTML
- Caching browser meningkatkan kecepatan loading
- Lebih mudah dikelola dan dipelihara

**Kekurangan**:
- Memerlukan permintaan HTTP tambahan (meskipun dapat di-cache)

## 3. Selektor CSS

Selektor CSS digunakan untuk "memilih" elemen HTML yang ingin diatur tampilannya.

### Selektor Dasar

#### 1. Selektor Elemen
Memilih semua elemen dengan tag tertentu.

```css
h1 {
    color: blue;
}
p {
    color: red;
}
```

#### 2. Selektor ID
Memilih elemen dengan ID tertentu. ID harus unik dalam satu halaman.

```css
#header {
    background-color: black;
    color: white;
}
```

HTML:
```html
<div id="header">Header Website</div>
```

#### 3. Selektor Class
Memilih semua elemen dengan class tertentu. Satu elemen dapat memiliki beberapa class.

```css
.highlight {
    background-color: yellow;
}
.text-center {
    text-align: center;
}
```

HTML:
```html
<p class="highlight">Teks yang disorot</p>
<h2 class="text-center">Judul Tengah</h2>
<p class="highlight text-center">Teks yang disorot dan ditengahkan</p>
```

#### 4. Selektor Universal
Memilih semua elemen dalam dokumen.

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

### Selektor Kombinasi

#### 1. Selektor Descendant (Keturunan)
Memilih elemen yang merupakan keturunan dari elemen lain.

```css
article p {
    font-size: 16px;
}
```

Memilih semua elemen `<p>` yang berada di dalam elemen `<article>`.

#### 2. Selektor Child (Anak Langsung)
Memilih elemen yang merupakan anak langsung dari elemen lain.

```css
ul > li {
    list-style-type: square;
}
```

Memilih semua elemen `<li>` yang merupakan anak langsung dari elemen `<ul>`.

#### 3. Selektor Adjacent Sibling (Saudara Sebelah)
Memilih elemen yang berada tepat setelah elemen lain.

```css
h2 + p {
    font-weight: bold;
}
```

Memilih elemen `<p>` yang berada tepat setelah elemen `<h2>`.

#### 4. Selektor General Sibling (Saudara Umum)
Memilih semua elemen yang merupakan saudara dari elemen lain.

```css
h2 ~ p {
    color: gray;
}
```

Memilih semua elemen `<p>` yang merupakan saudara dari elemen `<h2>`.

### Selektor Atribut
Memilih elemen berdasarkan atribut atau nilai atribut.

```css
/* Elemen dengan atribut tertentu */
[type] {
    border: 1px solid gray;
}

/* Elemen dengan nilai atribut tertentu */
[type="text"] {
    background-color: white;
}

/* Elemen dengan nilai atribut yang mengandung kata tertentu */
[class*="btn"] {
    cursor: pointer;
}
```

### Pseudo-class
Memilih elemen dalam keadaan tertentu.

```css
/* Link yang belum dikunjungi */
a:link {
    color: blue;
}

/* Link yang sudah dikunjungi */
a:visited {
    color: purple;
}

/* Link saat mouse di atasnya */
a:hover {
    color: red;
    text-decoration: underline;
}

/* Link saat diklik */
a:active {
    color: orange;
}

/* Elemen input saat fokus */
input:focus {
    border-color: blue;
    outline: none;
}

/* Elemen pertama dari jenisnya */
p:first-of-type {
    font-weight: bold;
}

/* Elemen terakhir dari jenisnya */
p:last-of-type {
    margin-bottom: 0;
}

/* Elemen ganjil */
li:nth-child(odd) {
    background-color: #f2f2f2;
}

/* Elemen genap */
li:nth-child(even) {
    background-color: #e6e6e6;
}
```

### Pseudo-element
Memilih bagian tertentu dari elemen.

```css
/* Huruf pertama dari paragraf */
p::first-letter {
    font-size: 2em;
    font-weight: bold;
}

/* Baris pertama dari paragraf */
p::first-line {
    font-style: italic;
}

/* Konten sebelum elemen */
h2::before {
    content: "➤ ";
    color: blue;
}

/* Konten setelah elemen */
h2::after {
    content: " ✓";
    color: green;
}

/* Teks yang disorot oleh pengguna */
::selection {
    background-color: yellow;
    color: black;
}
```

## 4. Properti Dasar CSS

### Warna dan Latar Belakang

#### Warna Teks
```css
p {
    color: red;                 /* Nama warna */
    color: #ff0000;             /* Heksadesimal */
    color: rgb(255, 0, 0);      /* RGB */
    color: rgba(255, 0, 0, 0.5); /* RGBA dengan transparansi */
    color: hsl(0, 100%, 50%);   /* HSL */
    color: hsla(0, 100%, 50%, 0.5); /* HSLA dengan transparansi */
}
```

#### Latar Belakang
```css
div {
    background-color: lightblue;
    background-image: url('gambar.jpg');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    
    /* Shorthand */
    background: lightblue url('gambar.jpg') no-repeat center/cover;
}
```

### Teks dan Font

#### Font
```css
p {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 16px;
    font-weight: bold;
    font-style: italic;
    
    /* Shorthand */
    font: italic bold 16px/1.5 Arial, sans-serif;
}
```

#### Teks
```css
p {
    text-align: center;
    text-decoration: underline;
    text-transform: uppercase;
    text-indent: 20px;
    line-height: 1.5;
    letter-spacing: 1px;
    word-spacing: 2px;
}
```

### Dimensi dan Spacing

#### Dimensi
```css
div {
    width: 300px;
    height: 200px;
    min-width: 100px;
    max-width: 500px;
    min-height: 100px;
    max-height: 300px;
}
```

#### Margin dan Padding
```css
div {
    /* Empat nilai: atas, kanan, bawah, kiri */
    margin: 10px 20px 15px 25px;
    
    /* Dua nilai: atas-bawah, kiri-kanan */
    padding: 10px 20px;
    
    /* Satu nilai: semua sisi */
    margin: 10px;
    
    /* Nilai individual */
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 15px;
    margin-left: 25px;
}
```

### Border dan Outline

```css
div {
    border-width: 2px;
    border-style: solid;
    border-color: black;
    
    /* Shorthand */
    border: 2px solid black;
    
    /* Individual sides */
    border-top: 2px dotted red;
    border-right: 3px dashed green;
    border-bottom: 4px double blue;
    border-left: 1px solid orange;
    
    /* Border radius */
    border-radius: 10px;
    border-radius: 10px 20px 30px 40px; /* top-left, top-right, bottom-right, bottom-left */
    
    /* Outline (tidak mempengaruhi layout) */
    outline: 2px solid red;
}
```

## 5. Praktik: Mewarnai Halaman dengan CSS Eksternal

### Langkah-langkah:
1. Buat file HTML baru (misalnya `index.html`)
2. Buat file CSS baru (misalnya `styles.css`) di folder yang sama
3. Hubungkan file CSS ke HTML menggunakan tag `<link>`
4. Tambahkan berbagai selektor dan properti CSS
5. Simpan kedua file dan buka HTML di browser

### Contoh File HTML (index.html):

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Belajar CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header id="main-header">
        <h1>Belajar CSS</h1>
        <nav>
            <ul>
                <li><a href="#intro">Pengenalan</a></li>
                <li><a href="#selectors">Selektor</a></li>
                <li><a href="#properties">Properti</a></li>
                <li><a href="#practice">Praktik</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="intro" class="content-section">
            <h2>Pengenalan CSS</h2>
            <p class="highlight">CSS (Cascading Style Sheets) adalah bahasa yang digunakan untuk mendeskripsikan tampilan dokumen HTML.</p>
            <p>CSS memisahkan konten dari presentasi, sehingga memudahkan pengembangan website.</p>
        </section>
        
        <section id="selectors" class="content-section">
            <h2>Selektor CSS</h2>
            <p>Selektor digunakan untuk memilih elemen HTML yang ingin diatur tampilannya.</p>
            <ul class="feature-list">
                <li>Selektor Elemen</li>
                <li>Selektor ID</li>
                <li>Selektor Class</li>
                <li>Selektor Universal</li>
            </ul>
        </section>
        
        <section id="properties" class="content-section">
            <h2>Properti CSS</h2>
            <p>Properti menentukan aspek tampilan yang ingin diubah.</p>
            <div class="property-examples">
                <div class="property-card">Warna</div>
                <div class="property-card">Font</div>
                <div class="property-card">Margin</div>
                <div class="property-card">Padding</div>
            </div>
        </section>
        
        <section id="practice" class="content-section">
            <h2>Praktik CSS</h2>
            <p>Praktik adalah cara terbaik untuk belajar CSS.</p>
            <a href="#" class="btn">Mulai Praktik</a>
        </section>
    </main>
    
    <aside class="sidebar">
        <h3>Tips CSS</h3>
        <ul>
            <li>Gunakan external CSS untuk website besar</li>
            <li>Buat nama class yang deskriptif</li>
            <li>Hindari penggunaan !important</li>
            <li>Gunakan CSS reset untuk konsistensi</li>
        </ul>
    </aside>
    
    <footer>
        <p>&copy; 2023 Belajar CSS. Hak Cipta Dilindungi.</p>
    </footer>
</body>
</html>
```

### Contoh File CSS (styles.css):

```css
/* Reset CSS sederhana */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Styling dasar */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f4;
    padding: 20px;
}

/* Header */
#main-header {
    background-color: #35424a;
    color: white;
    padding: 20px;
    margin-bottom: 20px;
    border-bottom: 3px solid #e8491d;
}

#main-header h1 {
    margin-bottom: 10px;
}

/* Navigasi */
nav ul {
    list-style: none;
    display: flex;
}

nav ul li {
    margin-right: 20px;
}

nav a {
    color: white;
    text-decoration: none;
}

nav a:hover {
    color: #e8491d;
}

/* Konten Utama */
main {
    width: 70%;
    float: left;
}

.content-section {
    background-color: white;
    margin-bottom: 20px;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.content-section h2 {
    color: #35424a;
    border-bottom: 2px solid #e8491d;
    padding-bottom: 10px;
    margin-bottom: 15px;
}

.highlight {
    background-color: #ffffcc;
    padding: 10px;
    border-left: 3px solid #e8491d;
}

/* List */
.feature-list {
    margin-left: 20px;
}

.feature-list li {
    padding: 5px 0;
}

/* Property Cards */
.property-examples {
    display: flex;
    justify-content: space-between;
    margin-top: 15px;
}

.property-card {
    background-color: #35424a;
    color: white;
    padding: 15px;
    width: 22%;
    text-align: center;
    border-radius: 5px;
}

/* Button */
.btn {
    display: inline-block;
    background-color: #e8491d;
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    margin-top: 10px;
}

.btn:hover {
    background-color: #333;
}

/* Sidebar */
.sidebar {
    width: 28%;
    float: right;
    background-color: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.sidebar h3 {
    color: #35424a;
    border-bottom: 2px solid #e8491d;
    padding-bottom: 10px;
    margin-bottom: 15px;
}

.sidebar ul {
    margin-left: 20px;
}

.sidebar li {
    padding: 5px 0;
}

/* Footer */
footer {
    clear: both;
    background-color: #35424a;
    color: white;
    text-align: center;
    padding: 20px;
    margin-top: 20px;
    border-top: 3px solid #e8491d;
}

/* Pseudo-classes */
a:link {
    color: #e8491d;
}

a:visited {
    color: #a33613;
}

a:hover {
    text-decoration: underline;
}

/* Pseudo-elements */
p::first-letter {
    font-size: 1.2em;
    font-weight: bold;
}

h2::before {
    content: "§ ";
    color: #e8491d;
}
```

## Latihan Mandiri
1. Buat file HTML dengan struktur yang mencakup header, main content, sidebar, dan footer
2. Buat file CSS eksternal dan hubungkan dengan HTML
3. Gunakan minimal 5 jenis selektor berbeda (elemen, id, class, descendant, pseudo-class)
4. Terapkan properti warna, font, margin, padding, dan border
5. Buat tombol dengan efek hover
6. Gunakan pseudo-element untuk menambahkan konten sebelum atau sesudah elemen
7. Pastikan halaman Anda memiliki tampilan yang menarik dan terorganisir

## Kesimpulan
- CSS digunakan untuk mengatur tampilan halaman web
- Ada tiga cara menghubungkan CSS dengan HTML: inline, internal, dan external
- Selektor CSS digunakan untuk memilih elemen yang akan diatur tampilannya
- Properti CSS menentukan aspek tampilan yang akan diubah
- CSS eksternal adalah cara terbaik untuk mengelola style pada website besar

## Referensi Tambahan
- [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [W3Schools - CSS Tutorial](https://www.w3schools.com/css/)
- [CSS Reference](https://cssreference.io/)