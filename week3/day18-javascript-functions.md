# Hari 18: Function (membuat dan memanggil)

## Tujuan Pembelajaran
- Memahami konsep function dalam JavaScript
- Mengenal berbagai cara deklarasi function
- Memahami parameter dan return value
- Mengenal scope dan closure
- Membuat function untuk tombol counter

## 1. Pengenalan Function

### Apa itu Function?
Function adalah blok kode yang dapat digunakan kembali untuk melakukan tugas tertentu. Function membantu mengorganisir kode dan menerapkan prinsip DRY (Don't Repeat Yourself).

### Cara Mendeklarasikan Function

#### 1. Function Declaration
```javascript
function namaFunction(parameter1, parameter2) {
    // kode function
    return hasil;
}
```

#### 2. Function Expression
```javascript
const namaFunction = function(parameter1, parameter2) {
    // kode function
    return hasil;
};
```

#### 3. Arrow Function (ES6)
```javascript
const namaFunction = (parameter1, parameter2) => {
    // kode function
    return hasil;
};
```

## 2. Parameter dan Return Value

### Parameter
Parameter adalah nilai yang dikirim ke function.

```javascript
function sapa(nama) {
    console.log(`Halo, ${nama}!`);
}

sapa("John"); // Output: Halo, John!
```

### Default Parameter
```javascript
function sapa(nama = "Tamu") {
    console.log(`Halo, ${nama}!`);
}

sapa(); // Output: Halo, Tamu!
sapa("John"); // Output: Halo, John!
```

### Return Value
Return value adalah nilai yang dikembalikan oleh function.

```javascript
function tambah(a, b) {
    return a + b;
}

let hasil = tambah(5, 3); // hasil = 8
```

### Multiple Parameters
```javascript
function hitungVolume(panjang, lebar, tinggi) {
    return panjang * lebar * tinggi;
}

let volume = hitungVolume(3, 4, 5); // volume = 60
```

## 3. Scope dan Closure

### Global Scope
Variabel yang dideklarasikan di luar function.

```javascript
let globalVar = "Saya global";

function tampilGlobal() {
    console.log(globalVar); // Bisa mengakses globalVar
}
```

### Local Scope
Variabel yang dideklarasikan di dalam function.

```javascript
function tampilLocal() {
    let localVar = "Saya local";
    console.log(localVar); // Bisa mengakses localVar
}

// console.log(localVar); // Error: localVar is not defined
```

### Closure
Function yang memiliki akses ke variabel di scope parent-nya.

```javascript
function createCounter() {
    let count = 0;
    return function() {
        return ++count;
    };
}

const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

## 4. Praktik: Membuat Counter Button

### Contoh 1: Simple Counter
```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Counter</title>
    <style>
        .counter {
            text-align: center;
            margin: 50px;
        }
        .count {
            font-size: 48px;
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 0 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="counter">
        <div class="count" id="count">0</div>
        <button onclick="decrement()">-</button>
        <button onclick="increment()">+</button>
        <button onclick="reset()">Reset</button>
    </div>

    <script>
        let count = 0;
        const countDisplay = document.getElementById("count");

        function updateDisplay() {
            countDisplay.textContent = count;
        }

        function increment() {
            count++;
            updateDisplay();
        }

        function decrement() {
            count--;
            updateDisplay();
        }

        function reset() {
            count = 0;
            updateDisplay();
        }
    </script>
</body>
</html>
```

### Contoh 2: Advanced Counter dengan Closure
```html
<!DOCTYPE html>
<html>
<head>
    <title>Advanced Counter</title>
    <style>
        .counter {
            text-align: center;
            margin: 50px;
        }
        .count {
            font-size: 48px;
            margin: 20px;
        }
        .controls {
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 0 5px;
            cursor: pointer;
        }
        .history {
            margin-top: 20px;
            font-size: 14px;
            color: #666;
        }
    </style>
</head>
<body>
    <div class="counter">
        <div class="count" id="count">0</div>
        <div class="controls">
            <button onclick="counter.decrement()">-</button>
            <button onclick="counter.increment()">+</button>
            <button onclick="counter.reset()">Reset</button>
        </div>
        <input type="number" id="stepInput" value="1" min="1" max="10">
        <div class="history" id="history"></div>
    </div>

    <script>
        const createCounter = () => {
            let count = 0;
            let history = [];

            const updateDisplay = () => {
                document.getElementById("count").textContent = count;
                updateHistory();
            };

            const updateHistory = () => {
                const historyElement = document.getElementById("history");
                historyElement.innerHTML = history
                    .slice(-5)
                    .map(action => `<div>${action}</div>`)
                    .join("");
            };

            const getStep = () => {
                return parseInt(document.getElementById("stepInput").value) || 1;
            };

            return {
                increment: () => {
                    const step = getStep();
                    count += step;
                    history.push(`Added ${step}`);
                    updateDisplay();
                },
                decrement: () => {
                    const step = getStep();
                    count -= step;
                    history.push(`Subtracted ${step}`);
                    updateDisplay();
                },
                reset: () => {
                    count = 0;
                    history.push("Reset to 0");
                    updateDisplay();
                }
            };
        };

        const counter = createCounter();
    </script>
</body>
</html>
```

### Contoh 3: Multiple Counters
```html
<!DOCTYPE html>
<html>
<head>
    <title>Multiple Counters</title>
    <style>
        .counters {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            padding: 20px;
        }
        .counter {
            border: 1px solid #ddd;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
        }
        .count {
            font-size: 36px;
            margin: 10px;
        }
        button {
            padding: 5px 10px;
            margin: 0 3px;
        }
        .add-counter {
            margin: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="add-counter">
        <button onclick="addCounter()">Add New Counter</button>
    </div>
    <div class="counters" id="counters"></div>

    <script>
        function createCounter(id) {
            const counterElement = document.createElement("div");
            counterElement.className = "counter";
            
            let count = 0;
            
            const updateDisplay = () => {
                countDisplay.textContent = count;
            };
            
            counterElement.innerHTML = `
                <div class="count">0</div>
                <button onclick="this.parentElement.decrement()">-</button>
                <button onclick="this.parentElement.increment()">+</button>
                <button onclick="this.parentElement.reset()">Reset</button>
                <button onclick="this.parentElement.remove()">Delete</button>
            `;
            
            const countDisplay = counterElement.querySelector(".count");
            
            counterElement.increment = () => {
                count++;
                updateDisplay();
            };
            
            counterElement.decrement = () => {
                count--;
                updateDisplay();
            };
            
            counterElement.reset = () => {
                count = 0;
                updateDisplay();
            };
            
            return counterElement;
        }

        function addCounter() {
            const countersContainer = document.getElementById("counters");
            const newCounter = createCounter(countersContainer.children.length + 1);
            countersContainer.appendChild(newCounter);
        }

        // Add initial counter
        addCounter();
    </script>
</body>
</html>
```

## 5. Function Callbacks

### Apa itu Callback?
Callback adalah function yang dikirim sebagai parameter ke function lain.

```javascript
function prosesData(data, callback) {
    // Proses data
    const hasil = data.toUpperCase();
    // Panggil callback dengan hasil
    callback(hasil);
}

function tampilHasil(hasil) {
    console.log(hasil);
}

prosesData("hello", tampilHasil); // Output: HELLO
```

### Event Listeners dengan Callback
```javascript
button.addEventListener("click", function() {
    console.log("Button clicked!");
});
```

## 6. Latihan Mandiri

### Latihan 1: Calculator Function
Buat kalkulator dengan fungsi-fungsi dasar (tambah, kurang, kali, bagi).

### Latihan 2: Timer Counter
Buat counter yang berjalan otomatis dengan interval waktu tertentu.

### Latihan 3: Score Keeper
Buat aplikasi pencatat skor untuk permainan dengan multiple pemain.

## Kesimpulan
- Function adalah blok kode yang dapat digunakan kembali
- Ada beberapa cara untuk mendeklarasikan function
- Parameter dan return value memungkinkan function menerima input dan mengembalikan output
- Scope menentukan akses ke variabel
- Closure memungkinkan function mengakses variabel dari scope parent
- Callback memungkinkan function dipanggil dari function lain

## Referensi Tambahan
- [MDN Web Docs - Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
- [JavaScript.info - Functions](https://javascript.info/function-basics)
- [W3Schools - JavaScript Functions](https://www.w3schools.com/js/js_functions.asp)
- [Eloquent JavaScript - Functions](https://eloquentjavascript.net/03_functions.html)