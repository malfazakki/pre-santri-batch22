# Hari 20: DOM Class & Style Manipulation

## Tujuan Pembelajaran
- Memahami cara memanipulasi class dengan JavaScript
- Mengenal cara mengubah style langsung melalui JavaScript
- Memahami penggunaan classList API
- Membuat animasi dengan CSS dan JavaScript
- Menerapkan perubahan style untuk efek visual

## 1. Manipulasi Class

### classList API
classList menyediakan metode untuk memanipulasi class elemen.

```javascript
// Mengakses elemen
const element = document.getElementById("myElement");

// Menambah class
element.classList.add("active");

// Menghapus class
element.classList.remove("active");

// Toggle class (menambah jika tidak ada, menghapus jika ada)
element.classList.toggle("active");

// Mengecek keberadaan class
const hasClass = element.classList.contains("active");

// Mengganti satu class dengan class lain
element.classList.replace("old-class", "new-class");
```

### className Property
Alternatif klasik untuk memanipulasi class.

```javascript
// Mengatur class
element.className = "class1 class2";

// Menambah class
element.className += " class3";
```

## 2. Manipulasi Style

### Style Property
Mengubah style langsung melalui JavaScript.

```javascript
const element = document.getElementById("myElement");

// Mengatur single style
element.style.backgroundColor = "red";
element.style.fontSize = "16px";
element.style.marginTop = "20px";

// Mengatur multiple styles
Object.assign(element.style, {
    backgroundColor: "blue",
    color: "white",
    padding: "10px"
});
```

### getComputedStyle
Mendapatkan style yang sedang diterapkan pada elemen.

```javascript
const element = document.getElementById("myElement");
const styles = window.getComputedStyle(element);

console.log(styles.backgroundColor);
console.log(styles.fontSize);
```

## 3. Praktik: Animasi dan Transisi

### Contoh 1: Toggle Menu dengan Animasi
```html
<!DOCTYPE html>
<html>
<head>
    <title>Animated Menu Toggle</title>
    <style>
        .menu {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }

        .menu.active {
            max-height: 200px;
        }

        .menu-item {
            padding: 10px;
            background-color: #f0f0f0;
            margin: 5px 0;
        }

        .toggle-btn {
            padding: 10px;
            background-color: #333;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <button class="toggle-btn" onclick="toggleMenu()">Toggle Menu</button>
    <div id="menu" class="menu">
        <div class="menu-item">Item 1</div>
        <div class="menu-item">Item 2</div>
        <div class="menu-item">Item 3</div>
    </div>

    <script>
        function toggleMenu() {
            const menu = document.getElementById("menu");
            menu.classList.toggle("active");
        }
    </script>
</body>
</html>
```

### Contoh 2: Fade Effect
```html
<!DOCTYPE html>
<html>
<head>
    <title>Fade Effect</title>
    <style>
        .fade-element {
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
        }

        .fade-element.visible {
            opacity: 1;
        }

        .box {
            width: 200px;
            height: 200px;
            background-color: #4CAF50;
            margin: 20px;
        }
    </style>
</head>
<body>
    <button onclick="toggleFade()">Toggle Fade</button>
    <div id="box" class="box fade-element"></div>

    <script>
        function toggleFade() {
            const box = document.getElementById("box");
            box.classList.toggle("visible");
        }
    </script>
</body>
</html>
```

### Contoh 3: Slide Animation
```html
<!DOCTYPE html>
<html>
<head>
    <title>Slide Animation</title>
    <style>
        .slide-container {
            overflow: hidden;
        }

        .slide-element {
            transform: translateX(-100%);
            transition: transform 0.3s ease-in-out;
            padding: 20px;
            background-color: #f0f0f0;
        }

        .slide-element.active {
            transform: translateX(0);
        }
    </style>
</head>
<body>
    <button onclick="toggleSlide()">Toggle Slide</button>
    <div class="slide-container">
        <div id="slideContent" class="slide-element">
            <h2>Sliding Content</h2>
            <p>This content slides in and out.</p>
        </div>
    </div>

    <script>
        function toggleSlide() {
            const content = document.getElementById("slideContent");
            content.classList.toggle("active");
        }
    </script>
</body>
</html>
```

