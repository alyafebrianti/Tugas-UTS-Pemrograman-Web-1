# Tugas-UTS-Pemrograman-Web-1
# Data Mahasiswa
## Nama : Alya Febrianti
## NIM : 312410692
## Kelas : TI.24.A1
## Mata Kuliah : Pemrograman Web 1

# penjelasan

### 🏪 **Judul Proyek:**

# BookStore — Aplikasi Web Penjualan Buku Online

---

### 📖 **Deskripsi Proyek**

BookStore adalah **website toko buku online** yang dibuat menggunakan **HTML, CSS, dan JavaScript**.
Website ini memiliki fitur:

* Menampilkan daftar buku
* Melihat stok dan harga buku
* Menghitung total harga saat checkout
* Melihat statistik toko di dashboard
* Melacak pesanan menggunakan kode tracking

Seluruh data buku tersimpan dalam file `data.js` dan diolah secara dinamis oleh `script.js`.

---

### 🧱 **Struktur Folder dan File**

```
📂 bookstore/
├── index.html          → Halaman utama (daftar buku)
├── dashboard.html      → Halaman ringkasan statistik toko
├── stok.html           → Halaman stok buku
├── checkout.html       → Halaman pembelian / checkout
├── tracking.html       → Halaman pelacakan pesanan
├── style.css           → File CSS untuk desain tampilan
├── data.js             → Data semua buku (judul, harga, stok)
├── script.js           → Logika utama JavaScript
└── img/                → Folder gambar buku
```

---

### 🌐 **Penjelasan Tiap File**

#### 🏠 **1. index.html**

Halaman utama untuk menampilkan semua buku yang tersedia di toko.
Menampilkan gambar, judul, harga, dan tombol **Beli**.

## Codingan
```
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - Toko Buku Online</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="login-page">
    <div class="container" style="max-width: 400px; margin-top: 100px;">
        <h2>Login Toko Buku</h2>
        <form id="loginForm">
            <label for="email"><b>Email</b></label>
            <input type="email" placeholder="Masukkan Email" name="email" id="email" required>

            <label for="password"><b>Password</b></label>
            <input type="password" placeholder="Masukkan Password" name="password" id="password" required>

            <button type="submit">Login</button>
        </form>
        <div style="text-align: center; margin-top: 15px;">
            <button class="btn btn-secondary" id="lupaPasswordBtn">Lupa Password</button>
            <button class="btn btn-secondary" id="daftarBtn">Daftar</button>
        </div>
    </div>

    <div id="lupaPasswordModal" class="modal">
        <div class="modal-content">
            <span class="close-btn">&times;</span>
            <h3>Lupa Password</h3>
            <p>Masukkan email Anda untuk menerima link reset password.</p>
            <input type="email" placeholder="Email Anda" required>
            <button>Kirim Link</button>
        </div>
    </div>

    <div id="daftarModal" class="modal">
        <div class="modal-content">
            <span class="close-btn">&times;</span>
            <h3>Daftar Akun Baru</h3>
            <form id="daftarForm">
                <p>Silakan isi detail pendaftaran Anda.</p>
                <input type="text" placeholder="Nama Lengkap" required>
                <input type="email" placeholder="Email" required>
                <input type="password" placeholder="Password" required>
                <button type="button" id="submitDaftar">Daftar Sekarang</button>
            </form>
        </div>
    </div>

    <script src="data.js"></script>
    <script src="script.js"></script>
</body>
</html>
```

🖼️ **Output:**

```
📕 Manajemen Keuangan
Harga: Rp60.000
Stok: 5
[ Beli ]
```

#### 📊 **2. dashboard.html**

Menampilkan ringkasan keseluruhan dari toko buku, seperti:

* Jumlah total buku
* Jumlah total stok
* Total harga semua buku
  
# Codingan 

```

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard - Toko Buku Online</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="dashboard-page">
    <div class="header">
        <div class="container">
            <div class="logo">
                <a href="dashboard.html">
                    <img src="aset/bookstore_logo.png" alt="BookStore Logo" class="header-logo">
                    <span>BookStore</span> 
                </a>
            </div>
            
            <div class="search-bar">
                <input type="text" placeholder="Cari buku...">
                <button>🔎</button>
            </div>

            <div class="nav-icons">
                <a href="stok.html" class="icon-link" title="Katalog">📚</a>
                <a href="checkout.html" class="icon-link" title="Pemesanan">🛒</a>
                <a href="tracking.html" class="icon-link" title="Tracking">🚚</a>
                <a href="#" onclick="handleLogout()" class="icon-link" title="Logout">🚪</a>
            </div>
        </div>
    </div>

    <div class="container">
        <h1 id="greeting">Loading...</h1>
        <hr>
        <h2>Menu Utama</h2>
        <div class="card-grid">
            <div class="card">
                <h3>📚 Stok/Katalog Buku</h3>
                <p>Lihat dan kelola daftar buku yang tersedia.</p>
                <a href="stok.html" class="btn">Kunjungi Katalog</a>
            </div>
            <div class="card">
                <h3>🚚 Tracking Pengiriman</h3>
                <p>Lacak status pesanan yang sedang dalam proses kirim.</p>
                <a href="tracking.html" class="btn">Lacak Pesanan</a>
            </div>
            <div class="card">
                <h3>🛒 Pemesanan Baru</h3>
                <p>Buat pemesanan buku baru (Laporan Pemesanan & History Transaksi).</p>
                <a href="checkout.html" class="btn">Checkout</a>
            </div>
        </div>
    </div>

    <script src="data.js"></script>
    <script src="script.js"></script>
</body>
</html>

```
  

