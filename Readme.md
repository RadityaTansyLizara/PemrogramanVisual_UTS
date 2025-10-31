| Variable | Isi |
| -------- | --- |
| **Nama** | RADITYA TANSY LIZARA |
| **NIM** | 312310454 |
| **Kelas** | TI.23.A5 |
| **Mata Kuliah** | Pemrograman Visual (Desktop) |

# 🍪 KUE KERING 3 BERLIAN
## Website E-Commerce & Admin Panel untuk Usaha Kue Kering

Proyek ini dibuat sebagai **Tugas Ujian Tengah Semester (UTS)** Mata Kuliah **Pemrograman Visual (Desktop)** di Universitas Pelita Bangsa.

---


## 1️⃣ Cara Setting Web Service dan Configuration Web
Website **Kue Kering 3 Berlian** menggunakan pendekatan berbasis web service untuk memisahkan antara frontend dan backend.  

### ⚙️ Langkah Konfigurasi:
1. **Web Service:**  
   Menggunakan API berbasis HTTP dengan format JSON. Data dikirim melalui endpoint seperti `/api/users`, `/api/menus`, dan `/api/products`.  
2. **Database Connection:**  
   - Konfigurasi database di file `.env` (misalnya `DB_HOST`, `DB_USER`, `DB_PASS`).  
   - Gunakan ORM atau query builder untuk komunikasi ke tabel seperti `users`, `roles`, `menus`, dll.  
3. **Web Configuration:**  
   - Routing diatur untuk memisahkan halaman public (Login, Home) dan halaman admin (Dashboard, Management).  
   - Middleware memastikan autentikasi sebelum mengakses route admin.  
4. **Testing:**  
   Gunakan Postman atau browser console untuk memastikan setiap endpoint berfungsi.

> “Dengan sistem service terpisah, website menjadi lebih mudah dikembangkan dan aman dari error akibat integrasi langsung.”

---

## 2️⃣ Nama Project & Alasan Pemilihan
**Nama Project:** `KUE KERING 3 BERLIAN`

### 💡 Alasan Pembuatan Proyek

Pembuatan website **Kue Kering 3 Berlian** dilatarbelakangi oleh ketertarikan penulis dalam bidang kuliner, khususnya dalam pembuatan kue, serta keinginan untuk mengembangkan usaha rumahan menjadi lebih modern melalui proses digitalisasi.

Nama **"3 Berlian"** memiliki makna personal, terinspirasi dari penulis yang merupakan anak pertama dari tiga bersaudara perempuan. Ketiganya diibaratkan sebagai **berlian** — simbol keindahan, kekuatan, dan nilai berharga dalam kebersamaan keluarga.

Nama ini juga **mudah diingat**, menggambarkan **identitas produk**, serta **cocok untuk branding e-commerce makanan**, karena memberikan kesan elegan namun tetap hangat dan dekat dengan nilai keluarga.

Dengan adanya website ini, diharapkan proses promosi dan penjualan produk kue rumahan dapat dilakukan secara **lebih efektif, efisien, dan menarik** di era digital saat ini.


### 🌐 Tujuan Utama:
Menyediakan sistem penjualan kue kering online dengan fitur login, manajemen produk, dan navigasi yang mudah digunakan.

---

## 3️⃣ Bisnis Proses
### 🧭 Alur Bisnis:
1. **Admin Login** ke sistem.  
2. **Dashboard** menampilkan ringkasan data produk & user.  
3. **Admin** dapat mengatur *role*, *user*, *menu navigasi*, dan *produk*.  
4. **Customer** mengunjungi halaman utama untuk melihat produk dan melakukan pemesanan.  
5. **Sistem** menyimpan data transaksi dan menampilkan laporan kepada admin.

> “Proses bisnis ini memudahkan pemilik usaha mengelola data kue, stok, dan promosi dalam satu platform.”

---

## 4️⃣ Model Data
### 📘 Struktur Database Utama:
1. **users**
   - Menyimpan data pengguna (admin, staff).  
   - Kolom: `id`, `username`, `password`, `role_id`, `is_active`.