### Contoh 4: Advanced Animation with Multiple States
```html
<!DOCTYPE html>
<html>
<head>
    <title>Advanced Animation</title>
    <style>
        .animation-box {
            width: 100px;
            height: 100px;
            background-color: #4CAF50;
            transition: all 0.3s ease-in-out;
            margin: 20px;
        }

        .animation-box.state-1 {
            transform: scale(1.5);
            background-color: #2196F3;
        }

        .animation-box.state-2 {
            transform: rotate(45deg);
            background-color: #f44336;
        }

        .animation-box.state-3 {
            transform: translate(100px, 0) rotate(90deg);
            background-color: #9c27b0;
        }

        .controls {
            margin: 20px;
        }
    </style>
</head>
<body>
    <div class="controls">
        <button onclick="changeState(0)">Reset</button>
        <button onclick="changeState(1)">State 1</button>
        <button onclick="changeState(2)">State 2</button>
        <button onclick="changeState(3)">State 3</button>
    </div>
    <div id="animationBox" class="animation-box"></div>

    <script>
        function changeState(state) {
            const box = document.getElementById("animationBox");
            
            // Remove all states
            box.classList.remove("state-1", "state-2", "state-3");
            
            // Add new state if not reset
            if (state > 0) {
                box.classList.add(`state-${state}`);
            }
        }
    </script>
</body>
</html>
```

### Contoh 5: Interactive Card Flip
```html
<!DOCTYPE html>
<html>
<head>
    <title>Card Flip</title>
    <style>
        .card-container {
            perspective: 1000px;
            width: 300px;
            height: 200px;
            margin: 50px auto;
        }

        .card {
            position: relative;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: transform 0.6s;
            cursor: pointer;
        }

        .card.flipped {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            border-radius: 10px;
        }

        .card-front {
            background-color: #2196F3;
            color: white;
        }

        .card-back {
            background-color: #4CAF50;
            color: white;
            transform: rotateY(180deg);
        }
    </style>
</head>
<body>
    <div class="card-container">
        <div id="card" class="card" onclick="flipCard()">
            <div class="card-front">Front</div>
            <div class="card-back">Back</div>
        </div>
    </div>

    <script>
        function flipCard() {
            const card = document.getElementById("card");
            card.classList.toggle("flipped");
        }
    </script>
</body>
</html>
```

## 4. Praktik: Style Manipulation untuk UI Interaktif

### Contoh: Interactive Button States
```html
<!DOCTYPE html>
<html>
<head>
    <title>Interactive Button</title>
    <style>
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-primary {
            background-color: #4CAF50;
            color: white;
        }

        .btn-primary:hover {
            background-color: #45a049;
            transform: translateY(-2px);
        }

        .btn-loading {
            opacity: 0.7;
            cursor: wait;
        }

        .btn-success {
            background-color: #2196F3;
        }

        .loading-spinner {
            display: none;
            width: 20px;
            height: 20px;
            border: 2px solid #fff;
            border-radius: 50%;
            border-top-color: transparent;
            animation: spin 1s linear infinite;
            margin-left: 10px;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <button id="actionButton" class="btn btn-primary" onclick="handleClick()">
        <span id="buttonText">Click Me</span>
        <span id="spinner" class="loading-spinner"></span>
    </button>

    <script>
        function handleClick() {
            const button = document.getElementById("actionButton");
            const buttonText = document.getElementById("buttonText");
            const spinner = document.getElementById("spinner");

            // Loading state
            button.classList.add("btn-loading");
            buttonText.textContent = "Loading...";
            spinner.style.display = "inline-block";
            button.disabled = true;

            // Simulate loading
            setTimeout(() => {
                // Success state
                button.classList.remove("btn-loading");
                button.classList.add("btn-success");
                buttonText.textContent = "Success!";
                spinner.style.display = "none";
                
                // Reset after 2 seconds
                setTimeout(() => {
                    button.classList.remove("btn-success");
                    buttonText.textContent = "Click Me";
                    button.disabled = false;
                }, 2000);
            }, 2000);
        }
    </script>
</body>
</html>
```

## 5. Latihan Mandiri

### Latihan 1: Accordion Menu
Buat menu accordion dengan animasi slide:
- Multiple sections yang bisa dibuka/tutup
- Animasi smooth saat membuka/menutup
- Indikator status (terbuka/tertutup)

### Latihan 2: Image Gallery
Buat galeri gambar dengan efek hover:
- Grid gambar
- Efek zoom saat hover
- Overlay text saat hover

### Latihan 3: Notification System
Buat sistem notifikasi dengan animasi:
- Notifikasi muncul dari atas/samping
- Fade out setelah beberapa detik
- Different styles untuk success/error/warning

## Kesimpulan
- classList API menyediakan cara mudah untuk memanipulasi class
- Style dapat diubah langsung melalui JavaScript
- CSS transitions dan animations dapat dikontrol dengan JavaScript
- Kombinasi CSS dan JavaScript membuat UI lebih interaktif
- Perubahan style yang baik meningkatkan UX

## Referensi Tambahan
- [MDN Web Docs - Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
- [CSS-Tricks - A Complete Guide to CSS Transitions](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [JavaScript.info - Styles and Classes](https://javascript.info/styles-and-classes)
- [W3Schools - HTML DOM Style Object](https://www.w3schools.com/jsref/dom_obj_style.asp)