# Hari 2: Tag Umum HTML (Heading, Paragraph, Link, Image)

## Tujuan Pembelajaran
- Memahami dan menggunakan tag heading (h1-h6)
- Membuat paragraf dengan tag p
- Menambahkan link menggunakan tag a
- Menyisipkan gambar dengan tag img
- Membuat halaman biodata sederhana

## 1. Tag Heading (h1-h6)

Heading digunakan untuk menampilkan judul atau subjudul dalam halaman web. HTML menyediakan enam level heading, dari `<h1>` (paling penting) hingga `<h6>` (paling tidak penting).

```html
<h1>Ini adalah Heading 1</h1>
<h2>Ini adalah Heading 2</h2>
<h3>Ini adalah Heading 3</h3>
<h4>Ini adalah Heading 4</h4>
<h5>Ini adalah Heading 5</h5>
<h6>Ini adalah Heading 6</h6>
```

### Praktik Terbaik untuk Heading
- Gunakan `<h1>` hanya sekali per halaman, biasanya untuk judul utama
- Gunakan heading secara hierarkis (h1, lalu h2, lalu h3, dst.)
- Jangan lewati level heading (misalnya dari h1 langsung ke h3)
- Jangan gunakan heading hanya untuk membuat teks tebal atau besar

## 2. Tag Paragraph (p)

Tag `<p>` digunakan untuk membuat paragraf teks.

```html
<p>Ini adalah paragraf pertama. Tag p membuat baris baru sebelum dan sesudah paragraf, memberikan ruang antara blok teks.</p>
<p>Ini adalah paragraf kedua. Perhatikan bahwa ada jarak antara paragraf ini dan paragraf sebelumnya.</p>
```

### Pemformatan Teks dalam Paragraf

Beberapa tag pemformatan teks yang dapat digunakan dalam paragraf:

```html
<p>Teks <strong>tebal</strong> menggunakan tag strong.</p>
<p>Teks <em>miring</em> menggunakan tag em.</p>
<p>Teks <mark>disorot</mark> menggunakan tag mark.</p>
<p>Teks <small>kecil</small> menggunakan tag small.</p>
<p>Teks <del>dicoret</del> menggunakan tag del.</p>
<p>Teks <ins>digarisbawahi</ins> menggunakan tag ins.</p>
<p>Teks <sub>subscript</sub> dan <sup>superscript</sup> menggunakan tag sub dan sup.</p>
```

### Tag br dan hr

- `<br>`: Membuat jeda baris (line break) tanpa membuat paragraf baru
- `<hr>`: Membuat garis horizontal (horizontal rule)

```html
<p>Baris pertama.<br>Baris kedua dalam paragraf yang sama.</p>
<hr>
<p>Paragraf setelah garis horizontal.</p>
```

## 3. Tag Link (a)

Tag `<a>` (anchor) digunakan untuk membuat hyperlink ke halaman web lain, file, lokasi di halaman yang sama, alamat email, atau URL lainnya.

### Sintaks Dasar

```html
<a href="url">Teks Link</a>
```

### Contoh Penggunaan Link

```html
<!-- Link ke halaman web eksternal -->
<a href="https://www.google.com">Kunjungi Google</a>

<!-- Link ke halaman web internal -->
<a href="halaman2.html">Halaman 2</a>

<!-- Link ke bagian tertentu dalam halaman yang sama -->
<a href="#section1">Pergi ke Bagian 1</a>
<h2 id="section1">Bagian 1</h2>

<!-- Link untuk mengirim email -->
<a href="mailto:contoh@email.com">Kirim Email</a>

<!-- Link untuk mendownload file -->
<a href="dokumen.pdf" download>Download PDF</a>
```

### Atribut Penting untuk Tag a

- `href`: URL tujuan link
- `target`: Menentukan di mana link akan dibuka
  - `_self`: Halaman yang sama (default)
  - `_blank`: Tab atau jendela baru
  - `_parent`: Frame induk
  - `_top`: Jendela penuh
- `title`: Teks tooltip yang muncul saat mouse hover
- `download`: Menandakan bahwa link adalah untuk mengunduh file

```html
<a href="https://www.example.com" target="_blank" title="Buka Example.com di tab baru">Example.com</a>
```

## 4. Tag Image (img)

Tag `<img>` digunakan untuk menyisipkan gambar ke dalam halaman web.

### Sintaks Dasar

```html
<img src="url_gambar" alt="teks alternatif">
```

### Contoh Penggunaan Gambar

```html
<!-- Gambar dari folder yang sama -->
<img src="gambar.jpg" alt="Deskripsi gambar">

<!-- Gambar dari subfolder -->
<img src="images/gambar.jpg" alt="Deskripsi gambar">

<!-- Gambar dari URL eksternal -->
<img src="https://www.example.com/gambar.jpg" alt="Deskripsi gambar">
```

### Atribut Penting untuk Tag img

- `src`: URL atau path ke file gambar (wajib)
- `alt`: Teks alternatif yang ditampilkan jika gambar tidak dapat dimuat (wajib untuk aksesibilitas)
- `width`: Lebar gambar (dalam piksel atau persentase)
- `height`: Tinggi gambar (dalam piksel atau persentase)
- `title`: Teks tooltip yang muncul saat mouse hover

