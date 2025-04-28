# Hari 7: Catch-up Day / Review

## Tujuan Pembelajaran
- Mengulas kembali materi HTML dan CSS yang telah dipelajari selama seminggu
- Mengidentifikasi area yang perlu diperkuat
- Menerapkan pengetahuan dalam latihan tambahan
- Mempersiapkan diri untuk materi minggu berikutnya

## 1. Ringkasan Materi Minggu 1

Selama minggu pertama, kita telah mempelajari dasar-dasar HTML dan CSS. Mari kita ringkas apa yang telah kita pelajari:

### Hari 1: Apa itu Web? Struktur HTML
- Pengenalan tentang web dan internet
- Struktur dasar dokumen HTML
- Tag HTML dan atribut
- Membuat dokumen HTML sederhana

### Hari 2: Tag Umum HTML
- Heading (h1-h6)
- Paragraf (p)
- Link (a)
- Gambar (img)
- Membuat halaman biodata sederhana

### Hari 3: List, Table, Form
- Unordered list (ul), ordered list (ol), dan description list (dl)
- Struktur tabel (table, tr, th, td)
- Form dan berbagai elemen input
- Membuat form pendaftaran

### Hari 4: Semantic HTML
- Pentingnya semantic HTML
- Elemen semantic (header, nav, main, section, article, aside, footer)
- Merapikan struktur halaman dengan tag semantic

### Hari 5: CSS Intro: Selektor dan Properti Dasar
- Cara menghubungkan CSS dengan HTML
- Berbagai jenis selektor CSS
- Properti dasar CSS (warna, background, dll.)
- Mewarnai halaman dengan CSS eksternal

### Hari 6: Styling Teks dan Box Model
- Properti styling teks (font, ukuran, warna, dll.)
- CSS Box Model (content, padding, border, margin)
- Mengatur layout dengan box model
- Mempercantik form pendaftaran dengan CSS

## 2. Konsep Kunci yang Perlu Dikuasai

### HTML
1. **Struktur Dasar HTML**
   ```html
   <!DOCTYPE html>
   <html lang="id">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Judul Halaman</title>
   </head>
   <body>
       <!-- Konten halaman -->
   </body>
   </html>
   ```

2. **Tag Penting HTML**
   - Heading: `<h1>` hingga `<h6>`
   - Paragraf: `<p>`
   - Link: `<a href="url">teks</a>`
   - Gambar: `<img src="gambar.jpg" alt="deskripsi">`
   - List: `<ul>`, `<ol>`, `<li>`
   - Tabel: `<table>`, `<tr>`, `<th>`, `<td>`
   - Form: `<form>`, `<input>`, `<select>`, `<textarea>`, `<button>`

3. **Tag Semantic HTML**
   - `<header>`: Bagian header halaman atau section
   - `<nav>`: Bagian navigasi
   - `<main>`: Konten utama halaman
   - `<section>`: Bagian tematik dalam dokumen
   - `<article>`: Konten yang berdiri sendiri
   - `<aside>`: Konten yang berhubungan secara tidak langsung
   - `<footer>`: Bagian footer halaman atau section

### CSS
1. **Cara Menghubungkan CSS dengan HTML**
   - Inline CSS: `<h1 style="color: blue;">Judul</h1>`
   - Internal CSS: `<style>h1 { color: blue; }</style>`
   - External CSS: `<link rel="stylesheet" href="styles.css">`

2. **Selektor CSS**
   - Selektor elemen: `h1 { ... }`
   - Selektor ID: `#header { ... }`
   - Selektor class: `.highlight { ... }`
   - Selektor kombinasi: `article p { ... }`
   - Pseudo-class: `a:hover { ... }`

3. **Properti CSS Penting**
   - Warna dan background: `color`, `background-color`
   - Font dan teks: `font-family`, `font-size`, `text-align`
   - Box model: `margin`, `padding`, `border`
   - Layout: `width`, `height`, `display`

4. **CSS Box Model**
   ```
   +------------------------+
   |        Margin          |
   |  +------------------+  |
   |  |     Border       |  |
   |  |  +------------+  |  |
   |  |  |  Padding   |  |  |
   |  |  |  +------+  |  |  |
   |  |  |  |Content|  |  |  |
   |  |  |  +------+  |  |  |
   |  |  +------------+  |  |
   |  +------------------+  |
   +------------------------+
   ```

## 3. Quiz Pemahaman

Mari uji pemahaman Anda dengan beberapa pertanyaan:

### HTML
1. Apa fungsi dari tag `<!DOCTYPE html>`?
2. Apa perbedaan antara tag `<div>` dan `<span>`?
3. Mengapa kita perlu menggunakan atribut `alt` pada tag `<img>`?
4. Apa perbedaan antara `<ul>` dan `<ol>`?
5. Sebutkan minimal 3 elemen semantic HTML dan jelaskan fungsinya.
6. Apa perbedaan antara `<input type="text">` dan `<textarea>`?
7. Bagaimana cara membuat tabel dengan header, body, dan footer?