2. **roles**
   - Mengatur peran pengguna.  
   - Kolom: `id`, `role_id`, `name`, `description`, `is_active`.

3. **menus**
   - Mengatur struktur navigasi aplikasi.  
   - Kolom: `id`, `menu_id`, `name`, `parent_id`, `level`, `sequence`, `link`, `icon`, `is_active`.

4. **products**
   - Menyimpan daftar produk kue.  
   - Kolom: `id`, `product_id`, `name`, `price`, `stock`, `image`, `description`.

> “Relasi utama antara `roles` dan `users` bersifat one-to-many, sementara `menus` memiliki relasi self-reference melalui `parent_id`.”

---

## 5️⃣ Schema Team — Individual Project 👩🏻‍💻

---

### 👤 Pengembang Utama
**Nama:** RADITYA TANSY LIZARA  
**Peran:** Fullstack Developer & Project Owner  
**Proyek:** Website E-Commerce & Admin Panel — *KUE KERING 3 BERLIAN*  

---

### 🧩 Peran & Tanggung Jawab

Pada proyek **Kue Kering 3 Berlian**, seluruh proses pengembangan dilakukan secara mandiri oleh penulis. Mulai dari tahap perencanaan, desain antarmuka, hingga pengaturan sistem dan database — semuanya dikerjakan secara terstruktur dengan menggunakan **MongoDB**, **IIS (Internet Information Services)**, **SSMS (SQL Server Management Studio)**, **SQL**, dan **Balsamiq**.

| **Bidang** | **Deskripsi Peran & Tanggung Jawab** |
|-------------|--------------------------------------|
| 🎯 **Project Planning** | Merancang ide dan konsep utama proyek, menentukan tujuan website, target pengguna, serta fitur-fitur inti yang ingin dikembangkan. |
| 🎨 **UI/UX Design** | Mendesain tampilan mockup dan alur interaksi pengguna menggunakan **Balsamiq** agar website terlihat profesional, ceria, dan merepresentasikan brand *“Kue Kering 3 Berlian”*. |
| ⚙️ **System Configuration** | Mengatur koneksi server dan deployment menggunakan **IIS**, memastikan aplikasi dapat berjalan dengan baik di lingkungan lokal maupun hosting. |
| 🗂️ **Database Management** | Mendesain dan mengelola struktur data menggunakan **MongoDB**, **SSMS**, dan **SQL**, termasuk pembuatan tabel seperti `users`, `roles`, dan `menus` untuk mengatur data pengguna dan navigasi. |
| 🧪 **Testing & Debugging** | Melakukan pengujian sistem, memeriksa koneksi database, serta memastikan semua fungsi berjalan stabil dan sesuai kebutuhan. |
| 📝 **Documentation** | Menyusun dokumentasi teknis, menjelaskan struktur tabel, fitur, serta alur kerja sistem agar mudah dipahami dalam proses evaluasi maupun pengembangan selanjutnya. |


---

### 💡 Filosofi Pengembangan
> “Saya mengerjakan proyek ini secara mandiri untuk mengasah kemampuan logika, desain, dan pengembangan web secara menyeluruh — dari konsep, pembuatan antarmuka, hingga pengelolaan database.”

---

### 🌟 Hasil Akhir
Melalui pengerjaan individu ini, saya berhasil:
- Mengembangkan sistem **login, dashboard, dan manajemen data dinamis**.  
- Mendesain tampilan dengan **nuansa ceria dan profesional** sesuai tema produk.  
- Membangun **struktur aplikasi modular** yang mudah dikembangkan di masa depan.  
- Menyusun dokumentasi proyek secara sistematis dan informatif.  

> 💬 *“Proyek ini bukan hanya tugas, tapi juga bukti kemandirian dan dedikasi saya dalam memahami alur pembuatan aplikasi web yang terstruktur.”* 🍪


---

## 6️⃣ Mockup Project
Berikut merupakan penjelasan visual berdasarkan rancangan tampilan website **Kue Kering 3 Berlian**.

---

# 🖥️ Slide 1 — Login Page
**Judul:** *Halaman Login — Autentikasi Pengguna*

