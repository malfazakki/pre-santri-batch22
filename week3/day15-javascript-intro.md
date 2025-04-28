# Hari 15: Intro JavaScript (Variabel, Tipe Data)

## Tujuan Pembelajaran
- Memahami apa itu JavaScript dan kegunaannya
- Mengenal cara penulisan JavaScript dalam HTML
- Memahami variabel dan cara deklarasinya
- Mengenal berbagai tipe data dalam JavaScript
- Membuat script sederhana di halaman web

## 1. Pengenalan JavaScript

### Apa itu JavaScript?
JavaScript adalah bahasa pemrograman yang digunakan untuk membuat website menjadi interaktif. JavaScript dapat:
- Mengubah konten HTML
- Memodifikasi style CSS
- Merespons interaksi user
- Melakukan perhitungan
- Mengumpulkan data
- Membuat animasi
- Dan banyak lagi

### Cara Menambahkan JavaScript ke HTML

#### 1. Internal JavaScript (dalam file HTML)
```html
<!DOCTYPE html>
<html>
<head>
    <title>Internal JavaScript</title>
</head>
<body>
    <!-- Di bagian head atau body -->
    <script>
        console.log("Hello World!");
    </script>
</body>
</html>
```

#### 2. External JavaScript (file terpisah)
```html
<!DOCTYPE html>
<html>
<head>
    <title>External JavaScript</title>
    <!-- Di bagian head -->
    <script src="script.js"></script>
</head>
<body>
    <!-- Atau di akhir body (recommended) -->
    <script src="script.js"></script>
</body>
</html>
```

#### 3. Inline JavaScript (dalam atribut HTML)
```html
<button onclick="alert('Hello!')">Klik Saya</button>
```

## 2. Variabel dalam JavaScript

### Deklarasi Variabel
JavaScript memiliki tiga cara untuk mendeklarasikan variabel:

#### 1. var (cara lama)
```javascript
var nama = "John";
var umur = 25;
```

#### 2. let (recommended untuk variabel yang bisa berubah)
```javascript
let nama = "John";
let umur = 25;
```

#### 3. const (untuk nilai yang tidak akan berubah)
```javascript
const PI = 3.14;
const NAMA_WEBSITE = "MyWeb";
```

### Aturan Penamaan Variabel
- Harus dimulai dengan huruf, underscore (_), atau dollar sign ($)
- Tidak boleh dimulai dengan angka
- Case sensitive (myVar ≠ myvar)
- Tidak boleh menggunakan kata kunci JavaScript
- Gunakan camelCase untuk penamaan (contoh: namaLengkap)

```javascript
// Valid
let nama;
let $harga;
let _nilai;
let namaLengkap;

// Tidak Valid
let 1nama;        // Dimulai dengan angka
let nama-lengkap; // Menggunakan dash
let break;        // Kata kunci JavaScript
```

## 3. Tipe Data dalam JavaScript

### 1. Number
```javascript
let angka = 42;        // Integer
let desimal = 3.14;    // Float
let negatif = -10;     // Negative number
```

### 2. String
```javascript
let nama = "John";             // Double quotes
let alamat = 'Jakarta';        // Single quotes
let pesan = `Halo ${nama}`;   // Template literal
```

### 3. Boolean
```javascript
let benar = true;
let salah = false;
```

### 4. Undefined
```javascript
let tidakDiisi;
console.log(tidakDiisi); // undefined
```

### 5. Null
```javascript
let kosong = null;
```

### 6. Object
```javascript
let orang = {
    nama: "John",
    umur: 25,
    alamat: "Jakarta"
};
```

### 7. Array
```javascript
let buah = ["Apel", "Jeruk", "Mangga"];
let angka = [1, 2, 3, 4, 5];
```

## 4. Operasi Dasar dengan Variabel

### Operasi Matematika
```javascript
let a = 10;
let b = 5;

let penjumlahan = a + b;    // 15
let pengurangan = a - b;     // 5
let perkalian = a * b;      // 50
let pembagian = a / b;      // 2
let modulus = a % b;        // 0
```

### Operasi String
```javascript
let namaDepan = "John";
let namaBelakang = "Doe";

// Concatenation
let namaLengkap = namaDepan + " " + namaBelakang;  // "John Doe"

// Template Literal
let salam = `Halo, ${namaDepan}!`;  // "Halo, John!"
```

### Type Conversion
```javascript
// String ke Number
let stringAngka = "42";
let angka = Number(stringAngka);     // 42
let angka2 = parseInt(stringAngka);  // 42
let angka3 = +stringAngka;          // 42

// Number ke String
let number = 42;
let string = String(number);         // "42"
let string2 = number.toString();     // "42"

// Ke Boolean
let boolean = Boolean(1);            // true
let boolean2 = Boolean(0);          // false
let boolean3 = Boolean("");         // false
let boolean4 = Boolean("hello");    // true
```

