# Hari 4: Semantic HTML (header, main, footer, section)

## Tujuan Pembelajaran
- Memahami konsep dan pentingnya Semantic HTML
- Mengenal elemen-elemen semantic dalam HTML5
- Menggunakan elemen semantic untuk struktur halaman web
- Merapikan struktur halaman menggunakan tag semantic

## 1. Pengenalan Semantic HTML

### Apa itu Semantic HTML?
Semantic HTML adalah penggunaan elemen HTML yang maknanya menggambarkan tujuan atau isi dari elemen tersebut, bukan hanya bagaimana tampilannya. Semantic HTML memberikan informasi tentang struktur dan makna konten kepada browser, mesin pencari, pembaca layar, dan pengembang lain.

### Mengapa Semantic HTML Penting?
1. **Aksesibilitas**: Membantu teknologi assistive (seperti pembaca layar) memahami struktur halaman
2. **SEO (Search Engine Optimization)**: Membantu mesin pencari memahami konten halaman
3. **Maintainability**: Membuat kode lebih mudah dibaca dan dipelihara
4. **Konsistensi**: Mendorong struktur halaman yang konsisten

### Perbedaan Non-Semantic vs Semantic HTML

**Non-Semantic HTML:**
```html
<div class="header">
    <h1>Judul Website</h1>
    <div class="nav">
        <ul>
            <li><a href="#">Beranda</a></li>
            <li><a href="#">Tentang</a></li>
            <li><a href="#">Kontak</a></li>
        </ul>
    </div>
</div>

<div class="content">
    <div class="article">
        <h2>Artikel 1</h2>
        <p>Konten artikel...</p>
    </div>
    <div class="sidebar">
        <h3>Artikel Terkait</h3>
        <ul>
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
        </ul>
    </div>
</div>

<div class="footer">
    <p>Hak Cipta &copy; 2023</p>
</div>
```

**Semantic HTML:**
```html
<header>
    <h1>Judul Website</h1>
    <nav>
        <ul>
            <li><a href="#">Beranda</a></li>
            <li><a href="#">Tentang</a></li>
            <li><a href="#">Kontak</a></li>
        </ul>
    </nav>
</header>

<main>
    <article>
        <h2>Artikel 1</h2>
        <p>Konten artikel...</p>
    </article>
    <aside>
        <h3>Artikel Terkait</h3>
        <ul>
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
        </ul>
    </aside>
</main>

<footer>
    <p>Hak Cipta &copy; 2023</p>
</footer>
```

## 2. Elemen-elemen Semantic HTML5

### Elemen Struktur Utama

#### `<header>`
Mendefinisikan bagian header dari halaman atau section. Biasanya berisi judul, logo, dan navigasi utama.

```html
<header>
    <h1>Nama Website</h1>
    <img src="logo.png" alt="Logo">
    <nav>
        <!-- Menu navigasi -->
    </nav>
</header>
```

#### `<nav>`
Mendefinisikan bagian navigasi. Berisi link-link navigasi utama.

```html
<nav>
    <ul>
        <li><a href="index.html">Beranda</a></li>
        <li><a href="about.html">Tentang</a></li>
        <li><a href="services.html">Layanan</a></li>
        <li><a href="contact.html">Kontak</a></li>
    </ul>
</nav>
```

#### `<main>`
Mendefinisikan konten utama dari halaman. Setiap halaman hanya boleh memiliki satu elemen `<main>`.

```html
<main>
    <h2>Judul Konten Utama</h2>
    <p>Paragraf konten utama...</p>
    <!-- Konten utama lainnya -->
</main>
```

#### `<article>`
Mendefinisikan konten yang berdiri sendiri dan dapat didistribusikan secara independen (seperti artikel blog, berita, atau komentar).

```html
<article>
    <h2>Judul Artikel</h2>
    <p>Tanggal publikasi: <time datetime="2023-06-15">15 Juni 2023</time></p>
    <p>Konten artikel...</p>
</article>
```

#### `<section>`
Mendefinisikan bagian tematik dalam dokumen. Biasanya memiliki heading.

```html
<section>
    <h2>Layanan Kami</h2>
    <p>Deskripsi layanan...</p>
    <!-- Konten section lainnya -->
</section>
```

#### `<aside>`
Mendefinisikan konten yang berhubungan secara tidak langsung dengan konten utama (sidebar, iklan, dll).

```html
<aside>
    <h3>Artikel Terkait</h3>
    <ul>
        <li><a href="#">Artikel 1</a></li>
        <li><a href="#">Artikel 2</a></li>
    </ul>
</aside>
```

#### `<footer>`
Mendefinisikan bagian footer dari halaman atau section. Biasanya berisi informasi hak cipta, kontak, dan link-link terkait.

