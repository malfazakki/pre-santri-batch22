# Hari 6: Styling Teks dan Box (margin, padding, border)

## Tujuan Pembelajaran
- Memahami dan menerapkan styling teks dengan CSS
- Memahami konsep CSS Box Model
- Menggunakan margin, padding, dan border untuk mengatur layout
- Mempercantik form pendaftaran dengan CSS

## 1. Styling Teks dengan CSS

Teks adalah komponen utama dalam sebagian besar halaman web. CSS menyediakan berbagai properti untuk mengontrol tampilan teks.

### Font Properties

#### Font Family
Menentukan jenis font yang digunakan.

```css
p {
    font-family: Arial, Helvetica, sans-serif;
}

h1 {
    font-family: 'Times New Roman', Times, serif;
}
```

Ada lima kategori umum font:
- **Serif**: Font dengan garis kecil di ujung karakter (Times New Roman, Georgia)
- **Sans-serif**: Font tanpa garis kecil (Arial, Helvetica, Verdana)
- **Monospace**: Font dengan lebar karakter yang sama (Courier New, Roboto Mono)
- **Cursive**: Font yang menyerupai tulisan tangan (Comic Sans MS, Brush Script)
- **Fantasy**: Font dekoratif (Impact, Papyrus)

#### Web Safe Fonts
Font yang umumnya tersedia di sebagian besar sistem:
- Arial
- Verdana
- Helvetica
- Tahoma
- Times New Roman
- Georgia
- Courier New
- Trebuchet MS

#### Google Fonts
Cara menggunakan Google Fonts:

```html
<head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
</head>
```

```css
body {
    font-family: 'Roboto', sans-serif;
}
```

#### Font Size
Mengatur ukuran font.

```css
h1 {
    font-size: 32px;
}

p {
    font-size: 16px;
}

small {
    font-size: 0.8em; /* Relatif terhadap ukuran font elemen induk */
}
```

Unit ukuran font:
- **px**: Piksel, ukuran tetap
- **em**: Relatif terhadap ukuran font elemen induk
- **rem**: Relatif terhadap ukuran font elemen root (html)
- **%**: Persentase dari ukuran font elemen induk
- **vw**: Persentase dari lebar viewport
- **pt**: Point, biasanya untuk cetak

#### Font Weight
Mengatur ketebalan font.

```css
p {
    font-weight: normal; /* atau 400 */
}

strong {
    font-weight: bold; /* atau 700 */
}

h1 {
    font-weight: 900; /* Extra bold */
}
```

Nilai font-weight:
- **normal** (400)
- **bold** (700)
- **bolder** (relatif terhadap elemen induk)
- **lighter** (relatif terhadap elemen induk)
- Nilai numerik: 100, 200, 300, ..., 900

#### Font Style
Mengatur gaya font (normal, italic, oblique).

```css
p {
    font-style: normal;
}

em {
    font-style: italic;
}
```

#### Font Variant
Mengatur varian font, seperti small-caps.

```css
p {
    font-variant: small-caps;
}
```

#### Font Shorthand
Menggabungkan beberapa properti font dalam satu deklarasi.

```css
p {
    /* font: font-style font-variant font-weight font-size/line-height font-family */
    font: italic small-caps bold 16px/1.5 Arial, sans-serif;
}
```

### Text Properties

#### Text Color
Mengatur warna teks.

```css
p {
    color: #333333;
}

h1 {
    color: rgb(0, 102, 204);
}

a {
    color: hsl(200, 100%, 50%);
}
```

#### Text Alignment
Mengatur perataan teks.

```css
h1 {
    text-align: center;
}

p {
    text-align: justify;
}

.right-aligned {
    text-align: right;
}
```

Nilai text-align:
- **left**: Rata kiri (default)
- **right**: Rata kanan
- **center**: Rata tengah
- **justify**: Rata kiri dan kanan

#### Text Decoration
Mengatur dekorasi teks seperti garis bawah, garis atas, atau garis tengah.

