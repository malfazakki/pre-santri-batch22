# Hari 3: List, Table, Form (input, button)

## Tujuan Pembelajaran
- Memahami dan menggunakan berbagai jenis list dalam HTML
- Membuat dan mengatur tabel untuk menampilkan data
- Membuat form interaktif dengan berbagai elemen input
- Membuat latihan form pendaftaran

## 1. List dalam HTML

HTML menyediakan tiga jenis list untuk mengorganisir informasi:

### Unordered List (ul)
Digunakan untuk daftar item yang tidak memiliki urutan tertentu. Setiap item ditandai dengan bullet point.

```html
<ul>
    <li>Apel</li>
    <li>Jeruk</li>
    <li>Pisang</li>
    <li>Mangga</li>
</ul>
```

### Ordered List (ol)
Digunakan untuk daftar item yang memiliki urutan tertentu. Setiap item ditandai dengan nomor.

```html
<ol>
    <li>Langkah pertama</li>
    <li>Langkah kedua</li>
    <li>Langkah ketiga</li>
    <li>Langkah keempat</li>
</ol>
```

#### Atribut untuk Ordered List
- `type`: Menentukan jenis penomoran
  - `1`: Angka (default)
  - `A`: Huruf besar
  - `a`: Huruf kecil
  - `I`: Angka Romawi besar
  - `i`: Angka Romawi kecil
- `start`: Menentukan nilai awal penomoran

```html
<ol type="A" start="3">
    <li>Item ini akan dimulai dengan C</li>
    <li>Item ini akan menjadi D</li>
</ol>
```

### Description List (dl)
Digunakan untuk daftar istilah dan definisinya.

```html
<dl>
    <dt>HTML</dt>
    <dd>Hypertext Markup Language, bahasa standar untuk membuat halaman web.</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets, bahasa yang digunakan untuk mendesain tampilan halaman web.</dd>
    
    <dt>JavaScript</dt>
    <dd>Bahasa pemrograman yang membuat halaman web menjadi interaktif.</dd>
</dl>
```

### List Bersarang (Nested Lists)
List dapat disusun di dalam list lain untuk membuat struktur hierarkis.

```html
<ul>
    <li>Buah-buahan
        <ul>
            <li>Buah Tropis
                <ul>
                    <li>Mangga</li>
                    <li>Pisang</li>
                </ul>
            </li>
            <li>Buah Non-Tropis
                <ul>
                    <li>Apel</li>
                    <li>Pir</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>Sayuran
        <ul>
            <li>Sayuran Daun</li>
            <li>Sayuran Buah</li>
        </ul>
    </li>
</ul>
```

## 2. Tabel dalam HTML

Tabel digunakan untuk menampilkan data dalam format baris dan kolom.

### Struktur Dasar Tabel

```html
<table>
    <thead>
        <tr>
            <th>Nama</th>
            <th>Usia</th>
            <th>Pekerjaan</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John Doe</td>
            <td>30</td>
            <td>Web Developer</td>
        </tr>
        <tr>
            <td>Jane Smith</td>
            <td>25</td>
            <td>UI Designer</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="3">Data per 2023</td>
        </tr>
    </tfoot>
</table>
```

### Elemen-elemen Tabel
- `<table>`: Mendefinisikan tabel
- `<thead>`: Mengelompokkan konten header tabel
- `<tbody>`: Mengelompokkan konten utama tabel
- `<tfoot>`: Mengelompokkan konten footer tabel
- `<tr>`: Table Row, mendefinisikan baris
- `<th>`: Table Header, mendefinisikan sel header
- `<td>`: Table Data, mendefinisikan sel data

### Atribut Tabel
- `colspan`: Menggabungkan beberapa kolom
- `rowspan`: Menggabungkan beberapa baris
- `border`: Menentukan ketebalan border (lebih baik menggunakan CSS)
- `width` dan `height`: Menentukan dimensi tabel (lebih baik menggunakan CSS)

```html
<table border="1">
    <tr>
        <th>Nama</th>
        <th colspan="2">Kontak</th>
    </tr>
    <tr>
        <td>John Doe</td>
        <td>john@example.com</td>
        <td>123-456-7890</td>
    </tr>
    <tr>
        <td>Jane Smith</td>
        <td>jane@example.com</td>
        <td>098-765-4321</td>
    </tr>
</table>
```

### Tabel Kompleks
Tabel dapat dibuat lebih kompleks dengan menggabungkan sel dan menggunakan struktur yang lebih terorganisir.

