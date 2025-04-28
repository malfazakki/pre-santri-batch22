# Hari 16: Kondisional (if, else) & Event Handling (click)

## Tujuan Pembelajaran
- Memahami konsep kondisional dalam JavaScript
- Mengenal berbagai jenis statement kondisional
- Memahami dasar-dasar event handling
- Membuat interaksi button dengan event click
- Membuat elemen interaktif show/hide

## 1. Kondisional dalam JavaScript

### If Statement
Statement if digunakan untuk menjalankan kode jika kondisi tertentu terpenuhi (true).

```javascript
if (kondisi) {
    // kode yang dijalankan jika kondisi true
}
```

Contoh:
```javascript
let umur = 18;

if (umur >= 17) {
    console.log("Anda sudah bisa membuat SIM");
}
```

### If...Else Statement
Menambahkan alternatif jika kondisi tidak terpenuhi (false).

```javascript
if (kondisi) {
    // kode jika kondisi true
} else {
    // kode jika kondisi false
}
```

Contoh:
```javascript
let nilai = 75;

if (nilai >= 70) {
    console.log("Anda lulus!");
} else {
    console.log("Anda perlu remedial");
}
```

### If...Else If...Else Statement
Untuk multiple kondisi.

```javascript
if (kondisi1) {
    // kode jika kondisi1 true
} else if (kondisi2) {
    // kode jika kondisi2 true
} else {
    // kode jika semua kondisi false
}
```

Contoh:
```javascript
let nilai = 85;

if (nilai >= 90) {
    console.log("Grade A");
} else if (nilai >= 80) {
    console.log("Grade B");
} else if (nilai >= 70) {
    console.log("Grade C");
} else {
    console.log("Grade D");
}
```

### Operator Perbandingan
- `==` : Sama dengan (nilai)
- `===` : Sama dengan (nilai dan tipe data)
- `!=` : Tidak sama dengan (nilai)
- `!==` : Tidak sama dengan (nilai dan tipe data)
- `>` : Lebih besar dari
- `<` : Lebih kecil dari
- `>=` : Lebih besar atau sama dengan
- `<=` : Lebih kecil atau sama dengan

```javascript
let x = 5;
let y = "5";

console.log(x == y);   // true (nilai sama)
console.log(x === y);  // false (tipe data berbeda)
```

### Operator Logika
- `&&` : AND (dan)
- `||` : OR (atau)
- `!` : NOT (tidak)

```javascript
let umur = 25;
let memilikiKTP = true;

if (umur >= 17 && memilikiKTP) {
    console.log("Boleh membuat SIM");
}

if (umur < 13 || umur > 65) {
    console.log("Tidak boleh masuk wahana ini");
}

if (!memilikiKTP) {
    console.log("Silakan buat KTP terlebih dahulu");
}
```

## 2. Event Handling

### Apa itu Event?
Event adalah aksi yang terjadi di halaman web, seperti:
- Click
- Mouse hover
- Keyboard press
- Form submit
- Page load
- Dan lain-lain

### Cara Menangani Event

#### 1. HTML Event Attributes
```html
<button onclick="alert('Hello!')">Klik Saya</button>
```

#### 2. DOM Element Properties
```javascript
let button = document.getElementById("myButton");
button.onclick = function() {
    alert("Hello!");
}
```

#### 3. addEventListener Method (Recommended)
```javascript
let button = document.getElementById("myButton");
button.addEventListener("click", function() {
    alert("Hello!");
});
```

### Jenis-jenis Event Umum
- `click`: Saat elemen diklik
- `dblclick`: Saat elemen diklik dua kali
- `mouseover`: Saat mouse di atas elemen
- `mouseout`: Saat mouse keluar dari elemen
- `keydown`: Saat tombol keyboard ditekan
- `keyup`: Saat tombol keyboard dilepas
- `submit`: Saat form disubmit
- `change`: Saat nilai input berubah
- `load`: Saat halaman selesai dimuat

## 3. Praktik: Button Interaktif

### Contoh 1: Show/Hide Text
```html
<!DOCTYPE html>
<html>
<head>
    <title>Show/Hide Text</title>
    <style>
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <button id="toggleButton">Toggle Text</button>
    <p id="text">Ini adalah teks yang bisa disembunyikan!</p>

    <script>
        const button = document.getElementById("toggleButton");
        const text = document.getElementById("text");

        button.addEventListener("click", function() {
            if (text.classList.contains("hidden")) {
                text.classList.remove("hidden");
                button.textContent = "Hide Text";
            } else {
                text.classList.add("hidden");
                button.textContent = "Show Text";
            }
        });
    </script>
</body>
</html>
```