```css
a {
    text-decoration: none; /* Menghilangkan garis bawah pada link */
}

h2 {
    text-decoration: underline;
}

.strikethrough {
    text-decoration: line-through;
}

.fancy {
    text-decoration: underline wavy red;
}
```

#### Text Transform
Mengubah kapitalisasi teks.

```css
h1 {
    text-transform: uppercase;
}

h2 {
    text-transform: capitalize;
}

.lowercase {
    text-transform: lowercase;
}
```

Nilai text-transform:
- **uppercase**: Semua huruf kapital
- **lowercase**: Semua huruf kecil
- **capitalize**: Huruf pertama setiap kata kapital
- **none**: Tidak ada transformasi

#### Text Indent
Mengatur indentasi baris pertama teks.

```css
p {
    text-indent: 30px;
}
```

#### Letter Spacing
Mengatur jarak antar huruf.

```css
h1 {
    letter-spacing: 2px;
}

.tight {
    letter-spacing: -1px;
}
```

#### Word Spacing
Mengatur jarak antar kata.

```css
p {
    word-spacing: 4px;
}
```

#### Line Height
Mengatur tinggi baris, yang memengaruhi jarak antar baris teks.

```css
p {
    line-height: 1.6;
}

.tight-text {
    line-height: 1.2;
}

.spacious {
    line-height: 2;
}
```

#### Text Shadow
Menambahkan bayangan pada teks.

```css
h1 {
    /* text-shadow: horizontal-offset vertical-offset blur-radius color */
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.glow {
    text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
}

.multiple-shadows {
    text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
}
```

#### White Space
Mengatur bagaimana spasi putih (white space) diperlakukan.

```css
pre {
    white-space: pre; /* Mempertahankan semua spasi dan line break */
}

.nowrap {
    white-space: nowrap; /* Mencegah teks berpindah baris */
}
```

#### Word Wrap dan Overflow
Mengatur perilaku teks yang terlalu panjang.

```css
p {
    word-wrap: break-word; /* Memecah kata yang terlalu panjang */
}

.ellipsis {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis; /* Menampilkan ... untuk teks yang terpotong */
}
```

## 2. CSS Box Model

Setiap elemen HTML diperlakukan sebagai kotak (box) oleh CSS. Box Model menjelaskan bagaimana margin, border, padding, dan konten bekerja bersama untuk membentuk layout halaman.

### Komponen Box Model

Box Model terdiri dari empat komponen (dari dalam ke luar):
1. **Content**: Area di mana konten elemen ditampilkan
2. **Padding**: Area transparan di sekitar konten
3. **Border**: Garis yang mengelilingi padding dan konten
4. **Margin**: Area transparan di luar border

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

### Content Box

Area di mana konten elemen ditampilkan. Ukurannya dapat diatur dengan properti `width` dan `height`.

```css
div {
    width: 300px;
    height: 200px;
    background-color: lightblue;
}
```

### Padding

Ruang antara konten dan border. Padding transparan dan mengadopsi warna background elemen.

```css
div {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 15px;
    padding-left: 25px;
    
    /* Shorthand untuk semua sisi */
    padding: 10px;
    
    /* Shorthand untuk top/bottom dan left/right */
    padding: 10px 20px;
    
    /* Shorthand untuk top, right/left, bottom */
    padding: 10px 20px 15px;
    
    /* Shorthand untuk top, right, bottom, left (searah jarum jam) */
    padding: 10px 20px 15px 25px;
}
```

### Border