```html
<table border="1">
    <caption>Jadwal Kelas</caption>
    <thead>
        <tr>
            <th>Waktu</th>
            <th>Senin</th>
            <th>Selasa</th>
            <th>Rabu</th>
            <th>Kamis</th>
            <th>Jumat</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>08:00 - 10:00</td>
            <td>HTML</td>
            <td>CSS</td>
            <td>JavaScript</td>
            <td rowspan="2">Project</td>
            <td>Review</td>
        </tr>
        <tr>
            <td>10:30 - 12:30</td>
            <td>CSS</td>
            <td>JavaScript</td>
            <td>HTML</td>
            <td>Quiz</td>
        </tr>
        <tr>
            <td>13:30 - 15:30</td>
            <td colspan="5" align="center">Praktikum</td>
        </tr>
    </tbody>
</table>
```

## 3. Form dalam HTML

Form digunakan untuk mengumpulkan input dari pengguna. Form dapat berisi berbagai elemen input seperti text field, checkbox, radio button, dan lainnya.

### Struktur Dasar Form

```html
<form action="proses.php" method="post">
    <label for="nama">Nama:</label>
    <input type="text" id="nama" name="nama" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <input type="submit" value="Kirim">
</form>
```

### Atribut Form
- `action`: URL tempat data form akan dikirim
- `method`: Metode HTTP yang digunakan untuk mengirim data (get atau post)
- `target`: Menentukan di mana respons akan ditampilkan
- `enctype`: Menentukan bagaimana data form dikodekan saat dikirim

### Elemen Input

#### Text Input
```html
<label for="username">Username:</label>
<input type="text" id="username" name="username" placeholder="Masukkan username" required>
```

#### Password Input
```html
<label for="password">Password:</label>
<input type="password" id="password" name="password" placeholder="Masukkan password" required>
```

#### Email Input
```html
<label for="email">Email:</label>
<input type="email" id="email" name="email" placeholder="contoh@email.com">
```

#### Number Input
```html
<label for="umur">Umur:</label>
<input type="number" id="umur" name="umur" min="18" max="100">
```

#### Date Input
```html
<label for="tanggal">Tanggal Lahir:</label>
<input type="date" id="tanggal" name="tanggal">
```

#### Radio Buttons
```html
<p>Jenis Kelamin:</p>
<input type="radio" id="pria" name="gender" value="pria">
<label for="pria">Pria</label><br>
<input type="radio" id="wanita" name="gender" value="wanita">
<label for="wanita">Wanita</label>
```

#### Checkboxes
```html
<p>Hobi:</p>
<input type="checkbox" id="membaca" name="hobi" value="membaca">
<label for="membaca">Membaca</label><br>
<input type="checkbox" id="olahraga" name="hobi" value="olahraga">
<label for="olahraga">Olahraga</label><br>
<input type="checkbox" id="musik" name="hobi" value="musik">
<label for="musik">Musik</label>
```

#### Dropdown List
```html
<label for="kota">Kota:</label>
<select id="kota" name="kota">
    <option value="">Pilih Kota</option>
    <option value="jakarta">Jakarta</option>
    <option value="bandung">Bandung</option>
    <option value="surabaya">Surabaya</option>
    <option value="yogyakarta">Yogyakarta</option>
</select>
```

#### Textarea
```html
<label for="pesan">Pesan:</label><br>
<textarea id="pesan" name="pesan" rows="4" cols="50" placeholder="Tulis pesan Anda di sini..."></textarea>
```

#### File Input
```html
<label for="file">Upload File:</label>
<input type="file" id="file" name="file">
```

#### Hidden Input
```html
<input type="hidden" id="userid" name="userid" value="12345">
```

#### Button
```html
<button type="button" onclick="alert('Hello World!')">Klik Saya</button>
<button type="submit">Kirim</button>
<button type="reset">Reset</button>
```

### Atribut Input Penting
- `type`: Jenis input (text, password, email, dll.)
- `name`: Nama untuk mengidentifikasi data saat dikirim
- `id`: Pengenal unik untuk elemen (digunakan dengan label)
- `value`: Nilai default
- `placeholder`: Teks petunjuk yang muncul di dalam input
- `required`: Menandakan bahwa input harus diisi
- `disabled`: Menonaktifkan input
- `readonly`: Membuat input hanya bisa dibaca
- `min` dan `max`: Nilai minimum dan maksimum (untuk input numerik)
- `pattern`: Pola regex untuk validasi

## 4. Praktik: Membuat Form Pendaftaran