```html
<img src="profile.jpg" alt="Foto Profil" width="200" height="200" title="Foto Profil Saya">
```

### Praktik Terbaik untuk Gambar

- Selalu sertakan atribut `alt` untuk aksesibilitas
- Tentukan dimensi gambar untuk mencegah layout shift saat halaman dimuat
- Gunakan format gambar yang sesuai (JPG untuk foto, PNG untuk gambar dengan transparansi, SVG untuk ikon)
- Optimalkan ukuran file gambar untuk kecepatan loading

## 5. Menggabungkan Semua Elemen

Berikut contoh menggabungkan heading, paragraf, link, dan gambar:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Saya</title>
</head>
<body>
    <h1>Profil Saya</h1>
    
    <img src="foto_profil.jpg" alt="Foto Profil" width="150" height="150">
    
    <h2>Tentang Saya</h2>
    <p>Halo! Nama saya <strong>Nama Lengkap</strong>. Saya adalah seorang web developer pemula yang sedang belajar HTML dan CSS.</p>
    
    <h2>Hobi</h2>
    <p>Beberapa hobi saya antara lain:</p>
    <p>Membaca buku, menonton film, dan belajar hal-hal baru tentang teknologi.</p>
    
    <h2>Kontak</h2>
    <p>Anda dapat menghubungi saya melalui:</p>
    <p>
        Email: <a href="mailto:email@example.com">email@example.com</a><br>
        LinkedIn: <a href="https://www.linkedin.com/in/username" target="_blank">LinkedIn Profile</a>
    </p>
    
    <hr>
    
    <p>Terima kasih telah mengunjungi halaman profil saya!</p>
</body>
</html>
```

## 6. Praktik: Membuat Halaman Biodata Sederhana

### Langkah-langkah:
1. Buat file HTML baru dengan nama `biodata.html`
2. Tambahkan struktur dasar HTML
3. Buat judul halaman menggunakan tag `<h1>`
4. Tambahkan foto profil menggunakan tag `<img>`
5. Buat beberapa bagian (seperti data pribadi, pendidikan, keahlian) menggunakan heading `<h2>`
6. Isi setiap bagian dengan paragraf `<p>`
7. Tambahkan link ke media sosial atau email
8. Simpan file dan buka di browser

### Contoh Struktur Halaman Biodata:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biodata - Nama Anda</title>
</head>
<body>
    <h1>Biodata</h1>
    
    <img src="foto_saya.jpg" alt="Foto Saya" width="200" height="200">
    
    <h2>Data Pribadi</h2>
    <p>
        <strong>Nama:</strong> Nama Lengkap Anda<br>
        <strong>Tempat, Tanggal Lahir:</strong> Kota, DD Bulan YYYY<br>
        <strong>Alamat:</strong> Alamat Lengkap Anda<br>
        <strong>Email:</strong> <a href="mailto:email@example.com">email@example.com</a>
    </p>
    
    <h2>Pendidikan</h2>
    <p>
        <strong>2018-2022:</strong> Universitas Contoh, Jurusan Ilmu Komputer<br>
        <strong>2015-2018:</strong> SMA Contoh
    </p>
    
    <h2>Keahlian</h2>
    <p>
        HTML, CSS, JavaScript, Desain Grafis, Microsoft Office
    </p>
    
    <h2>Pengalaman</h2>
    <p>
        <strong>2022-Sekarang:</strong> Web Developer di Perusahaan Contoh<br>
        <strong>2021-2022:</strong> Magang sebagai UI/UX Designer di Startup Contoh
    </p>
    
    <h2>Media Sosial</h2>
    <p>
        <a href="https://www.linkedin.com/in/username" target="_blank">LinkedIn</a><br>
        <a href="https://github.com/username" target="_blank">GitHub</a><br>
        <a href="https://www.instagram.com/username" target="_blank">Instagram</a>
    </p>
    
    <hr>
    
    <p>Terakhir diperbarui: Juni 2023</p>
</body>
</html>
```

## Latihan Mandiri
1. Buat halaman biodata pribadi Anda menggunakan semua elemen yang telah dipelajari
2. Tambahkan minimal 3 bagian (misalnya: data pribadi, pendidikan, hobi)
3. Sertakan minimal 1 gambar
4. Tambahkan minimal 3 link (ke email, media sosial, atau website favorit)
5. Gunakan tag pemformatan teks untuk menekankan informasi penting

## Kesimpulan
- Tag heading (`<h1>` hingga `<h6>`) digunakan untuk judul dan subjudul
- Tag paragraf (`<p>`) digunakan untuk membuat blok teks
- Tag link (`<a>`) digunakan untuk membuat hyperlink
- Tag gambar (`<img>`) digunakan untuk menyisipkan gambar
- Kombinasi tag-tag ini memungkinkan kita membuat halaman web dengan konten yang terstruktur dan informatif

## Referensi Tambahan
- [MDN Web Docs - HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [W3Schools - HTML Tutorial](https://www.w3schools.com/html/)
- [HTML.com - HTML Cheat Sheet](https://html.com/cheat-sheet/)