```html
<footer>
    <p>Hak Cipta &copy; 2023 Nama Website</p>
    <address>
        Kontak: <a href="mailto:info@example.com">info@example.com</a>
    </address>
</footer>
```

### Elemen Semantic Lainnya

#### `<figure>` dan `<figcaption>`
Mendefinisikan konten mandiri seperti ilustrasi, diagram, foto, dll., dengan caption opsional.

```html
<figure>
    <img src="diagram.jpg" alt="Diagram Proses">
    <figcaption>Gambar 1: Diagram alur proses produksi</figcaption>
</figure>
```

#### `<time>`
Mendefinisikan waktu atau tanggal.

```html
<p>Acara akan dimulai pada <time datetime="2023-07-20T19:00">20 Juli 2023, pukul 19:00</time>.</p>
```

#### `<mark>`
Mendefinisikan teks yang disorot/ditandai.

```html
<p>Perhatikan <mark>bagian penting</mark> dari teks ini.</p>
```

#### `<details>` dan `<summary>`
Membuat widget disclosure yang dapat dibuka/ditutup.

```html
<details>
    <summary>Baca selengkapnya</summary>
    <p>Ini adalah konten tambahan yang akan muncul ketika pengguna mengklik "Baca selengkapnya".</p>
</details>
```

#### `<address>`
Mendefinisikan informasi kontak.

```html
<address>
    Ditulis oleh <a href="mailto:john@example.com">John Doe</a>.<br>
    Kunjungi kami di:<br>
    Example.com<br>
    Jalan Contoh No. 123<br>
    Kota Contoh
</address>
```

## 3. Struktur Halaman Web dengan Semantic HTML

Berikut adalah contoh struktur halaman web lengkap menggunakan elemen semantic:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website Semantic HTML</title>
</head>
<body>
    <header>
        <h1>Nama Website</h1>
        <nav>
            <ul>
                <li><a href="#">Beranda</a></li>
                <li><a href="#">Tentang</a></li>
                <li><a href="#">Layanan</a></li>
                <li><a href="#">Blog</a></li>
                <li><a href="#">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="hero">
            <h2>Selamat Datang di Website Kami</h2>
            <p>Deskripsi singkat tentang website dan layanan yang ditawarkan.</p>
        </section>

        <section id="layanan">
            <h2>Layanan Kami</h2>
            
            <article>
                <h3>Layanan 1</h3>
                <p>Deskripsi layanan 1...</p>
            </article>
            
            <article>
                <h3>Layanan 2</h3>
                <p>Deskripsi layanan 2...</p>
            </article>
            
            <article>
                <h3>Layanan 3</h3>
                <p>Deskripsi layanan 3...</p>
            </article>
        </section>

        <section id="blog">
            <h2>Blog Terbaru</h2>
            
            <article>
                <h3>Judul Artikel 1</h3>
                <p>Ditulis pada <time datetime="2023-06-10">10 Juni 2023</time></p>
                <p>Ringkasan artikel 1...</p>
                <a href="#">Baca selengkapnya</a>
            </article>
            
            <article>
                <h3>Judul Artikel 2</h3>
                <p>Ditulis pada <time datetime="2023-06-05">5 Juni 2023</time></p>
                <p>Ringkasan artikel 2...</p>
                <a href="#">Baca selengkapnya</a>
            </article>
        </section>

        <aside>
            <h3>Kategori</h3>
            <ul>
                <li><a href="#">Kategori 1</a></li>
                <li><a href="#">Kategori 2</a></li>
                <li><a href="#">Kategori 3</a></li>
            </ul>
            
            <h3>Artikel Populer</h3>
            <ul>
                <li><a href="#">Artikel Populer 1</a></li>
                <li><a href="#">Artikel Populer 2</a></li>
                <li><a href="#">Artikel Populer 3</a></li>
            </ul>
        </aside>
    </main>

    <footer>
        <section id="kontak">
            <h3>Hubungi Kami</h3>
            <address>
                Email: <a href="mailto:info@example.com">info@example.com</a><br>
                Telepon: <a href="tel:+6281234567890">+62 812-3456-7890</a><br>
                Alamat: Jalan Contoh No. 123, Kota Contoh
            </address>
        </section>
        
        <section id="sosial-media">
            <h3>Ikuti Kami</h3>
            <ul>
                <li><a href="#">Facebook</a></li>
                <li><a href="#">Twitter</a></li>
                <li><a href="#">Instagram</a></li>
                <li><a href="#">LinkedIn</a></li>
            </ul>
        </section>
        
        <p>&copy; 2023 Nama Website. Hak Cipta Dilindungi.</p>
    </footer>
