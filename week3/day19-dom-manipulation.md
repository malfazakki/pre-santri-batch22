# Hari 19: DOM Manipulation (getElementById, innerText)

## Tujuan Pembelajaran
- Memahami konsep Document Object Model (DOM)
- Mengenal cara mengakses elemen HTML dengan JavaScript
- Memahami penggunaan getElementById dan metode serupa
- Memanipulasi konten dengan innerText dan innerHTML
- Mengubah isi halaman menggunakan JavaScript

## 1. Pengenalan DOM

### Apa itu DOM?
DOM (Document Object Model) adalah representasi terstruktur dari dokumen HTML sebagai pohon objek yang dapat dimanipulasi dengan JavaScript.

### Struktur DOM
```plaintext
document
  └── html
      ├── head
      │   ├── title
      │   └── meta
      └── body
          ├── div
          │   ├── h1
          │   └── p
          └── div
              └── form
```

## 2. Mengakses Elemen DOM

### getElementById
Mengakses elemen berdasarkan ID-nya.

```html
<div id="myDiv">Hello World</div>

<script>
const element = document.getElementById("myDiv");
console.log(element); // <div id="myDiv">Hello World</div>
</script>
```

### Metode Akses Lainnya
```javascript
// Mengakses berdasarkan class
const elements = document.getElementsByClassName("myClass");

// Mengakses berdasarkan tag name
const paragraphs = document.getElementsByTagName("p");

// Mengakses dengan querySelector (CSS selector)
const element = document.querySelector("#myDiv");
const elements = document.querySelectorAll(".myClass");
```

## 3. Memanipulasi Konten

### innerText
Mengubah atau mengakses konten teks dari elemen.

```html
<div id="myDiv">Original Text</div>

<script>
const div = document.getElementById("myDiv");

// Membaca teks
console.log(div.innerText); // "Original Text"

// Mengubah teks
div.innerText = "New Text";
</script>
```

### innerHTML
Mengubah atau mengakses konten HTML dari elemen.

```html
<div id="myDiv">
    <span>Original Content</span>
</div>

<script>
const div = document.getElementById("myDiv");

// Membaca HTML
console.log(div.innerHTML); // "<span>Original Content</span>"

// Mengubah HTML
div.innerHTML = "<strong>New Content</strong>";
</script>
```

## 4. Praktik: Manipulasi DOM

### Contoh 1: Text Editor Sederhana
```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Text Editor</title>
    <style>
        .editor-container {
            margin: 20px;
            padding: 20px;
            border: 1px solid #ddd;
        }
        .preview {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            min-height: 100px;
        }
        button {
            margin: 5px;
            padding: 5px 10px;
        }
    </style>
</head>
<body>
    <div class="editor-container">
        <textarea id="editor" rows="5" cols="50"></textarea>
        <div>
            <button onclick="updatePreview()">Update Preview</button>
            <button onclick="clearText()">Clear</button>
        </div>
        <div id="preview" class="preview"></div>
    </div>

    <script>
        function updatePreview() {
            const editor = document.getElementById("editor");
            const preview = document.getElementById("preview");
            preview.innerText = editor.value;
        }

        function clearText() {
            const editor = document.getElementById("editor");
            const preview = document.getElementById("preview");
            editor.value = "";
            preview.innerText = "";
        }
    </script>
</body>
</html>
```

### Contoh 2: Dynamic Content Updater
```html
<!DOCTYPE html>
<html>
<head>
    <title>Dynamic Content Updater</title>
    <style>
        .container {
            margin: 20px;
            padding: 20px;
            border: 1px solid #ddd;
        }
        .content-box {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
        }
        .controls {
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="controls">
            <input type="text" id="titleInput" placeholder="Enter title">
            <button onclick="updateTitle()">Update Title</button>
        </div>
        <div class="controls">
            <textarea id="contentInput" placeholder="Enter content"></textarea>
            <button onclick="updateContent()">Update Content</button>
        </div>
        <div class="content-box">
            <h2 id="titleDisplay">Default Title</h2>
            <p id="contentDisplay">Default Content</p>
        </div>
    </div>

    <script>
        function updateTitle() {
            const titleInput = document.getElementById("titleInput");
            const titleDisplay = document.getElementById("titleDisplay");
            titleDisplay.innerText = titleInput.value || "Default Title";
            titleInput.value = "";
        }

        function updateContent() {
            const contentInput = document.getElementById("contentInput");
            const contentDisplay = document.getElementById("contentDisplay");
            contentDisplay.innerText = contentInput.value || "Default Content";
            contentInput.value = "";
        }
    </script>
</body>
</html>
```