🖼️ **Output:**

```
Total Buku: 5
Total Stok: 43
Total Harga: Rp278.000
```
<img width="952" height="500" alt="dashboard" src="https://github.com/user-attachments/assets/18f65e70-10ab-4ec7-bfe0-50be59a8b5f8" />

<img width="337" height="389" alt="dashboard katalog buku" src="https://github.com/user-attachments/assets/cd90a7dd-aa2b-447d-bef4-b4551809d3b0" />

<img width="660" height="435" alt="tambah stok buku" src="https://github.com/user-attachments/assets/a4a9074b-1317-453f-b632-bce3cde58ac3" />

---

#### 📦 **3. stok.html**

Halaman untuk melihat data stok dan harga buku.

# Codingan
```
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stok & Katalog - Toko Buku Online</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="stok-page">
    <div class="header">
        <div class="container">
            <div class="logo">
                <a href="dashboard.html">
                    <img src="aset/bookstore_logo.png" alt="BookStore Logo" class="header-logo">
                    <span>BookStore</span> 
                </a>
            </div>
            
            <div class="search-bar">
                <input type="text" placeholder="Cari buku...">
                <button>🔎</button>
            </div>

            <div class="nav-icons">
                <a href="stok.html" class="icon-link" title="Katalog">📚</a>
                <a href="checkout.html" class="icon-link" title="Pemesanan">🛒</a>
                <a href="tracking.html" class="icon-link" title="Tracking">🚚</a>
                <a href="#" onclick="handleLogout()" class="icon-link" title="Logout">🚪</a>
            </div>
        </div>
    </div>

    <div class="container">
        <h1>Katalog Buku</h1>
        <hr>

        <button id="openStokModal" class="btn">Tambah Stok Buku Baru</button>

        <h2>Daftar Buku Tersedia</h2>
        <div id="katalogList" class="card-grid">
            <p>Memuat data...</p>
        </div>
    </div>

    <div id="stokModal" class="modal">
        <div class="modal-content">
            <span id="closeStokModal" class="close-btn">&times;</span>
            <h3>Tambah Stok Buku Baru</h3>
            <form id="addStokForm">
                <label for="new_kodeBarang">Kode Barang</label>
                <input type="text" id="new_kodeBarang" required>

                <label for="new_namaBarang">Nama Barang</label>
                <input type="text" id="new_namaBarang" required>

                <label for="new_jenisBarang">Jenis Barang</label>
                <input type="text" id="new_jenisBarang" value="Buku Ajar" required>

                <label for="new_edisi">Edisi</label>
                <input type="text" id="new_edisi">

                <label for="new_stok">Stok</label>
                <input type="number" id="new_stok" min="1" required>

                <label for="new_harga">Harga</label>
                <input type="text" id="new_harga" placeholder="Contoh: Rp 150.000" required>

                <button type="submit">Simpan Stok Baru</button>
            </form>
        </div>
    </div>

    <script src="data.js"></script>
    <script src="script.js"></script>
</body>
</html>

```

🖼️ **Output:**

```
📘 Pengantar Komunikasi
Harga: Rp50.000
Stok: 10
```
<img width="660" height="435" alt="tambah stok buku" src="https://github.com/user-attachments/assets/08308739-3e72-45aa-be6d-cb566d3bfdfd" />

<img width="629" height="451" alt="berhasil tambah stok buku" src="https://github.com/user-attachments/assets/6989c3da-9096-4d11-832d-42f8a267fd10" />

---

#### 💳 **4. checkout.html**

Formulir pembelian buku dengan perhitungan total otomatis.
Pengguna memilih buku dan jumlah, lalu total harga akan tampil otomatis.

# Codingan