### CSS
1. Apa perbedaan antara ID dan class dalam CSS?
2. Jelaskan perbedaan antara `margin` dan `padding`.
3. Apa yang dimaksud dengan CSS Box Model?
4. Bagaimana cara membuat teks menjadi tebal tanpa menggunakan tag HTML?
5. Apa fungsi dari properti `box-sizing: border-box`?
6. Bagaimana cara membuat elemen berada di tengah halaman secara horizontal?
7. Apa perbedaan antara `display: none` dan `visibility: hidden`?

## 4. Latihan Tambahan

### Latihan 1: Halaman Profil Lengkap
Buat halaman profil pribadi yang lengkap dengan:
- Header dengan nama dan foto profil
- Navigasi dengan minimal 4 link
- Bagian "Tentang Saya" dengan paragraf deskripsi
- Bagian "Pendidikan" dengan tabel
- Bagian "Keahlian" dengan list
- Bagian "Portofolio" dengan gambar dan deskripsi
- Bagian "Kontak" dengan form
- Footer dengan informasi hak cipta

Gunakan tag semantic HTML dan styling CSS yang menarik.

### Latihan 2: Perbaiki Kode Berikut

HTML yang perlu diperbaiki:
```html
<div class="header">
    <h1>Website Saya</h1>
    <div class="nav">
        <ul>
            <li><a href="#">Home</a>
            <li><a href="#">About</a>
            <li><a href="#">Contact</a>
        </ul>
    </div>
</div>
<div class="main">
    <div class="article">
        <h1>Artikel Utama</h1>
        <p>Ini adalah paragraf pertama.
        <p>Ini adalah paragraf kedua.
    </div>
    <div class="sidebar">
        <h2>Artikel Terkait</h2>
        <ul>
            <li><a href="#">Artikel 1</a></li>
            <li><a href="#">Artikel 2</a></li>
        </ul>
    </div>
</div>
<div class="footer">
    <p>Copyright 2023
</div>
```

CSS yang perlu diperbaiki:
```css
body {
    font-family: arial;
    color: black;
    background-color: white
}

.header {
    background-color: #333;
    color: white;
    padding: 20px
}

.nav ul {
    list-style-type: none;
}

.nav li {
    display: inline;
    margin-right: 10px
}

.nav a {
    color: white;
    text-decoration: none;
}

.nav a:hover {
    text-decoration: underline
}

.main {
    width: 800px;
    margin: 0 auto;
}

.article {
    width: 70%;
    float: left;
}

.sidebar {
    width: 30%;
    float: right;
}

.footer {
    clear: both;
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center
}
```

### Latihan 3: Buat Card Produk
Buat card produk dengan HTML dan CSS yang memiliki:
- Gambar produk
- Nama produk
- Harga
- Deskripsi singkat
- Tombol "Beli Sekarang"

Tambahkan efek hover pada card dan tombol.

## 5. Proyek Mini: Landing Page Sederhana

Buat landing page sederhana untuk produk atau layanan fiktif dengan:

### Struktur HTML:
1. Header dengan logo dan navigasi
2. Hero section dengan judul, deskripsi, dan call-to-action button
3. Fitur section dengan 3-4 fitur (ikon, judul, deskripsi)
4. Testimonial section dengan 2-3 testimonial
5. Call-to-action section
6. Footer dengan link dan informasi kontak

### Styling CSS:
1. Gunakan warna yang konsisten (3-4 warna)
2. Gunakan font yang mudah dibaca
3. Terapkan box model untuk layout
4. Buat tombol dengan efek hover
5. Pastikan halaman responsif (minimal untuk desktop dan tablet)

## 6. Checklist Persiapan Minggu Berikutnya

- [ ] Memahami struktur dasar HTML
- [ ] Menguasai tag-tag HTML umum
- [ ] Memahami penggunaan tag semantic HTML
- [ ] Dapat membuat form dengan berbagai elemen input
- [ ] Memahami cara menghubungkan CSS dengan HTML
- [ ] Menguasai berbagai jenis selektor CSS
- [ ] Memahami CSS Box Model
- [ ] Dapat menerapkan styling teks dan box dengan CSS
- [ ] Menyelesaikan semua latihan dan proyek mini

## 7. Sumber Belajar Tambahan