### Contoh 3: Interactive List Manager
```html
<!DOCTYPE html>
<html>
<head>
    <title>Interactive List Manager</title>
    <style>
        .container {
            margin: 20px;
            padding: 20px;
            border: 1px solid #ddd;
        }
        .list-container {
            margin-top: 20px;
        }
        .list-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            margin: 5px 0;
            background-color: #f5f5f5;
        }
        .controls {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="controls">
            <input type="text" id="itemInput" placeholder="Enter item">
            <button onclick="addItem()">Add Item</button>
        </div>
        <div id="listContainer" class="list-container"></div>
    </div>

    <script>
        function addItem() {
            const input = document.getElementById("itemInput");
            const container = document.getElementById("listContainer");
            
            if (input.value.trim() !== "") {
                const itemDiv = document.createElement("div");
                itemDiv.className = "list-item";
                
                const textSpan = document.createElement("span");
                textSpan.innerText = input.value;
                
                const deleteButton = document.createElement("button");
                deleteButton.innerText = "Delete";
                deleteButton.onclick = function() {
                    container.removeChild(itemDiv);
                };
                
                itemDiv.appendChild(textSpan);
                itemDiv.appendChild(deleteButton);
                container.appendChild(itemDiv);
                
                input.value = "";
            }
        }
    </script>
</body>
</html>
```

### Contoh 4: Real-time Form Validation
```html
<!DOCTYPE html>
<html>
<head>
    <title>Real-time Form Validation</title>
    <style>
        .container {
            margin: 20px;
            padding: 20px;
            border: 1px solid #ddd;
        }
        .form-group {
            margin-bottom: 15px;
        }
        .error {
            color: red;
            font-size: 12px;
            display: none;
        }
        .success {
            color: green;
            font-size: 12px;
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <form id="validationForm" onsubmit="return validateForm(event)">
            <div class="form-group">
                <label for="username">Username:</label>
                <input type="text" id="username" onkeyup="validateUsername()">
                <span id="usernameError" class="error">Username must be at least 3 characters</span>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" onkeyup="validateEmail()">
                <span id="emailError" class="error">Please enter a valid email</span>
            </div>
            <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" id="password" onkeyup="validatePassword()">
                <span id="passwordError" class="error">Password must be at least 6 characters</span>
            </div>
            <button type="submit">Submit</button>
            <span id="submitSuccess" class="success">Form submitted successfully!</span>
        </form>
    </div>

    <script>
        function validateUsername() {
            const username = document.getElementById("username");
            const error = document.getElementById("usernameError");
            
            if (username.value.length < 3) {
                error.style.display = "block";
                return false;
            } else {
                error.style.display = "none";
                return true;
            }
        }

        function validateEmail() {
            const email = document.getElementById("email");
            const error = document.getElementById("emailError");
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            
            if (!emailRegex.test(email.value)) {
                error.style.display = "block";
                return false;
            } else {
                error.style.display = "none";
                return true;
            }
        }

        function validatePassword() {
            const password = document.getElementById("password");
            const error = document.getElementById("passwordError");
            
            if (password.value.length < 6) {
                error.style.display = "block";
                return false;
            } else {
                error.style.display = "none";
                return true;
            }
        }

        function validateForm(event) {
            event.preventDefault();
            
            const isUsernameValid = validateUsername();
            const isEmailValid = validateEmail();
            const isPasswordValid = validatePassword();
            
            if (isUsernameValid && isEmailValid && isPasswordValid) {
                const success = document.getElementById("submitSuccess");
                success.style.display = "block";
                setTimeout(() => {
                    success.style.display = "none";
                }, 3000);
                return true;
            }
            
            return false;
        }
    </script>
</body>
</html>
```

## 5. Latihan Mandiri

### Latihan 1: Note Taking App
Buat aplikasi pencatat sederhana dengan fitur:
- Input teks
- Tombol tambah catatan
- Daftar catatan yang bisa dihapus

### Latihan 2: Dynamic Table Generator
Buat generator tabel dengan fitur:
- Input jumlah baris dan kolom
- Tombol generate tabel
- Hasil tabel dengan border

### Latihan 3: Form Data Display
Buat form yang menampilkan data secara real-time:
- Input fields (nama, email, dll)
- Preview data saat diketik
- Tombol reset form

## Kesimpulan
- DOM memungkinkan JavaScript mengakses dan memanipulasi elemen HTML
- getElementById adalah metode umum untuk mengakses elemen
- innerText dan innerHTML digunakan untuk memanipulasi konten
- DOM manipulation sangat penting untuk membuat website interaktif
- Kombinasi event handling dan DOM manipulation membuat UI dinamis

## Referensi Tambahan
- [MDN Web Docs - DOM Introduction](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [W3Schools - JavaScript HTML DOM](https://www.w3schools.com/js/js_htmldom.asp)
- [JavaScript.info - Document](https://javascript.info/document)
- [DOM Enlightenment](http://domenlightenment.com/)