```
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Checkout - Toko Buku Online</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="checkout-page">
    <div class="header">
        <div class="container">
            <div class="logo">
                <a href="dashboard.html">
                    <img src="aset/bookstore_logo.png" alt="BookStore Logo" class="header-logo">
                    <span>BookStore</span> 
                </a>
            </div>
            
            <div class="search-bar">
                <input type="text" placeholder="Cari buku...">
                <button>🔎</button>
            </div>

            <div class="nav-icons">
                <a href="stok.html" class="icon-link" title="Katalog">📚</a>
                <a href="checkout.html" class="icon-link" title="Pemesanan">🛒</a>
                <a href="tracking.html" class="icon-link" title="Tracking">🚚</a>
                <a href="#" onclick="handleLogout()" class="icon-link" title="Logout">🚪</a>
            </div>
        </div>
    </div>

    <div class="container">
        <h1>Halaman Pemesanan (Checkout)</h1>
        <hr>

        <h2>Detail Keranjang Belanja</h2>
        <table id="cartTable">
            <thead>
                <tr>
                    <th>Kode Barang</th>
                    <th>Nama Barang</th>
                    <th>Harga Satuan</th>
                    <th>Qty</th>
                    <th>Subtotal</th>
                    <th>Aksi</th>
                </tr>
            </thead>
            <tbody id="cartTableBody">
                </tbody>
            <tfoot>
                <tr>
                    <td colspan="4" style="text-align: right;"><strong>Total Pembayaran:</strong></td>
                    <td colspan="2"><strong id="grandTotal">Rp 0</strong></td>
                </tr>
            </tfoot>
        </table>
        
        <br>
        <h2>Informasi Pemesan & Pembayaran</h2>
        <form id="checkoutForm">
            <label for="namaPemesan">Nama Lengkap</label>
            <input type="text" id="namaPemesan" required>

            <label for="alamat">Alamat Pengiriman</label>
            <textarea id="alamat" rows="4" required></textarea>

            <label for="metodeBayar">Metode Pembayaran</label>
            <select id="metodeBayar" required>
                <option value="">Pilih Metode</option>
                <option value="transfer">Transfer Bank</option>
                <option value="cod">COD (Bayar di Tempat)</option>
            </select>

            <button type="submit" style="width: 100%;">Konfirmasi Pemesanan</button>
        </form>
    </div>

    <script src="data.js"></script>
    <script src="script.js"></script>
</body>
</html>

```

🖼️ **Output:**

```
Pilih Buku: [Dropdown]
Jumlah: [ 2 ]
Total: Rp100.000
```

<img width="628" height="449" alt="halaman tambah keranjang" src="https://github.com/user-attachments/assets/02c407f8-dcb2-4783-8db6-0453ab9d523b" />

<img width="496" height="344" alt="halaman pemesanan" src="https://github.com/user-attachments/assets/74803806-7eb1-43c6-a87a-700b84b0b5ce" />

<img width="748" height="446" alt="berhasil tambah pemesanan" src="https://github.com/user-attachments/assets/bfa9d79a-334b-4113-b3db-910746b97952" />

---

#### 🚚 **5. tracking.html**

Halaman untuk melacak status pesanan berdasarkan kode unik.

# Codingan

```
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tracking Pengiriman - Toko Buku Online</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="tracking-page">
    <div class="header">
        <div class="container">
            <div class="logo">
                <a href="dashboard.html">
                    <img src="aset/bookstore_logo.png" alt="BookStore Logo" class="header-logo">
                    <span>BookStore</span> 
                </a>
            </div>
            
            <div class="search-bar">
                <input type="text" placeholder="Cari buku...">
                <button>🔎</button>
            </div>

            <div class="nav-icons">
                <a href="stok.html" class="icon-link" title="Katalog">📚</a>
                <a href="checkout.html" class="icon-link" title="Pemesanan">🛒</a>
                <a href="tracking.html" class="icon-link" title="Tracking">🚚</a>
                <a href="#" onclick="handleLogout()" class="icon-link" title="Logout">🚪</a>
            </div>
        </div>
    </div>

    <div class="container">
        <h1>Lacak Pengiriman Pesanan</h1>
        <hr>

        <form id="trackingForm">
            <label for="doNumber">Nomor Delivery Order (DO)</label>
            <input type="text" placeholder="Contoh: 20230012" name="doNumber" id="doNumber" required>

            <button type="submit">Cari Status</button>
        </form>

        <div id="trackingResult" style="margin-top: 30px;">
            </div>
    </div>

    <script src="data.js"></script>
    <script src="script.js"></script>
</body>
</html>

```

🖼️ **Output:**

```
Masukkan Kode Pesanan: [12345]
→ Status: Pesanan Anda sedang dikirim 📦
```

<img width="937" height="361" alt="halaman lacak pengiriman" src="https://github.com/user-attachments/assets/60265322-175e-40c6-abea-bc9368419f4d" />

<img width="471" height="437" alt="berhasil lacak pesanan" src="https://github.com/user-attachments/assets/a10ef7fa-e819-48fd-a438-4ae7d18037a1" />

<img width="494" height="401" alt="lacak pengiriman" src="https://github.com/user-attachments/assets/40d2892d-0d64-483c-b3ba-e7942e9786d0" />

---

#### 🎨 **6. style.css**

Mengatur tampilan website agar rapi dan menarik:

* Warna dominan biru
* Tata letak menu dan konten
* Desain kartu buku, form, dan tombol

Contoh gaya:

```css
header {
  background-color: #0077b6;
  color: white;
  text-align: center;
  padding: 20px;
}
```

---
# Codingan CSS

```
/* style.css */

/* ====== LATAR & TIPOGRAFI ====== */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f9;
    color: #333;
}

a {
    text-decoration: none;
    color: #007bff;
}

a:hover {
    color: #0056b3;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 20px auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* Header/Navbar (Gaya E-commerce dengan UNGU) */
.header {
    /* WARNA UTAMA: UNGU TERANG */
    background-color: #E0BBE4; 
    color: #333; /* Teks header diubah agar kontras dengan latar terang */
    padding: 15px 0;
    margin-bottom: 20px;
}

.header .container {
    display: grid; 
    grid-template-columns: auto 1fr auto; 
    gap: 20px;
    align-items: center;
    background-color: transparent;
    box-shadow: none;
    padding: 0 20px;
    width: auto;
    max-width: 1200px;
    margin: 0 auto;
}

/* Bagian Logo (Kolom 1) */
.logo a {
    color: #333; /* Warna teks logo disesuaikan */
    font-size: 2.2em;
    font-weight: 800;
    display: flex; 
    align-items: center; 
}

.header-logo {
    height: 100px; 
    margin-right: 10px; 
    width: auto; 
}

/* Search Bar (Kolom 2) */
.search-bar {
    display: flex;
    justify-content: flex-start;
}

.search-bar input {
    width: 70%;
    padding: 10px;
    border: none;
    border-radius: 4px 0 0 4px; 
    font-size: 1em;
}

.search-bar button {
    /* WARNA SEKUNDER (Ungu Gelap) untuk tombol search */
    background-color: #957DAD; 
    color: white;
    padding: 10px 15px;
    border: none;
    border-radius: 0 4px 4px 0; 
    cursor: pointer;
    margin: 0;
}

/* Navigasi dan Ikon (Kolom 3) */
.nav-icons {
    display: flex;
    align-items: center;
    justify-content: flex-end; 
}

/* Gaya Ikon */
.icon-link {
    color: #333; /* Warna ikon disesuaikan */
    margin-left: 15px;
    font-size: 1.5em; 
    cursor: pointer;
}

.icon-link:hover {
    color: #957DAD; /* Warna hover ungu gelap */
}

/* Forms and Inputs */
input[type="email"],
input[type="password"],
input[type="text"],
input[type="number"],
select,
textarea {
    width: 100%;
    padding: 12px;
    margin: 8px 0 16px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

button, .btn {
    /* WARNA TOMBOL PRIMER: UNGU GELAP */
    background-color: #957DAD; 
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1em;
    transition: background-color 0.3s;
    display: inline-block;
    text-align: center;
}

button:hover, .btn:hover {
    background-color: #79688c; /* Ungu sedikit lebih gelap */
}

.btn-secondary {
    background-color: #6c757d;
}

.btn-secondary:hover {
    background-color: #5a6268;
}

/* Card Styles (for dashboard and katalog) */
.card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

.card {
    background: #fff;
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 15px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
    text-align: center;
}

.card img {
    max-width: 100%;
    height: auto;
    border-radius: 4px;
    margin-bottom: 10px;
}

/* Table Styles */
table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

th, td {
    border: 1px solid #ddd;
    padding: 12px;
    text-align: left;
}

th {
    background-color: #f2f2f2;
}

/* Modal/Pop-up Styles */
.modal {
    display: none; 
    position: fixed;
    z-index: 100;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.4);
    padding-top: 60px;
}

.modal-content {
    background-color: #fefefe;
    margin: 5% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
    max-width: 500px;
    border-radius: 8px;
    position: relative;
}

.close-btn {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close-btn:hover,
.close-btn:focus {
    color: #000;
    text-decoration: none;
    cursor: pointer;
}

/* Tracking Progress Bar (Example) */
.progress-container {
    margin-top: 15px;
}

.progress-bar {
    width: 100%;
    background-color: #e0e0e0;
    border-radius: 5px;
    overflow: hidden;
}

.progress {
    height: 30px;
    /* Warna progress dipertahankan agar menunjukkan status (hijau) */
    background-color: #28a745; 
    color: white;
    text-align: center;
    line-height: 30px;
    border-radius: 5px;
    transition: width 0.4s ease;
}

.progress.dikirim {
    width: 80%;
    background-color: #ffc107;
}

.progress.dalam-perjalanan {
    width: 50%;
    background-color: #007bff;
}

.tracking-detail {
    margin-top: 20px;
    border: 1px solid #ddd;
    padding: 15px;
    border-radius: 5px;
    background-color: #f9f9f9;
}

.tracking-history ul {
    list-style: none;
    padding: 0;
    margin-top: 10px;
}

.tracking-history li {
    padding: 10px 0;
    border-bottom: 1px dotted #ddd;
}
```
#### 📂 **7. data.js**

Menyimpan data buku dalam bentuk *array of objects*:

```javascript
const books = [
  { title: "Manajemen Keuangan", price: 60000, stock: 5, image: "img/manajemen.jpg" },
  { title: "Mikrobiologi Dasar", price: 45000, stock: 8, image: "img/mikrobiologi.jpg" }
];
```

File ini berfungsi sebagai “database” untuk seluruh halaman.

---
# Codingan data.js
```
var dataPengguna = [
    {
        id: 1,
        nama: "Rina Wulandari",
        email: "rina@gmail.com",
        password: "rina123",
        role: "User",
    },
    {
        id: 2,
        nama: "Agus Pranoto",
        email: "agus@gmail.com",
        password: "agus123",
        role: "User",
    },
    {
        id: 3,
        nama: "Siti Marlina",
        email: "siti@gmail.com",
        password: "siti123",
        role: "Admin",
    }
]

var dataKatalogBuku = [
    {
        kodeBarang: "ASIP4301",
        namaBarang: "Pengantar Ilmu Komunikasi",
        jenisBarang: "Buku Ajar",
        edisi: "2",
        stok: 548,
        harga: "Rp 180.000",
        cover: "img/pengantar_komunikasi.jpg"
    },
    {
        kodeBarang: "EKMA4002",
        namaBarang: "Manajemen Keuangan",
        jenisBarang: "Buku Ajar",
        edisi: "3",
        stok: 392,
        harga: "Rp 220.000",
        cover: "img/manajemen_keuangan.jpg"
    },
    {
        kodeBarang: "EKMA4310",
        namaBarang: "Kepemimpinan",
        jenisBarang: "Buku Ajar",
        edisi: "1",
        stok: 278,
        harga: "Rp 150.000",
        cover: "img/kepemimpinan.jpg"
    },
    {
        kodeBarang: "BIOL4211",
        namaBarang: "Mikrobiologi Dasar",
        jenisBarang: "Buku Ajar",
        edisi: "2",
        stok: 165,
        harga: "Rp 200.000",
        cover: "img/mikrobiologi.jpg"
    },
    {
        kodeBarang: "PAUD4401",
        namaBarang: "Perkembangan Anak Usia Dini",
        jenisBarang: "Buku Ajar",
        edisi: "4",
        stok: 204,
        harga: "Rp 250.000",
        cover: "img/paud_perkembangan.jpg"
    }
]

var dataTracking = {
    "20230012": {
        nomorDO: "20230012",
        nama: "Rina Wulandari",
        status: "Dalam Perjalanan",
        ekspedisi: "JNE",
        tanggalKirim: "2025-08-25",
        paket: "0JKT01",
        total: "Rp 180.000",
        perjalanan:[
            {
                waktu: "2025-08-25 10:12:20",
                keterangan: "Penerimaan di Loket: TANGERANG SELATAN. Pengirim: Universitas Terbuka"
            },
            {
                waktu: "2025-08 25 14:07:56",
                keterangan: "Tiba di Hub: TANGERANG SELATAN"
            },
            {
                waktu: "2025-08-25 10:12:20",
                keterangan: "Diteruskan ke Kantor Jakarta Selatan"
            },
        ]
    },
    "20230013": {
        nomorDO: "20230013",
        nama: "Agus Pranoto",
        status: "Dikirim",
        ekspedisi: "Pos Indonesia",
        tanggalKirim: "2025-08-25",
        paket: "0UPBJJBDG",
        total: "Rp 220.000",
        perjalanan:[
            {
                waktu: "2025-08-25 10:12:20",
                keterangan: "Penerimaan di Loket: TANGERANG SELATAN. Pengirim: Universitas Terbuka"
            },
            {
                waktu: "2025-08-25 14:07:56",
                keterangan: "Tiba di Hub: TANGERANG SELATAN"
            },      
            {
                waktu: "2025-08-25 16:30:10",
                keterangan: "Diteruskan ke Kantor Kota Bandung"
            },
            {
                waktu: "2025-08-26 12:15:33",
                keterangan: "Tiba di Hub: Kota BANDUNG"
            },
            {
                waktu: "2025-08-26 15:06:12",
                keterangan: "Proses antar ke Cimahi"
            },
            {
                waktu: "2025-08-26 20:00:00",
                keterangan: "Selesai Antar. Penerima: Agus Pranoto"
            }
        ]
    }
}

```
<img width="338" height="326" alt="image" src="https://github.com/user-attachments/assets/e04a1133-c9f7-4224-99cc-b664eb231a48" />


<img width="412" height="305" alt="daftar" src="https://github.com/user-attachments/assets/ddd4b2ed-ee4b-448b-8146-475c5fb9da73" />

#### ⚙️ **8. script.js**

File utama untuk logika interaktif:

* Menampilkan buku di halaman utama
* Menghitung total pembelian
* Menampilkan stok
* Melacak pesanan
* Mengisi dashboard statistik

Contoh fungsi:

```javascript
function hitungTotal() {
  const select = document.getElementById("bookSelect");
  const jumlah = document.getElementById("jumlah").value;
  const total = select.value * jumlah;
  document.getElementById("totalHarga").innerText =
    `Total: Rp${total.toLocaleString()}`;
}
```

---
# Codingan script.js

```
// script.js

let currentDataPengguna = []; 
let shoppingCart = []; 

// --- Global Functions ---

function loadUserData() {
    const localUsers = localStorage.getItem('allUsers');
    
    if (localUsers) {
        currentDataPengguna = JSON.parse(localUsers);
    } else {
        currentDataPengguna = dataPengguna; 
        localStorage.setItem('allUsers', JSON.stringify(dataPengguna));
    }
}

function handleLogout() {
    localStorage.removeItem('loggedInUser'); 
    window.location.href = 'index.html'; 
}

function showGreeting() {
    const date = new Date();
    const hour = date.getHours();
    let greeting;

    if (hour >= 5 && hour < 12) {
        greeting = "Selamat Pagi";
    } else if (hour >= 12 && hour < 17) {
        greeting = "Selamat Siang";
    } else if (hour >= 17 && hour < 20) {
        greeting = "Selamat Sore";
    } else {
        greeting = "Selamat Malam";
    }

    const greetingElement = document.getElementById('greeting');
    if (greetingElement) {
        const loggedInUser = localStorage.getItem('loggedInUser');
        const userName = loggedInUser ? JSON.parse(loggedInUser).nama : "Pengguna";
        greetingElement.textContent = `${greeting}, ${userName}!`; 
    }
}

// --- Login/Registration Logic (index.html) ---
function handleLogin() {
    const loginForm = document.getElementById('loginForm');
    if (loginForm) {
        loginForm.addEventListener('submit', function(event) {
            event.preventDefault();
            const emailInput = document.getElementById('email').value;
            const passwordInput = document.getElementById('password').value;

            const user = currentDataPengguna.find(
                u => u.email === emailInput && u.password === passwordInput
            );

            if (user) {
                localStorage.setItem('loggedInUser', JSON.stringify(user));
                window.location.href = 'dashboard.html';
            } else {
                alert("Email/password yang Anda masukkan salah");
            }
        });

        // Setup Modal for Lupa Password and Daftar
        const lupaPasswordModal = document.getElementById('lupaPasswordModal');
        const daftarModal = document.getElementById('daftarModal');
        const closeBtns = document.querySelectorAll('.close-btn');

        document.getElementById('lupaPasswordBtn').onclick = () => {
            lupaPasswordModal.style.display = 'block';
        };

        document.getElementById('daftarBtn').onclick = () => {
            daftarModal.style.display = 'block';
        };

        closeBtns.forEach(btn => {
            btn.onclick = function() {
                btn.closest('.modal').style.display = 'none';
            };
        });

        window.onclick = function(event) {
            if (event.target === lupaPasswordModal) {
                lupaPasswordModal.style.display = 'none';
            }
            if (event.target === daftarModal) {
                daftarModal.style.display = 'none';
            }
        };
    }
}

function handleRegistration() {
    const daftarModal = document.getElementById('daftarModal');
    const registerButton = document.getElementById('submitDaftar');

    if (registerButton) {
        registerButton.addEventListener('click', function() {
            const inputs = daftarModal.querySelectorAll('input');
            const nama = inputs[0].value.trim();
            const email = inputs[1].value.trim();
            const password = inputs[2].value.trim();

            if (!nama || !email || !password) {
                alert("Semua kolom (Nama, Email, Password) wajib diisi.");
                return;
            }

            const isEmailExist = currentDataPengguna.some(u => u.email === email);
            if (isEmailExist) {
                alert("Gagal: Email ini sudah terdaftar. Silakan gunakan email lain.");
                return;
            }

            const newUser = {
                id: currentDataPengguna.length + 1,
                nama: nama,
                email: email,
                password: password,
                role: "User",
            };

            currentDataPengguna.push(newUser);
            
            localStorage.setItem('allUsers', JSON.stringify(currentDataPengguna)); 

            alert(`Pendaftaran berhasil! Selamat datang, ${nama}. Anda sekarang bisa login.`);

            daftarModal.style.display = 'none';
            document.getElementById('daftarForm').reset();
        });
    }
}

// --- Dashboard Logic ---
function initDashboard() {
    showGreeting();
}

// --- Stok/Katalog Logic (stok.html) ---
function initStok() {
    if (typeof dataKatalogBuku === 'undefined') {
        document.getElementById('katalogList').innerHTML = '<p>Error: dataKatalogBuku tidak ditemukan.</p>';
        return;
    }

    renderKatalog(dataKatalogBuku);
    handleAddNewStok();
}

function renderKatalog(katalog) {
    const katalogList = document.getElementById('katalogList');
    if (!katalogList) return;
    katalogList.innerHTML = ''; 

    katalog.forEach(buku => {
        const card = document.createElement('div');
        card.className = 'card';
        card.innerHTML = `
            <img src="${buku.cover}" alt="${buku.namaBarang}" onerror="this.src='img/default_book.png'" style="max-height: 250px; object-fit: cover;">
            <h3>${buku.namaBarang}</h3>
            <p><strong>Kode:</strong> ${buku.kodeBarang}</p>
            <p><strong>Stok:</strong> ${buku.stok}</p>
            <p><strong>Harga:</strong> ${buku.harga}</p>
            <button class="btn" onclick="addToCart('${buku.kodeBarang}')">Tambah ke Keranjang</button>
        `;
        katalogList.appendChild(card);
    });
}

function handleAddNewStok() {
    const addStokForm = document.getElementById('addStokForm');
    const stokModal = document.getElementById('stokModal');

    document.getElementById('openStokModal').onclick = () => {
        stokModal.style.display = 'block';
    };

    document.getElementById('closeStokModal').onclick = () => {
        stokModal.style.display = 'none';
    };

    window.onclick = function(event) {
        if (event.target === stokModal) {
            stokModal.style.display = 'none';
        }
    };


    if (addStokForm) {
        addStokForm.addEventListener('submit', function(event) {
            event.preventDefault();

            const newBuku = {
                kodeBarang: document.getElementById('new_kodeBarang').value,
                namaBarang: document.getElementById('new_namaBarang').value,
                jenisBarang: document.getElementById('new_jenisBarang').value,
                edisi: document.getElementById('new_edisi').value,
                stok: parseInt(document.getElementById('new_stok').value),
                harga: document.getElementById('new_harga').value,
                cover: "img/default_book.png" 
            };

            if (!newBuku.kodeBarang || !newBuku.namaBarang || isNaN(newBuku.stok)) {
                alert("Semua kolom harus diisi dengan benar.");
                return;
            }

            dataKatalogBuku.push(newBuku);
            renderKatalog(dataKatalogBuku); 
            alert(`Buku "${newBuku.namaBarang}" berhasil ditambahkan!`);
            addStokForm.reset();
            stokModal.style.display = 'none';
        });
    }
}

// --- Checkout/Cart Logic (checkout.html) ---
function initCheckout() {
    const savedCart = localStorage.getItem('shoppingCart');
    if (savedCart) {
        shoppingCart = JSON.parse(savedCart);
    }
    
    renderCartTable();
    handleCheckoutSubmit();
}

function renderCartTable() {
    const cartTableBody = document.getElementById('cartTableBody');
    const totalElement = document.getElementById('grandTotal');
    
    if (!cartTableBody || !totalElement) return;

    cartTableBody.innerHTML = ''; 
    let grandTotal = 0;

    shoppingCart.forEach((item, index) => {
        const priceNum = parseInt(item.harga.replace('Rp ', '').replace('.', ''));
        const subtotalNum = priceNum * item.qty;
        grandTotal += subtotalNum;

        const row = cartTableBody.insertRow();
        row.innerHTML = `
            <td>${item.kodeBarang}</td>
            <td>${item.namaBarang}</td>
            <td>${item.harga}</td>
            <td>
                <input type="number" value="${item.qty}" min="1" 
                       style="width: 50px; text-align: center;" 
                       onchange="updateCartQty(${index}, this.value)">
            </td>
            <td>Rp ${subtotalNum.toLocaleString('id-ID')}</td>
            <td>
                <button class="btn-secondary" style="padding: 5px 10px;" onclick="removeFromCart(${index})">Hapus</button>
            </td>
        `;
    });

    totalElement.textContent = `Rp ${grandTotal.toLocaleString('id-ID')}`;
    localStorage.setItem('shoppingCart', JSON.stringify(shoppingCart));
}

function addToCart(kodeBarang) {
    if (typeof dataKatalogBuku === 'undefined') {
        alert("Data katalog tidak ditemukan.");
        return;
    }

    const buku = dataKatalogBuku.find(b => b.kodeBarang === kodeBarang);
    if (!buku) return;

    const existingItem = shoppingCart.find(item => item.kodeBarang === kodeBarang);

    if (existingItem) {
        existingItem.qty += 1; 
        alert(`Kuantitas ${buku.namaBarang} diperbarui menjadi ${existingItem.qty}`);
    } else {
        shoppingCart.push({
            kodeBarang: buku.kodeBarang,
            namaBarang: buku.namaBarang,
            harga: buku.harga,
            qty: 1
        });
        alert(`Buku "${buku.namaBarang}" berhasil ditambahkan ke keranjang!`);
    }
    localStorage.setItem('shoppingCart', JSON.stringify(shoppingCart));
}

function updateCartQty(index, newQty) {
    const qty = parseInt(newQty);
    if (qty > 0) {
        shoppingCart[index].qty = qty;
        renderCartTable();
    } else {
        alert("Kuantitas harus lebih dari 0.");
    }
}

function removeFromCart(index) {
    const deletedItem = shoppingCart[index].namaBarang;
    shoppingCart.splice(index, 1); 
    alert(`${deletedItem} berhasil dihapus dari keranjang.`);
    renderCartTable();
}

function handleCheckoutSubmit() {
    const checkoutForm = document.getElementById('checkoutForm');
    if (checkoutForm) {
        checkoutForm.addEventListener('submit', function(event) {
            event.preventDefault();

            if (shoppingCart.length === 0) {
                alert("Keranjang belanja Anda kosong. Silakan tambahkan buku terlebih dahulu.");
                return;
            }

            const namaPemesan = document.getElementById('namaPemesan').value;
            const alamat = document.getElementById('alamat').value;
            const metodeBayar = document.getElementById('metodeBayar').value;
            
            if (!namaPemesan || !alamat || !metodeBayar) {
                alert("Mohon lengkapi semua data pemesan dan pembayaran.");
                return;
            }

            alert(`Pemesanan Berhasil!\n\nNama: ${namaPemesan}\nTotal Item: ${shoppingCart.length}\nTotal Bayar: ${document.getElementById('grandTotal').textContent}\nPesanan Anda akan segera diproses.`);

            shoppingCart = [];
            localStorage.removeItem('shoppingCart');
            renderCartTable();
            checkoutForm.reset();
        });
    }
}


// --- Tracking Logic (tracking.html) ---
function initTracking() {
    const trackingForm = document.getElementById('trackingForm');
    if (trackingForm) {
        trackingForm.addEventListener('submit', function(event) {
            event.preventDefault();
            const doNumber = document.getElementById('doNumber').value.trim();

            const result = dataTracking[doNumber];

            const trackingResultDiv = document.getElementById('trackingResult');
            trackingResultDiv.innerHTML = ''; 

            if (result) {
                trackingResultDiv.innerHTML = `
                    <h3>Detail Pengiriman: #${result.nomorDO}</h3>
                    <div class="tracking-detail">
                        <p><strong>Nama Pemesan:</strong> ${result.nama}</p>
                        <p><strong>Status Pengiriman:</strong> 
                            <span style="font-weight: bold; color: ${result.status === 'Dikirim' ? 'green' : (result.status === 'Dalam Perjalanan' ? 'blue' : 'orange')};">${result.status}</span>
                        </p>
                        <div class="progress-container">
                            <label>Simulasi Progress:</label>
                            <div class="progress-bar">
                                <div class="progress ${result.status.toLowerCase().replace(/ /g, '-')}" style="width: ${result.status === 'Dikirim' ? '100%' : (result.status === 'Dalam Perjalanan' ? '60%' : '20%')};">${result.status}</div>
                            </div>
                        </div>
                        <p><strong>Ekspedisi:</strong> ${result.ekspedisi}</p>
                        <p><strong>Tanggal Kirim:</strong> ${result.tanggalKirim}</p>
                        <p><strong>Jenis Paket:</strong> ${result.paket}</p>
                        <p><strong>Total Pembayaran:</strong> ${result.total}</p>
                    </div>

                    <div class="tracking-history">
                        <h4>Riwayat Perjalanan:</h4>
                        <ul>
                            ${result.perjalanan.map(log => `
                                <li><strong>[${log.waktu}]</strong> ${log.keterangan}</li>
                            `).join('')}
                        </ul>
                    </div>
                `;
            } else {
                trackingResultDiv.innerHTML = '<p style="color: red;">Nomor Delivery Order tidak ditemukan.</p>';
            }
        });
    }
}


// --- Main Initialization ---
document.addEventListener('DOMContentLoaded', () => {
    loadUserData(); 

    if (document.body.classList.contains('login-page')) {
        handleLogin();
        handleRegistration();
    } else if (document.body.classList.contains('dashboard-page')) {
        initDashboard();
    } else if (document.body.classList.contains('stok-page')) {
        initStok();
    } else if (document.body.classList.contains('tracking-page')) {
        initTracking();
    } else if (document.body.classList.contains('checkout-page')) {
        initCheckout();
    }
});

```
### 💻 **Cara Menjalankan Proyek**

1. Unduh semua file ke dalam satu folder (`bookstore`).
2. Pastikan semua gambar berada di folder `/img/`.
3. Buka `index.html` menggunakan browser (Chrome, Edge, Firefox, dll).
4. Gunakan menu navigasi untuk berpindah halaman:

   * 🏠 **Home**
   * 📊 **Dashboard**
   * 📦 **Stok Buku**
   * 💳 **Checkout**
   * 🚚 **Tracking**

---

---

### 👩‍💻 **Teknologi yang Digunakan**

| Teknologi    | Kegunaan                    |
| ------------ | --------------------------- |
| HTML5        | Struktur halaman            |
| CSS3         | Desain dan tata letak       |
| JavaScript   | Logika dan interaksi        |
| GitHub Pages | Hosting situs secara gratis |

---