### Langkah-langkah:
1. Buat file HTML baru dengan nama `form-pendaftaran.html`
2. Tambahkan struktur dasar HTML
3. Buat form dengan berbagai elemen input
4. Tambahkan validasi dasar
5. Simpan file dan buka di browser

### Contoh Form Pendaftaran:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Pendaftaran</title>
</head>
<body>
    <h1>Form Pendaftaran Kursus</h1>
    
    <form action="#" method="post">
        <h2>Data Pribadi</h2>
        
        <label for="nama_lengkap">Nama Lengkap:</label><br>
        <input type="text" id="nama_lengkap" name="nama_lengkap" required><br><br>
        
        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" required><br><br>
        
        <label for="telepon">Nomor Telepon:</label><br>
        <input type="tel" id="telepon" name="telepon" pattern="[0-9]{10,13}" placeholder="Contoh: 08123456789"><br><br>
        
        <label for="tanggal_lahir">Tanggal Lahir:</label><br>
        <input type="date" id="tanggal_lahir" name="tanggal_lahir"><br><br>
        
        <p>Jenis Kelamin:</p>
        <input type="radio" id="pria" name="gender" value="pria">
        <label for="pria">Pria</label><br>
        <input type="radio" id="wanita" name="gender" value="wanita">
        <label for="wanita">Wanita</label><br><br>
        
        <h2>Informasi Kursus</h2>
        
        <label for="program">Program yang Diminati:</label><br>
        <select id="program" name="program" required>
            <option value="">Pilih Program</option>
            <option value="web">Web Development</option>
            <option value="mobile">Mobile App Development</option>
            <option value="data">Data Science</option>
            <option value="ui">UI/UX Design</option>
        </select><br><br>
        
        <p>Jadwal yang Diinginkan:</p>
        <input type="checkbox" id="pagi" name="jadwal" value="pagi">
        <label for="pagi">Pagi (08.00 - 12.00)</label><br>
        <input type="checkbox" id="siang" name="jadwal" value="siang">
        <label for="siang">Siang (13.00 - 17.00)</label><br>
        <input type="checkbox" id="malam" name="jadwal" value="malam">
        <label for="malam">Malam (18.00 - 21.00)</label><br><br>
        
        <label for="pengalaman">Pengalaman Programming:</label><br>
        <select id="pengalaman" name="pengalaman">
            <option value="pemula">Pemula (belum pernah)</option>
            <option value="dasar">Dasar (tahu konsep dasar)</option>
            <option value="menengah">Menengah (pernah membuat project)</option>
            <option value="ahli">Ahli (sudah bekerja sebagai programmer)</option>
        </select><br><br>
        
        <label for="motivasi">Motivasi Mengikuti Kursus:</label><br>
        <textarea id="motivasi" name="motivasi" rows="4" cols="50" placeholder="Ceritakan mengapa Anda tertarik mengikuti kursus ini..."></textarea><br><br>
        
        <h2>Dokumen Pendukung</h2>
        
        <label for="cv">Upload CV (PDF):</label><br>
        <input type="file" id="cv" name="cv" accept=".pdf"><br><br>
        
        <input type="checkbox" id="setuju" name="setuju" required>
        <label for="setuju">Saya menyetujui syarat dan ketentuan yang berlaku</label><br><br>
        
        <button type="submit">Kirim Pendaftaran</button>
        <button type="reset">Reset Form</button>
    </form>
</body>
</html>
```

## Latihan Mandiri
1. Buat form pendaftaran dengan minimal 10 elemen input berbeda
2. Gunakan validasi dasar seperti required, min, max, pattern
3. Kelompokkan input yang berhubungan menggunakan heading atau fieldset
4. Tambahkan tombol submit dan reset
5. Pastikan form Anda memiliki tampilan yang rapi dan mudah digunakan

## Kesimpulan
- List digunakan untuk menampilkan informasi dalam bentuk daftar (ordered, unordered, atau description)
- Tabel digunakan untuk menampilkan data dalam format baris dan kolom
- Form digunakan untuk mengumpulkan input dari pengguna
- Elemen input memiliki berbagai tipe untuk mengumpulkan berbagai jenis data
- Validasi form membantu memastikan data yang dimasukkan sesuai dengan yang diharapkan

## Referensi Tambahan
- [MDN Web Docs - HTML Lists](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
- [MDN Web Docs - HTML Tables](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
- [MDN Web Docs - HTML Forms](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
- [W3Schools - HTML Forms](https://www.w3schools.com/html/html_forms.asp)