</body>
</html>
```

## 4. Praktik: Merapikan Struktur Halaman dengan Semantic Tag

### Langkah-langkah:
1. Ambil halaman HTML yang sudah dibuat sebelumnya (misalnya halaman biodata atau form pendaftaran)
2. Identifikasi bagian-bagian yang dapat menggunakan tag semantic
3. Ganti tag `<div>` dengan tag semantic yang sesuai
4. Tambahkan tag semantic lain yang diperlukan
5. Simpan file dan buka di browser

### Contoh Sebelum dan Sesudah:

**Sebelum (Non-Semantic):**
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Saya</title>
</head>
<body>
    <div class="header">
        <h1>Profil Saya</h1>
        <div class="nav">
            <ul>
                <li><a href="#">Beranda</a></li>
                <li><a href="#">Tentang</a></li>
                <li><a href="#">Portofolio</a></li>
                <li><a href="#">Kontak</a></li>
            </ul>
        </div>
    </div>

    <div class="main-content">
        <div class="profile-section">
            <h2>Tentang Saya</h2>
            <img src="foto.jpg" alt="Foto Profil">
            <p>Perkenalkan, nama saya John Doe. Saya adalah seorang web developer...</p>
        </div>

        <div class="education-section">
            <h2>Pendidikan</h2>
            <ul>
                <li>S1 Teknik Informatika - Universitas Contoh (2018-2022)</li>
                <li>SMA Negeri 1 Contoh (2015-2018)</li>
            </ul>
        </div>

        <div class="skills-section">
            <h2>Keahlian</h2>
            <ul>
                <li>HTML & CSS</li>
                <li>JavaScript</li>
                <li>PHP</li>
                <li>MySQL</li>
            </ul>
        </div>

        <div class="sidebar">
            <div class="contact-info">
                <h3>Informasi Kontak</h3>
                <p>Email: john@example.com</p>
                <p>Telepon: 081234567890</p>
            </div>
        </div>
    </div>

    <div class="footer">
        <p>&copy; 2023 John Doe. Hak Cipta Dilindungi.</p>
    </div>
</body>
</html>
```

**Sesudah (Semantic):**
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Saya</title>
</head>
<body>
    <header>
        <h1>Profil Saya</h1>
        <nav>
            <ul>
                <li><a href="#">Beranda</a></li>
                <li><a href="#">Tentang</a></li>
                <li><a href="#">Portofolio</a></li>
                <li><a href="#">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="tentang">
            <h2>Tentang Saya</h2>
            <figure>
                <img src="foto.jpg" alt="Foto Profil">
                <figcaption>John Doe - Web Developer</figcaption>
            </figure>
            <p>Perkenalkan, nama saya John Doe. Saya adalah seorang web developer...</p>
        </section>

        <section id="pendidikan">
            <h2>Pendidikan</h2>
            <ul>
                <li>S1 Teknik Informatika - Universitas Contoh (2018-2022)</li>
                <li>SMA Negeri 1 Contoh (2015-2018)</li>
            </ul>
        </section>

        <section id="keahlian">
            <h2>Keahlian</h2>
            <ul>
                <li>HTML & CSS</li>
                <li>JavaScript</li>
                <li>PHP</li>
                <li>MySQL</li>
            </ul>
        </section>

        <aside>
            <h3>Informasi Kontak</h3>
            <address>
                Email: <a href="mailto:john@example.com">john@example.com</a><br>
                Telepon: <a href="tel:+6281234567890">081234567890</a>
            </address>
        </aside>
    </main>

    <footer>
        <p>&copy; 2023 John Doe. Hak Cipta Dilindungi.</p>
    </footer>
</body>
</html>
```

## Latihan Mandiri
1. Ambil halaman HTML yang telah Anda buat sebelumnya (biodata atau form pendaftaran)
2. Ubah struktur halaman menggunakan tag semantic HTML5
3. Pastikan untuk menggunakan minimal 6 elemen semantic berbeda (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, dll.)
4. Tambahkan elemen semantic tambahan seperti `<figure>`, `<time>`, atau `<address>` jika sesuai
5. Validasi HTML Anda menggunakan [W3C Validator](https://validator.w3.org/)

## Kesimpulan
- Semantic HTML memberikan makna pada struktur halaman web, bukan hanya tampilan
- Penggunaan tag semantic meningkatkan aksesibilitas, SEO, dan maintainability
- HTML5 menyediakan berbagai elemen semantic seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>`
- Struktur halaman yang baik menggunakan kombinasi elemen semantic yang tepat
- Mengganti `<div>` dengan tag semantic yang sesuai membuat kode lebih mudah dibaca dan dipahami

## Referensi Tambahan
- [MDN Web Docs - HTML elements reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [W3Schools - HTML Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)
- [HTML5 Doctor - HTML5 sectioning elements](http://html5doctor.com/outlines/)
- [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/)