### 📸 Deskripsi Visual:
Form login di sisi kanan, logo Kue Kering 3 Berlian di kiri, input *Username* dan *Password*, tombol *Sign In*, dan opsi *Stay signed in*.

### 🎯 Tujuan:
Menjelaskan sistem autentikasi pengguna sebelum masuk dashboard.

### 💡 Penjelasan:
- Username & password diverifikasi ke database.  
- Jika valid, sistem membuat sesi login.  
- Password disimpan dalam bentuk hash (bcrypt).  
- Opsi “Stay signed in” membuat sesi bertahan menggunakan cookie.

---

# 🧭 Slide 2 — Dashboard / Home
**Judul:** *Dashboard Admin — Ringkasan & Navigasi*

### 📸 Deskripsi Visual:
Menampilkan logo besar, sidebar navigasi kiri (Dashboard, Sistem Manager, Master Data, dll), dan header dengan search bar.

### 💡 Penjelasan:
- Dashboard adalah pusat kontrol admin.  
- Sidebar berfungsi untuk berpindah antar modul.  
- Area tengah menampilkan info umum dan aktivitas terbaru.

---

# 🔐 Slide 3 — Role Management
**Judul:** *Role Management — Kontrol Akses Berbasis Peran*

### 📸 Deskripsi Visual:
Tabel dengan kolom **Role Id**, **Name**, **Status**, dan tombol **CREATE NEW**.

### 💡 Penjelasan:
- Digunakan untuk mengatur hak akses pengguna.  
- Admin bisa menambah, edit, atau menonaktifkan role.  
- Struktur tabel `roles` menyimpan nama dan status aktif.  
- Menggunakan middleware untuk memeriksa akses tiap role.

> “Dengan Role Management, admin dapat memastikan tiap user hanya mengakses fitur sesuai kewenangannya.”

---

# 👥 Slide 4 — User Management
**Judul:** *User Management — Kelola Data Pengguna*

### 📸 Deskripsi Visual:
Tabel berisi **User Id**, **Name**, **Role**, **Status**, dan **Last Login**.

### 💡 Penjelasan:
- Admin bisa menambah user baru atau ubah status aktif.  
- Password disimpan aman dengan hashing.  
- Dapat melacak kapan terakhir user login.  
- Endpoint CRUD: `/api/users`.

---

# 🧩 Slide 5 — Menu Management
**Judul:** *Menu Management — Mengatur Struktur Navigasi Aplikasi*

### 📸 Deskripsi Visual:
Tabel dengan kolom **Menu Id**, **Name**, **Parent**, **Level**, **Sequence**, **Link**, **Icon**, dan **Status**.  
Sidebar kiri menampilkan hasil menu secara real-time.

### 💡 Penjelasan:
- Admin dapat menambah, ubah, dan atur urutan menu.  
- Struktur `parent_id` digunakan untuk menu bertingkat.  
- Query utama: `SELECT * FROM menus WHERE is_active=1 ORDER BY level, sequence`.  
- Validasi urutan & preview live di sidebar.

> “Menu Management memberikan fleksibilitas tinggi untuk menata navigasi sesuai kebutuhan organisasi.”

---

# 🧾 Slide 6 — Menu Editor
**Judul:** *Menu Editor — Formulir Membuat/Mengubah Menu*

### 📸 Deskripsi Visual:
Form dengan field: Menu Id, Name, Parent, Level, Sequence, Link, Icon, Tag1, Tag2, Status, dan tombol **SAVE / BACK**.

### 💡 Penjelasan:
- Menu Id unik dan wajib diisi.  
- Parent menentukan hierarki.  
- Sequence menentukan urutan tampil.  
- Icon menyesuaikan tampilan sidebar.  
- SAVE menyimpan ke database, BACK kembali ke daftar menu.

---

# ✨ Penutup
> “Website **Kue Kering 3 Berlian** adalah contoh penerapan konsep web development yang efisien dan modern.  
> Dengan struktur data rapi, navigasi dinamis, serta sistem manajemen pengguna yang aman, website ini mampu membantu usaha kecil menengah dalam mengelola dan memasarkan produk kue kering secara digital.”
