# Hari 1: Apa itu Web? Struktur HTML

## Tujuan Pembelajaran
- Memahami konsep dasar web dan internet
- Mengenal struktur dasar dokumen HTML
- Membuat dokumen HTML sederhana

## 1. Apa itu Web?

### World Wide Web (WWW)
Web atau World Wide Web adalah sistem informasi yang dapat diakses melalui internet. Web terdiri dari halaman-halaman yang saling terhubung menggunakan hyperlink. Halaman web disimpan di server dan dapat diakses oleh pengguna melalui browser web.

### Bagaimana Web Bekerja?
1. **Client-Server Model**: Web menggunakan model client-server, di mana browser (client) meminta informasi dari server web.
2. **HTTP (Hypertext Transfer Protocol)**: Protokol yang digunakan untuk komunikasi antara client dan server.
3. **URL (Uniform Resource Locator)**: Alamat yang digunakan untuk mengakses halaman web, misalnya: https://www.example.com.

### Komponen Utama Web
- **Browser**: Program yang digunakan untuk mengakses dan menampilkan halaman web (Chrome, Firefox, Safari, dll).
- **Server Web**: Komputer yang menyimpan dan mengirimkan halaman web ke browser.
- **HTML**: Bahasa markup yang digunakan untuk membuat struktur halaman web.
- **CSS**: Bahasa yang digunakan untuk mengatur tampilan halaman web.
- **JavaScript**: Bahasa pemrograman yang membuat halaman web interaktif.

## 2. Pengenalan HTML

### Apa itu HTML?
HTML (Hypertext Markup Language) adalah bahasa markup standar yang digunakan untuk membuat halaman web. HTML menggunakan tag untuk mendefinisikan struktur dan konten halaman web.

### Sejarah Singkat HTML
- HTML diciptakan oleh Tim Berners-Lee pada tahun 1991
- Versi terbaru adalah HTML5 (dirilis tahun 2014)
- HTML terus berkembang dengan fitur-fitur baru

## 3. Struktur Dasar HTML

### Anatomi Dokumen HTML
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Judul Halaman</title>
</head>
<body>
    <!-- Konten halaman web akan ditulis di sini -->
    <h1>Halo Dunia!</h1>
    <p>Ini adalah paragraf pertama saya.</p>
</body>
</html>
```

### Penjelasan Struktur
- `<!DOCTYPE html>`: Deklarasi tipe dokumen, memberitahu browser bahwa dokumen ini adalah HTML5.
- `<html>`: Elemen root yang membungkus seluruh konten HTML.
- `<head>`: Berisi informasi tentang dokumen (metadata) yang tidak ditampilkan di halaman.
- `<meta charset="UTF-8">`: Menentukan pengkodean karakter dokumen.
- `<title>`: Menentukan judul halaman yang muncul di tab browser.
- `<body>`: Berisi semua konten yang akan ditampilkan di halaman web.
- `<!-- -->`: Komentar dalam HTML, tidak ditampilkan di browser.

### Tag dan Elemen
- **Tag**: Markup yang digunakan untuk mendefinisikan elemen HTML, ditulis dalam tanda kurung sudut (`<` dan `>`).
- **Elemen**: Terdiri dari tag pembuka, konten, dan tag penutup. Contoh: `<p>Ini adalah paragraf</p>`.
- **Tag Penutup**: Sama dengan tag pembuka tetapi memiliki garis miring (`/`). Contoh: `</p>`.
- **Elemen Kosong**: Elemen tanpa konten, seperti `<img>` atau `<br>`. Dapat ditulis sebagai `<br>` atau `<br />`.

### Atribut HTML
Atribut memberikan informasi tambahan tentang elemen HTML.
```html
<tag attribute="value">Konten</tag>
```

Contoh:
```html
<a href="https://www.example.com">Kunjungi Example.com</a>
```

Atribut umum:
- `id`: Pengenal unik untuk elemen
- `class`: Mengelompokkan elemen untuk styling CSS
- `style`: Menambahkan styling inline
- `title`: Memberikan informasi tambahan (muncul saat hover)

## 4. Praktik: Membuat Dokumen HTML Sederhana

### Langkah-langkah:
1. Buka editor teks (Notepad, VS Code, dll.)
2. Buat file baru dengan ekstensi .html (misalnya: index.html)
3. Tulis struktur dasar HTML
4. Tambahkan beberapa konten sederhana
5. Simpan file
6. Buka file dengan browser

### Contoh Dokumen HTML Sederhana:
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halaman Pertama Saya</title>
</head>
<body>
    <h1>Selamat Datang di Halaman Web Pertama Saya</h1>
    <p>Ini adalah halaman web pertama yang saya buat menggunakan HTML.</p>
    <p>Saya sedang belajar pengembangan web.</p>
</body>
</html>
```

## Latihan Mandiri
1. Buat dokumen HTML dengan struktur dasar yang benar
2. Tambahkan judul halaman "Tentang Saya"
3. Tambahkan heading dan beberapa paragraf tentang diri Anda
4. Buka file dengan browser dan perhatikan hasilnya

## Kesimpulan
- Web adalah sistem informasi yang dapat diakses melalui internet
- HTML adalah bahasa markup yang digunakan untuk membuat struktur halaman web
- Struktur dasar HTML terdiri dari `<!DOCTYPE>`, `<html>`, `<head>`, dan `<body>`
- Tag HTML digunakan untuk mendefinisikan elemen-elemen dalam halaman web

## Referensi Tambahan
- [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools - HTML Tutorial](https://www.w3schools.com/html/)
- [HTML.com](https://html.com/)