### HTML
- [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools - HTML Tutorial](https://www.w3schools.com/html/)
- [HTML.com](https://html.com/)
- [HTML Cheat Sheet](https://htmlcheatsheet.com/)

### CSS
- [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3Schools - CSS Tutorial](https://www.w3schools.com/css/)
- [CSS-Tricks](https://css-tricks.com/)
- [CSS Reference](https://cssreference.io/)

### Tools
- [HTML Validator](https://validator.w3.org/)
- [CSS Validator](https://jigsaw.w3.org/css-validator/)
- [CodePen](https://codepen.io/) - Untuk bereksperimen dengan HTML dan CSS
- [Visual Studio Code](https://code.visualstudio.com/) - Editor kode yang populer

## 8. Tips Belajar Efektif

1. **Praktik Secara Konsisten**: Luangkan waktu setiap hari untuk menulis kode HTML dan CSS.
2. **Analisis Website yang Ada**: Pelajari kode sumber website yang Anda sukai untuk memahami bagaimana mereka dibuat.
3. **Buat Proyek Kecil**: Mulai dengan proyek kecil dan tingkatkan kompleksitasnya seiring waktu.
4. **Gunakan Developer Tools**: Pelajari cara menggunakan developer tools di browser untuk menginspeksi dan memodifikasi elemen HTML dan CSS.
5. **Bergabung dengan Komunitas**: Bergabung dengan forum atau grup diskusi untuk bertanya dan berbagi pengetahuan.
6. **Dokumentasikan Pembelajaran**: Buat catatan atau blog tentang apa yang Anda pelajari untuk memperkuat pemahaman.
7. **Jangan Takut Gagal**: Kesalahan adalah bagian dari proses belajar. Jangan takut untuk bereksperimen dan belajar dari kesalahan.

## 9. Jawaban Quiz

### HTML
1. `<!DOCTYPE html>` memberitahu browser bahwa dokumen adalah HTML5.
2. `<div>` adalah elemen block yang biasanya digunakan untuk mengelompokkan elemen, sedangkan `<span>` adalah elemen inline yang biasanya digunakan untuk styling teks.
3. Atribut `alt` pada tag `<img>` penting untuk aksesibilitas (pembaca layar), SEO, dan sebagai fallback jika gambar tidak dapat dimuat.
4. `<ul>` (unordered list) menampilkan daftar dengan bullet point, sedangkan `<ol>` (ordered list) menampilkan daftar dengan nomor.
5. Tiga elemen semantic HTML:
   - `<header>`: Bagian header halaman atau section
   - `<nav>`: Bagian navigasi
   - `<footer>`: Bagian footer halaman atau section
6. `<input type="text">` adalah field input satu baris, sedangkan `<textarea>` adalah field input multi-baris.
7. Untuk membuat tabel dengan header, body, dan footer:
   ```html
   <table>
       <thead>
           <tr>
               <th>Header 1</th>
               <th>Header 2</th>
           </tr>
       </thead>
       <tbody>
           <tr>
               <td>Data 1</td>
               <td>Data 2</td>
           </tr>
       </tbody>
       <tfoot>
           <tr>
               <td>Footer 1</td>
               <td>Footer 2</td>
           </tr>
       </tfoot>
   </table>
   ```

### CSS
1. ID (#) harus unik dalam satu halaman dan hanya dapat digunakan sekali, sedangkan class (.) dapat digunakan berkali-kali pada banyak elemen.
2. `margin` adalah ruang di luar border elemen, sedangkan `padding` adalah ruang antara border dan konten elemen.
3. CSS Box Model menjelaskan bagaimana elemen HTML diperlakukan sebagai kotak dengan content, padding, border, dan margin.
4. Untuk membuat teks tebal dengan CSS: `font-weight: bold;` atau `font-weight: 700;`
5. `box-sizing: border-box` membuat width dan height elemen termasuk padding dan border, bukan hanya content.
6. Untuk membuat elemen block berada di tengah secara horizontal: `margin: 0 auto;` (dengan width tertentu).
7. `display: none` menghilangkan elemen dari layout (tidak mengambil ruang), sedangkan `visibility: hidden` menyembunyikan elemen tetapi tetap mengambil ruang dalam layout.

## 10. Solusi Latihan 2

HTML yang sudah diperbaiki:
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website Saya</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Website Saya</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <h1>Artikel Utama</h1>
            <p>Ini adalah paragraf pertama.</p>
            <p>Ini adalah paragraf kedua.</p>
        </article>
        
        <aside>
            <h2>Artikel Terkait</h2>
            <ul>
                <li><a href="#">Artikel 1</a></li>
                <li><a href="#">Artikel 2</a></li>
            </ul>
        </aside>
    </main>
    
    <footer>
        <p>Copyright &copy; 2023</p>
    </footer>
</body>
</html>
```

CSS yang sudah diperbaiki:
```css
body {
    font-family: Arial, sans-serif;
    color: black;
    background-color: white;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 20px;
}

nav ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
}

nav li {
    display: inline;
    margin-right: 10px;
}

nav a {
    color: white;
    text-decoration: none;
}

nav a:hover {
    text-decoration: underline;
}

main {
    width: 800px;
    margin: 0 auto;
    padding: 20px;
    overflow: hidden;
}

article {
    width: 70%;
    float: left;
}

aside {
    width: 30%;
    float: right;
}

footer {
    clear: both;
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
}
```

## Kesimpulan

Minggu pertama telah memberikan dasar yang kuat dalam HTML dan CSS. Anda telah mempelajari struktur dasar HTML, tag-tag umum, semantic HTML, serta dasar-dasar CSS termasuk selektor dan box model. Dengan menguasai konsep-konsep ini, Anda telah siap untuk melanjutkan ke materi yang lebih kompleks.

Gunakan hari ini untuk mengulas kembali materi, mengidentifikasi area yang perlu diperkuat, dan menyelesaikan latihan tambahan. Jangan ragu untuk kembali ke materi sebelumnya jika ada konsep yang belum sepenuhnya dipahami.

Selamat belajar dan terus berlatih!