Garis yang mengelilingi padding dan konten.

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
    
    /* Border radius (rounded corners) */
    border-radius: 10px;
    border-radius: 50%; /* Membuat elemen menjadi lingkaran (jika width = height) */
    
    /* Individual corners */
    border-top-left-radius: 10px;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 30px;
    border-bottom-left-radius: 40px;
    
    /* Shorthand untuk semua corner */
    border-radius: 10px 20px 30px 40px;
}
```

Gaya border:
- **solid**: Garis solid
- **dotted**: Garis titik-titik
- **dashed**: Garis putus-putus
- **double**: Garis ganda
- **groove**: Efek 3D groove
- **ridge**: Efek 3D ridge
- **inset**: Efek 3D inset
- **outset**: Efek 3D outset
- **none**: Tidak ada border
- **hidden**: Border tersembunyi

### Margin

Ruang di luar border. Margin transparan dan tidak mengadopsi warna background.

```css
div {
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 15px;
    margin-left: 25px;
    
    /* Shorthand untuk semua sisi */
    margin: 10px;
    
    /* Shorthand untuk top/bottom dan left/right */
    margin: 10px 20px;
    
    /* Shorthand untuk top, right/left, bottom */
    margin: 10px 20px 15px;
    
    /* Shorthand untuk top, right, bottom, left (searah jarum jam) */
    margin: 10px 20px 15px 25px;
    
    /* Auto margins untuk centering horizontal */
    margin: 0 auto;
    
    /* Margin negatif */
    margin-top: -10px;
}
```

### Box Sizing

Properti `box-sizing` mengontrol bagaimana lebar dan tinggi elemen dihitung.

```css
div {
    box-sizing: content-box; /* Default: width dan height hanya untuk content */
    box-sizing: border-box; /* width dan height termasuk padding dan border */
}
```

Dengan `box-sizing: border-box`, ukuran total elemen tetap sama meskipun padding atau border berubah, yang membuat layout lebih mudah diprediksi.

```css
* {
    box-sizing: border-box; /* Diterapkan ke semua elemen */
}
```

### Contoh Box Model

```css
div {
    width: 300px;
    height: 200px;
    padding: 20px;
    border: 5px solid black;
    margin: 30px;
    background-color: lightblue;
}
```

Dengan `box-sizing: content-box` (default):
- Total width = 300px (content) + 40px (padding) + 10px (border) + 60px (margin) = 410px
- Total height = 200px (content) + 40px (padding) + 10px (border) + 60px (margin) = 310px

Dengan `box-sizing: border-box`:
- Content width = 300px - 40px (padding) - 10px (border) = 250px
- Content height = 200px - 40px (padding) - 10px (border) = 150px
- Total width = 300px + 60px (margin) = 360px
- Total height = 200px + 60px (margin) = 260px

## 3. Mengatur Layout dengan Box Model

### Centering Elements

#### Horizontal Centering

Untuk elemen block:
```css
div {
    width: 300px; /* Harus memiliki width */
    margin: 0 auto;
}
```

Untuk elemen inline atau inline-block:
```css
.container {
    text-align: center;
}
```

#### Vertical Centering

Dengan line-height (untuk teks satu baris):
```css
.text {
    height: 100px;
    line-height: 100px; /* Sama dengan height */
}
```

Dengan flexbox:
```css
.container {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 300px;
}
```

### Controlling Overflow

Mengatur bagaimana konten yang melebihi ukuran elemen ditampilkan.

```css
div {
    width: 300px;
    height: 200px;
    overflow: visible; /* Default: konten akan keluar dari box */
    overflow: hidden; /* Konten yang melebihi akan disembunyikan */
    overflow: scroll; /* Selalu menampilkan scrollbar */
    overflow: auto; /* Menampilkan scrollbar hanya jika diperlukan */
    
    /* Mengontrol overflow secara terpisah */
    overflow-x: hidden;
    overflow-y: auto;
}
```

### Display Property

Mengontrol bagaimana elemen ditampilkan.

```css
div {
    display: block; /* Elemen block (default untuk div) */
    display: inline; /* Elemen inline (default untuk span) */
    display: inline-block; /* Kombinasi inline dan block */
    display: none; /* Menyembunyikan elemen (tidak mengambil ruang) */
    display: flex; /* Membuat flex container */
    display: grid; /* Membuat grid container */
}
```

### Visibility Property

Mengontrol visibilitas elemen.

```css
div {
    visibility: visible; /* Default: elemen terlihat */
    visibility: hidden; /* Menyembunyikan elemen (tetap mengambil ruang) */
    visibility: collapse; /* Untuk elemen tabel */
}
```

## 4. Praktik: Mempercantik Form Pendaftaran

Sekarang kita akan menerapkan styling teks dan box model untuk mempercantik form pendaftaran yang telah dibuat sebelumnya.

### Langkah-langkah:
1. Ambil file HTML form pendaftaran yang telah dibuat
2. Buat file CSS baru (misalnya `form-style.css`)
3. Hubungkan file CSS ke HTML
4. Terapkan styling untuk mempercantik form

### Contoh HTML Form Pendaftaran:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Pendaftaran</title>
    <link rel="stylesheet" href="form-style.css">
</head>
<body>
    <div class="container">
        <header>
            <h1>Form Pendaftaran Kursus</h1>
            <p>Silakan isi form di bawah ini untuk mendaftar kursus online kami.</p>
        </header>
        
        <form action="#" method="post">
            <fieldset>
                <legend>Data Pribadi</legend>
                
                <div class="form-group">
                    <label for="nama_lengkap">Nama Lengkap:</label>
                    <input type="text" id="nama_lengkap" name="nama_lengkap" required>
                </div>
                
                <div class="form-group">
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email" required>
                </div>
                
                <div class="form-group">
                    <label for="telepon">Nomor Telepon:</label>
                    <input type="tel" id="telepon" name="telepon" pattern="[0-9]{10,13}" placeholder="Contoh: 08123456789">
                </div>
                
                <div class="form-group">
                    <label for="tanggal_lahir">Tanggal Lahir:</label>
                    <input type="date" id="tanggal_lahir" name="tanggal_lahir">
                </div>
                
                <div class="form-group">
                    <label>Jenis Kelamin:</label>
                    <div class="radio-group">
                        <input type="radio" id="pria" name="gender" value="pria">
                        <label for="pria" class="radio-label">Pria</label>
                        
                        <input type="radio" id="wanita" name="gender" value="wanita">
                        <label for="wanita" class="radio-label">Wanita</label>
                    </div>
                </div>
            </fieldset>
            
            <fieldset>
                <legend>Informasi Kursus</legend>
                
                <div class="form-group">
                    <label for="program">Program yang Diminati:</label>
                    <select id="program" name="program" required>
                        <option value="">Pilih Program</option>
                        <option value="web">Web Development</option>
                        <option value="mobile">Mobile App Development</option>
                        <option value="data">Data Science</option>
                        <option value="ui">UI/UX Design</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label>Jadwal yang Diinginkan:</label>
                    <div class="checkbox-group">
                        <input type="checkbox" id="pagi" name="jadwal" value="pagi">
                        <label for="pagi" class="checkbox-label">Pagi (08.00 - 12.00)</label>
                        
                        <input type="checkbox" id="siang" name="jadwal" value="siang">
                        <label for="siang" class="checkbox-label">Siang (13.00 - 17.00)</label>
                        
                        <input type="checkbox" id="malam" name="jadwal" value="malam">
                        <label for="malam" class="checkbox-label">Malam (18.00 - 21.00)</label>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="pengalaman">Pengalaman Programming:</label>
                    <select id="pengalaman" name="pengalaman">
                        <option value="pemula">Pemula (belum pernah)</option>
                        <option value="dasar">Dasar (tahu konsep dasar)</option>
                        <option value="menengah">Menengah (pernah membuat project)</option>
                        <option value="ahli">Ahli (sudah bekerja sebagai programmer)</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="motivasi">Motivasi Mengikuti Kursus:</label>
                    <textarea id="motivasi" name="motivasi" rows="4" placeholder="Ceritakan mengapa Anda tertarik mengikuti kursus ini..."></textarea>
                </div>
            </fieldset>
            
            <fieldset>
                <legend>Dokumen Pendukung</legend>
                
                <div class="form-group">
                    <label for="cv">Upload CV (PDF):</label>
                    <input type="file" id="cv" name="cv" accept=".pdf">
                </div>
                
                <div class="form-group checkbox-group">
                    <input type="checkbox" id="setuju" name="setuju" required>
                    <label for="setuju" class="checkbox-label">Saya menyetujui <a href="#">syarat dan ketentuan</a> yang berlaku</label>
                </div>
            </fieldset>
            
            <div class="form-buttons">
                <button type="submit" class="btn btn-primary">Kirim Pendaftaran</button>
                <button type="reset" class="btn btn-secondary">Reset Form</button>
            </div>
        </form>
    </div>
</body>
</html>
```

