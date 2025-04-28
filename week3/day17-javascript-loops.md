# Hari 17: Looping (for, while)

## Tujuan Pembelajaran
- Memahami konsep perulangan (loop) dalam JavaScript
- Mengenal berbagai jenis loop: for, while, do...while
- Memahami penggunaan break dan continue
- Menerapkan loop untuk array dan object
- Mencetak daftar item ke halaman HTML

## 1. Pengenalan Loop

### Apa itu Loop?
Loop adalah struktur kontrol yang memungkinkan kita menjalankan blok kode berulang kali berdasarkan kondisi tertentu.

### Mengapa Menggunakan Loop?
- Mengotomatisasi tugas berulang
- Memproses array atau collection data
- Mengiterasi melalui object
- Membuat pola atau struktur berulang

## 2. Jenis-jenis Loop

### For Loop
Loop yang paling umum digunakan ketika kita tahu berapa kali kita ingin mengulangi sesuatu.

```javascript
for (inisialisasi; kondisi; increment/decrement) {
    // kode yang akan diulang
}
```

Contoh:
```javascript
// Menghitung 1-5
for (let i = 1; i <= 5; i++) {
    console.log(i);
}

// Output:
// 1
// 2
// 3
// 4
// 5
```

### While Loop
Digunakan ketika kita tidak tahu pasti berapa kali loop akan berjalan.

```javascript
while (kondisi) {
    // kode yang akan diulang
}
```

Contoh:
```javascript
let count = 1;
while (count <= 5) {
    console.log(count);
    count++;
}
```

### Do...While Loop
Mirip dengan while loop, tetapi selalu menjalankan kode minimal satu kali.

```javascript
do {
    // kode yang akan diulang
} while (kondisi);
```

Contoh:
```javascript
let count = 1;
do {
    console.log(count);
    count++;
} while (count <= 5);
```

### For...of Loop
Digunakan untuk mengiterasi array atau iterable objects.

```javascript
for (let item of array) {
    // kode yang akan diulang
}
```

Contoh:
```javascript
const buah = ["Apel", "Jeruk", "Mangga"];
for (let item of buah) {
    console.log(item);
}
```

### For...in Loop
Digunakan untuk mengiterasi properti object.

```javascript
for (let key in object) {
    // kode yang akan diulang
}
```

Contoh:
```javascript
const orang = {
    nama: "John",
    umur: 30,
    pekerjaan: "Developer"
};

for (let key in orang) {
    console.log(`${key}: ${orang[key]}`);
}
```

## 3. Break dan Continue

### Break
Menghentikan loop secara keseluruhan.

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        break;
    }
    console.log(i);
}
// Output: 1, 2
```

### Continue
Melanjutkan ke iterasi berikutnya.

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue;
    }
    console.log(i);
}
// Output: 1, 2, 4, 5
```

## 4. Praktik: Mencetak Daftar ke HTML

### Contoh 1: Daftar Sederhana
```html
<!DOCTYPE html>
<html>
<head>
    <title>Daftar Sederhana</title>
</head>
<body>
    <h2>Daftar Buah</h2>
    <ul id="daftarBuah"></ul>

    <script>
        const buah = ["Apel", "Jeruk", "Mangga", "Pisang", "Anggur"];
        const daftarBuah = document.getElementById("daftarBuah");

        for (let item of buah) {
            const li = document.createElement("li");
            li.textContent = item;
            daftarBuah.appendChild(li);
        }
    </script>
</body>
</html>
```

### Contoh 2: Tabel Data
```html
<!DOCTYPE html>
<html>
<head>
    <title>Tabel Data</title>
    <style>
        table {
            border-collapse: collapse;
            width: 100%;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <h2>Daftar Siswa</h2>
    <table id="tabelSiswa">
        <thead>
            <tr>
                <th>No</th>
                <th>Nama</th>
                <th>Nilai</th>
                <th>Status</th>
            </tr>
        </thead>
        <tbody id="dataSiswa"></tbody>
    </table>

    <script>
        const siswa = [
            { nama: "John", nilai: 85 },
            { nama: "Jane", nilai: 92 },
            { nama: "Bob", nilai: 78 },
            { nama: "Alice", nilai: 95 }
        ];

        const dataSiswa = document.getElementById("dataSiswa");

        for (let i = 0; i < siswa.length; i++) {
            const row = document.createElement("tr");
            
            // Nomor
            const noCell = document.createElement("td");
            noCell.textContent = i + 1;
            row.appendChild(noCell);
            
            // Nama
            const namaCell = document.createElement("td");
            namaCell.textContent = siswa[i].nama;
            row.appendChild(namaCell);
            
            // Nilai
            const nilaiCell = document.createElement("td");
            nilaiCell.textContent = siswa[i].nilai;
            row.appendChild(nilaiCell);
            
            // Status
            const statusCell = document.createElement("td");
            statusCell.textContent = siswa[i].nilai >= 80 ? "Lulus" : "Tidak Lulus";
            statusCell.style.color = siswa[i].nilai >= 80 ? "green" : "red";
            row.appendChild(statusCell);
            
            dataSiswa.appendChild(row);
        }
    </script>
</body>
</html>
```