## 5. Praktik: Membuat Script Sederhana

### Contoh 1: Kalkulator Sederhana
```html
<!DOCTYPE html>
<html>
<head>
    <title>Kalkulator Sederhana</title>
</head>
<body>
    <h2>Kalkulator Sederhana</h2>
    <input type="number" id="angka1" placeholder="Angka pertama">
    <input type="number" id="angka2" placeholder="Angka kedua">
    <button onclick="hitung()">Hitung</button>
    <p id="hasil"></p>

    <script>
        function hitung() {
            // Mengambil nilai dari input
            let angka1 = Number(document.getElementById("angka1").value);
            let angka2 = Number(document.getElementById("angka2").value);

            // Melakukan perhitungan
            let penjumlahan = angka1 + angka2;
            let pengurangan = angka1 - angka2;
            let perkalian = angka1 * angka2;
            let pembagian = angka1 / angka2;

            // Menampilkan hasil
            let hasil = document.getElementById("hasil");
            hasil.innerHTML = `
                Penjumlahan: ${penjumlahan}<br>
                Pengurangan: ${pengurangan}<br>
                Perkalian: ${perkalian}<br>
                Pembagian: ${pembagian}
            `;
        }
    </script>
</body>
</html>
```

### Contoh 2: Form Biodata
```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Biodata</title>
</head>
<body>
    <h2>Form Biodata</h2>
    <input type="text" id="nama" placeholder="Nama">
    <input type="number" id="umur" placeholder="Umur">
    <input type="text" id="alamat" placeholder="Alamat">
    <button onclick="tampilkanBiodata()">Tampilkan</button>
    <div id="hasil"></div>

    <script>
        function tampilkanBiodata() {
            // Mengambil nilai dari input
            let nama = document.getElementById("nama").value;
            let umur = document.getElementById("umur").value;
            let alamat = document.getElementById("alamat").value;

            // Membuat object biodata
            let biodata = {
                nama: nama,
                umur: umur,
                alamat: alamat
            };

            // Menampilkan hasil
            let hasil = document.getElementById("hasil");
            hasil.innerHTML = `
                <h3>Biodata:</h3>
                <p>Nama: ${biodata.nama}</p>
                <p>Umur: ${biodata.umur} tahun</p>
                <p>Alamat: ${biodata.alamat}</p>
            `;
        }
    </script>
</body>
</html>
```

### Contoh 3: Konversi Tipe Data
```html
<!DOCTYPE html>
<html>
<head>
    <title>Konversi Tipe Data</title>
</head>
<body>
    <h2>Konversi Tipe Data</h2>
    <input type="text" id="input" placeholder="Masukkan nilai">
    <button onclick="konversi()">Konversi</button>
    <div id="hasil"></div>

    <script>
        function konversi() {
            let nilai = document.getElementById("input").value;
            
            let keNumber = Number(nilai);
            let keString = String(nilai);
            let keBoolean = Boolean(nilai);

            let hasil = document.getElementById("hasil");
            hasil.innerHTML = `
                <p>Nilai asli: ${nilai} (${typeof nilai})</p>
                <p>Ke Number: ${keNumber} (${typeof keNumber})</p>
                <p>Ke String: ${keString} (${typeof keString})</p>
                <p>Ke Boolean: ${keBoolean} (${typeof keBoolean})</p>
            `;
        }
    </script>
</body>
</html>
```

## 6. Latihan Mandiri

### Latihan 1: Kalkulator Luas dan Keliling
Buat program untuk menghitung luas dan keliling persegi panjang.

### Latihan 2: Konversi Suhu
Buat program untuk mengkonversi suhu dari Celsius ke Fahrenheit dan sebaliknya.

### Latihan 3: Data Diri
Buat program yang menyimpan dan menampilkan data diri lengkap dalam bentuk object.

## Kesimpulan
- JavaScript adalah bahasa pemrograman untuk membuat website interaktif
- Ada tiga cara menambahkan JavaScript ke HTML: internal, external, dan inline
- Variabel dapat dideklarasikan dengan var, let, atau const
- JavaScript memiliki beberapa tipe data dasar: number, string, boolean, undefined, null, object, dan array
- Konversi tipe data dapat dilakukan dengan berbagai metode

## Referensi Tambahan
- [MDN Web Docs - JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [W3Schools - JavaScript Tutorial](https://www.w3schools.com/js/)
- [JavaScript.info](https://javascript.info/)
- [Eloquent JavaScript](https://eloquentjavascript.net/)