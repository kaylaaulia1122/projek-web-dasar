# 📦 Product Manager - Web Application

Aplikasi web manajemen inventaris produk modern yang dibangun menggunakan **PHP Native**, **MySQL**, dan **Tailwind CSS**. Proyek ini dibuat untuk memenuhi Tugas Akhir Pemrograman Web dengan menerapkan praktik terbaik penulisan kode, keamanan web (*Web Security*), dan desain antarmuka (*UI/UX*) interaktif.

![PHP](https://img.shields.io/badge/PHP-7.4%20%7C%208.x-777BB4?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-5.7%20%7C%208.x-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.x-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)

---

## 🌟 Fitur Utama

### 🛠️ Fitur Inti (CRUD)
- **Create**: Menambahkan produk baru dengan validasi server-side lengkap.
- **Read**: Menampilkan daftar produk menggunakan layout **Flexbox Responsive Cards**.
- **Update**: Memperbarui informasi produk berdasarkan ID.
- **Delete**: Menghapus data produk aman dengan modal konfirmasi interaktif.

### 🛡️ Fitur Keamanan (Web Security)
- **PDO Prepared Statements**: Mencegah serangan **SQL Injection** pada seluruh query database.
- **Output Escaping (`htmlspecialchars`)**: Melindungi aplikasi dari serangan **Cross-Site Scripting (XSS)**.
- **CSRF Token Protection**: Mengamankan aksi penghapusan data via method `POST` dengan verifikasi token session `hash_equals`.
- **Post-Redirect-Get (PRG) Pattern**: Mencegah resubmission data ganda saat halaman di-*refresh*.
- **Strict Server-side Validation**: Memastikan nama produk unik, nama $\ge 3$ karakter, harga $> 0$, dan stok $\ge 0$.

### 🎨 Fitur UI/UX & Bonus Dashboard
- **Stat Cards Bar**: Menampilkan ringkasan Total Produk, Nilai Inventaris (Rp), dan Stok Menipis ($\le 5$).
- **Live Search & Filter**: Fitur pencarian produk berdasarkan nama/kategori dengan parameter `GET` yang aman.
- **Stock Status Badges**: Indicator visual untuk stok tersedia, menipis, atau habis.
- **Toast Notifications**: Feedback visual saat berhasil menambah, mengedit, atau menghapus data.
- **Modal Konfirmasi Hapus**: Mencegah ketidaksengajaan saat menghapus produk.

---

## 📂 Struktur Proyek

```text
product-manager/
├── config/
│   └── db.php         # Konfigurasi koneksi PDO MySQL
├── database/
│   └── store_db.sql   # Skema database & data sampel
├── public/
│   ├── index.php      # Dashboard utama (READ + Search/Filter + Stats)
│   ├── create.php     # Form tambah produk (CREATE + PRG)
│   ├── edit.php       # Form edit produk (UPDATE + PRG)
│   └── delete.php     # Action handler hapus produk (DELETE + CSRF)
└── README.md