### Contoh 2: Toggle Password Visibility
```html
<!DOCTYPE html>
<html>
<head>
    <title>Password Toggle</title>
</head>
<body>
    <div>
        <input type="password" id="password" placeholder="Masukkan password">
        <button id="togglePassword">Show Password</button>
    </div>

    <script>
        const passwordInput = document.getElementById("password");
        const toggleButton = document.getElementById("togglePassword");

        toggleButton.addEventListener("click", function() {
            if (passwordInput.type === "password") {
                passwordInput.type = "text";
                toggleButton.textContent = "Hide Password";
            } else {
                passwordInput.type = "password";
                toggleButton.textContent = "Show Password";
            }
        });
    </script>
</body>
</html>
```

### Contoh 3: Interactive Form Validation
```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Validation</title>
    <style>
        .error {
            color: red;
            display: none;
        }
        .success {
            color: green;
            display: none;
        }
    </style>
</head>
<body>
    <form id="myForm">
        <div>
            <label for="username">Username:</label>
            <input type="text" id="username" required>
            <span id="usernameError" class="error">Username harus diisi!</span>
        </div>
        <div>
            <label for="age">Umur:</label>
            <input type="number" id="age" required>
            <span id="ageError" class="error">Umur harus minimal 17 tahun!</span>
        </div>
        <button type="submit">Submit</button>
        <p id="success" class="success">Form berhasil disubmit!</p>
    </form>

    <script>
        const form = document.getElementById("myForm");
        const usernameInput = document.getElementById("username");
        const ageInput = document.getElementById("age");
        const usernameError = document.getElementById("usernameError");
        const ageError = document.getElementById("ageError");
        const success = document.getElementById("success");

        form.addEventListener("submit", function(event) {
            event.preventDefault();
            let isValid = true;

            // Username validation
            if (usernameInput.value.trim() === "") {
                usernameError.style.display = "block";
                isValid = false;
            } else {
                usernameError.style.display = "none";
            }

            // Age validation
            if (ageInput.value < 17) {
                ageError.style.display = "block";
                isValid = false;
            } else {
                ageError.style.display = "none";
            }

            // Show success message if valid
            if (isValid) {
                success.style.display = "block";
                form.reset();
            } else {
                success.style.display = "none";
            }
        });
    </script>
</body>
</html>
```

### Contoh 4: Interactive Color Changer
```html
<!DOCTYPE html>
<html>
<head>
    <title>Color Changer</title>
    <style>
        .box {
            width: 200px;
            height: 200px;
            border: 2px solid black;
            margin: 20px;
        }
    </style>
</head>
<body>
    <div class="box" id="colorBox"></div>
    <button onclick="changeColor('red')">Red</button>
    <button onclick="changeColor('green')">Green</button>
    <button onclick="changeColor('blue')">Blue</button>
    <button onclick="changeRandomColor()">Random</button>

    <script>
        const box = document.getElementById("colorBox");

        function changeColor(color) {
            box.style.backgroundColor = color;
        }

        function changeRandomColor() {
            const randomColor = '#' + Math.floor(Math.random()*16777215).toString(16);
            box.style.backgroundColor = randomColor;
        }
    </script>
</body>
</html>
```

## 4. Latihan Mandiri

### Latihan 1: Toggle Menu
Buat menu yang bisa ditampilkan/disembunyikan dengan tombol hamburger.

### Latihan 2: Form Validation
Buat form dengan validasi untuk:
- Email harus valid
- Password minimal 8 karakter
- Konfirmasi password harus sama

### Latihan 3: Interactive Quiz
Buat kuis sederhana dengan:
- Beberapa pertanyaan pilihan ganda
- Validasi jawaban
- Menampilkan skor akhir

## Kesimpulan
- Kondisional memungkinkan program mengambil keputusan berdasarkan kondisi
- Event handling membuat website menjadi interaktif
- Kombinasi kondisional dan event handling sangat penting dalam membuat UI yang dinamis
- Validasi form adalah salah satu penggunaan umum dari kondisional dan event handling
- Event listener adalah cara modern untuk menangani event

## Referensi Tambahan
- [MDN Web Docs - Conditional Statements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)
- [MDN Web Docs - Introduction to Events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [JavaScript.info - Conditional Branching](https://javascript.info/ifelse)
- [W3Schools - JavaScript Events](https://www.w3schools.com/js/js_events.asp)