### Contoh CSS untuk Form Pendaftaran (form-style.css):

```css
/* Reset CSS */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Base Styles */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f5f5f5;
    padding: 20px;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    background-color: white;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Header Styles */
header {
    text-align: center;
    margin-bottom: 30px;
}

h1 {
    color: #2c3e50;
    font-size: 28px;
    margin-bottom: 10px;
}

header p {
    color: #7f8c8d;
    font-size: 16px;
}

/* Form Styles */
form {
    display: block;
}

fieldset {
    border: 1px solid #ddd;
    border-radius: 5px;
    padding: 20px;
    margin-bottom: 25px;
}

legend {
    font-weight: bold;
    color: #2c3e50;
    padding: 0 10px;
    font-size: 18px;
}

.form-group {
    margin-bottom: 20px;
}

label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
    color: #2c3e50;
}

input[type="text"],
input[type="email"],
input[type="tel"],
input[type="date"],
select,
textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 16px;
    transition: border-color 0.3s;
}

input[type="text"]:focus,
input[type="email"]:focus,
input[type="tel"]:focus,
input[type="date"]:focus,
select:focus,
textarea:focus {
    border-color: #3498db;
    outline: none;
    box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
}

textarea {
    resize: vertical;
    min-height: 100px;
}

/* Radio and Checkbox Styles */
.radio-group,
.checkbox-group {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.radio-label,
.checkbox-label {
    display: inline;
    font-weight: normal;
    margin-left: 5px;
}

/* Button Styles */
.form-buttons {
    text-align: center;
    margin-top: 30px;
}

.btn {
    padding: 12px 24px;
    font-size: 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
    margin: 0 10px;
}

.btn-primary {
    background-color: #3498db;
    color: white;
}

.btn-secondary {
    background-color: #95a5a6;
    color: white;
}

.btn:hover {
    opacity: 0.9;
    transform: translateY(-2px);
}

.btn:active {
    transform: translateY(0);
}

/* Link Styles */
a {
    color: #3498db;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}

/* Responsive Adjustments */
@media (max-width: 600px) {
    .container {
        padding: 15px;
    }
    
    fieldset {
        padding: 15px;
    }
    
    .btn {
        width: 100%;
        margin: 10px 0;
    }
}
```

## Latihan Mandiri
1. Ambil form pendaftaran yang telah Anda buat sebelumnya
2. Buat file CSS eksternal dan hubungkan dengan HTML
3. Terapkan styling untuk teks (font, ukuran, warna, dll.)
4. Gunakan box model (margin, padding, border) untuk mengatur layout
5. Buat tombol yang menarik dengan efek hover
6. Pastikan form Anda responsif dan mudah dibaca
7. Tambahkan sentuhan kreatif Anda sendiri untuk membuat form lebih menarik

## Kesimpulan
- Styling teks dengan CSS memungkinkan kita mengontrol font, ukuran, warna, dan properti teks lainnya
- CSS Box Model terdiri dari content, padding, border, dan margin
- Properti box-sizing membantu mengontrol bagaimana ukuran elemen dihitung
- Kombinasi styling teks dan box model dapat membuat form dan elemen lain lebih menarik dan mudah digunakan
- Pemahaman yang baik tentang box model sangat penting untuk mengatur layout halaman web

## Referensi Tambahan
- [MDN Web Docs - CSS Text Styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text)
- [MDN Web Docs - The Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
- [CSS-Tricks - The CSS Box Model](https://css-tricks.com/the-css-box-model/)
- [Google Fonts](https://fonts.google.com/)