### Contoh 3: Card Grid
```html
<!DOCTYPE html>
<html>
<head>
    <title>Card Grid</title>
    <style>
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        .card {
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 4px;
        }
        .card h3 {
            margin: 10px 0;
        }
        .card p {
            color: #666;
        }
    </style>
</head>
<body>
    <h2>Produk Kami</h2>
    <div id="productGrid" class="grid"></div>

    <script>
        const products = [
            {
                name: "Produk 1",
                price: "Rp 199.000",
                image: "https://via.placeholder.com/150",
                description: "Deskripsi produk 1"
            },
            {
                name: "Produk 2",
                price: "Rp 299.000",
                image: "https://via.placeholder.com/150",
                description: "Deskripsi produk 2"
            },
            {
                name: "Produk 3",
                price: "Rp 399.000",
                image: "https://via.placeholder.com/150",
                description: "Deskripsi produk 3"
            },
            // Tambahkan produk lainnya...
        ];

        const grid = document.getElementById("productGrid");

        for (let product of products) {
            const card = document.createElement("div");
            card.className = "card";
            
            card.innerHTML = `
                <img src="${product.image}" alt="${product.name}">
                <h3>${product.name}</h3>
                <p>${product.description}</p>
                <strong>${product.price}</strong>
            `;
            
            grid.appendChild(card);
        }
    </script>
</body>
</html>
```

### Contoh 4: Dynamic List dengan Filter
```html
<!DOCTYPE html>
<html>
<head>
    <title>Dynamic List</title>
    <style>
        .filter-container {
            margin-bottom: 20px;
        }
        .item {
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
        .highlight {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <div class="filter-container">
        <input type="text" id="searchInput" placeholder="Cari item...">
    </div>
    <div id="itemList"></div>

    <script>
        const items = [
            "JavaScript",
            "Python",
            "Java",
            "PHP",
            "Ruby",
            "C++",
            "Swift",
            "Go",
            "Rust"
        ];

        const itemList = document.getElementById("itemList");
        const searchInput = document.getElementById("searchInput");

        function renderItems(filter = "") {
            itemList.innerHTML = "";
            
            for (let item of items) {
                if (item.toLowerCase().includes(filter.toLowerCase())) {
                    const div = document.createElement("div");
                    div.className = "item";
                    
                    if (filter && item.toLowerCase().includes(filter.toLowerCase())) {
                        const regex = new RegExp(`(${filter})`, 'gi');
                        div.innerHTML = item.replace(regex, '<span class="highlight">$1</span>');
                    } else {
                        div.textContent = item;
                    }
                    
                    itemList.appendChild(div);
                }
            }
        }

        // Initial render
        renderItems();

        // Filter on input
        searchInput.addEventListener("input", (e) => {
            renderItems(e.target.value);
        });
    </script>
</body>
</html>
```

## 5. Latihan Mandiri

### Latihan 1: Todo List
Buat aplikasi todo list sederhana dengan fitur:
- Menambah item
- Menghapus item
- Menandai item selesai

### Latihan 2: Shopping Cart
Buat simulasi keranjang belanja dengan fitur:
- Daftar produk
- Menambah ke keranjang
- Menghitung total harga

### Latihan 3: Data Table
Buat tabel data dengan fitur:
- Sorting (urutkan berdasarkan kolom)
- Filtering (filter berdasarkan input)
- Pagination (tampilkan beberapa data per halaman)

## Kesimpulan
- Loop adalah struktur kontrol penting untuk mengotomatisasi tugas berulang
- JavaScript menyediakan berbagai jenis loop untuk kebutuhan berbeda
- Break dan continue membantu mengontrol alur loop
- Loop sangat berguna untuk memanipulasi DOM dan menampilkan data
- Kombinasi loop dengan array dan object memungkinkan pembuatan UI dinamis

## Referensi Tambahan
- [MDN Web Docs - Loops and Iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
- [JavaScript.info - Loops: while and for](https://javascript.info/while-for)
- [W3Schools - JavaScript Loops](https://www.w3schools.com/js/js_loop_for.asp)
- [Eloquent JavaScript - Program Structure](https://eloquentjavascript.net/02_program_structure.html)