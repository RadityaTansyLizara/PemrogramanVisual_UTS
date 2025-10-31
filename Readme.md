| Variable | Isi |
| -------- | --- |
| Nama | RADITYA TANSY LIZARA  |
| NIM | 312310454 |
| Kelas | TI.23.A5 |
| Mata Kuliah | Pemrograman Visual (Desktop) |

# KUE KERING 3 BERLIAN

## Pembuatan Website E-Commerce & Admin Panel untuk Usaha Kue Kering
### Proyek ini dibuat sebagai Tugas Ujian Tengah Semester (UTS) Mata Kuliah Pemrograman Visual (Desktop), Universitas Pelita Bangsa.

## Ringkasan Proyek

### Kue Kering 3 Berlian adalah website yang menyediakan katalog produk kue kering beserta panel administrasi untuk mengelola data produk, pengguna, dan pengaturan sistem. Tujuan proyek ini adalah menerapkan konsep web development dasar hingga menengah: antarmuka pengguna (UI), autentikasi, manajemen peran (role management), dan struktur aplikasi yang rapi.

## Slide 1 — Halaman Login (File: docs/slides/01-login.png)

#### Judul slide: Halaman Login — Autentikasi Pengguna

#### Gambar: Tampilan login sederhana di sisi kanan layar dengan logo KueCute (atau brand Kue Kering 3 Berlian), kolom Username, Password, checkbox Stay signed in, tombol Sign In, serta opsi sign-in lewat social icons.

#### Tujuan slide: Menjelaskan proses autentikasi dasar dan tata letak antarmuka login.

## Poin yang disampaikan:

### 1. Desain UI
#### Fokus pada kesederhanaan dan kemudahan penggunaan: form diletakkan di posisi yang mudah terlihat, label jelas, ikon user & lock untuk aksesibilitas visual.

### 2. Fungsionalitas
#### Pengguna memasukkan username/password → tombol Sign In mengirimkan request POST ke endpoint /auth/login.

### 3. Keamanan
#### - Password disimpan dalam bentuk hash (mis. bcrypt). 
#### - Opsi "Stay signed in" merepresentasikan cookie durable — implementasikan dengan hati-hati (token refresh, masa berlaku). 
#### - Batasi percobaan login berulang (rate limiting).

### 4. UX tambahan
#### Tautan Forgot password? (opsional), informasi kesalahan tampilkan ramah (jangan menunjukkan apakah username valid).

#### “Di slide ini terlihat antarmuka login. Menempatkan form di posisi yang mudah ditemukan agar pengguna segera dapat masuk. Setelah mengklik Sign In, sistem akan memverifikasi kredensial di server, melakukan hashing pada password, dan menginisialisasi session. Untuk keamanan, Direkomendasikan menerapkan rate limiting serta reset password yang aman.”


## Slide 2 — Dashboard / Home (File: docs/slides/02-dashboard.png)

#### Judul slide: Dashboard Admin — Ringkasan & Navigasi

#### Gambar: Tampilan dashboard dengan logo besar di tengah, sidebar kiri berisi menu (Dashboard, Sistem Manager, cakecute, Master Data, dsb), header top dengan nama perusahaan dan search bar.

#### Tujuan slide: Menunjukkan tampilan utama admin setelah login, struktur navigasi, dan branding.

## Poin yang disampaikan:

### 1. Branding & Layout
#### - Bagian tengah menampilkan banner/brand besar (branding Kue Kering 3 Berlian) untuk konsistensi identitas.
#### - Sidebar kiri untuk navigasi modul — memudahkan akses ke fungsi manajemen.

### 2. Navigasi
#### - Menu terstruktur: Dashboard, Sistem Manager, Master Data, Utility, Documents, Administration Tools, Developer Area.
#### - Item yang bersarang (mis. Setup → User Management, Role Management) memudahkan pengelompokan fungsi.

### 3. Pengalaman pengguna (UX)
#### - Search bar untuk pencarian dokumen/produk.
#### - Breadcrumb (Home / Dashboard) untuk memberi konteks lokasi pengguna.

### 4. Fungsionalitas yang dapat ditunjukkan saat demo
#### - Menunjukkan klik pada menu → pindah ke modul Role Management.
#### - Demo notifikasi atau quick links jika ada.

### 5. Teknis
#### - Komponen sisi frontend: partial views untuk header, sidebar, content area sehingga mudah maintain.
#### - Penggunaan template engine (mis. Blade, Twig, atau simple PHP include) untuk konsistensi layout.

#### “Ini adalah dashboard setelah admin masuk. Sidebar di kiri memuat seluruh modul utama, sedangkan area tengah digunakan untuk menampilkan info banner dan ringkasan. Struktur layout dibuat modular sehingga setiap bagian (header/sidebar/content) dapat di-reuse di halaman lain.”


## Slide 3 — Sistem Manager → Setup → Role Management (File: docs/slides/03-role-management.png)

#### Judul slide: Role Management — Kontrol Akses Berbasis Peran

#### Gambar: Tabel daftar role berisi kolom Action (ikon edit, delete, permission), Role Id (ADMIN, IT DEV), Name (ADMINISTRATOR, IT DEV), status toggle; tombol CREATE NEW di pojok kanan atas; kotak Search dan pagination.

#### Tujuan slide: Menjelaskan implementasi manajemen peran (role) untuk sistem keamanan dan pembagian hak akses.

## Poin yang disampaikan:

### 1. Fungsi utama
#### - Menambah, mengubah, menonaktifkan atau menghapus role.
#### - Menetapkan hak akses/perizinan (permissions) terkait tiap modul.

### 2. Tata letak & operasi
#### - Kolom Action: ikon edit (ubah role), ikon delete (hapus), ikon permission (atur hak akses).
#### - Kolom Status: checkbox/toggle untuk menonaktifkan role sementara.
#### - Create New membuka form modal untuk menambah role baru (Role ID, Name, Deskripsi).

### 3. Alur data & teknis
#### - Saat Create atau Edit → server memvalidasi data → menyimpan ke tabel roles di DB.

### 4. Struktur tabel (contoh minimal):
#### - roles (id INT PK, role_id VARCHAR UNIQUE, name VARCHAR, description TEXT, is_active TINYINT, created_at, updated_at)
#### - role_permissions (id, role_id_fk, permission_key)
#### - Penerapan middleware: setiap route menggunakan pengecekan role → menentukan akses (RBAC).

### 5. UX & admin convenience
#### - Fitur pencarian dan pagination agar admin dapat mengelola banyak role.
#### - Konfirmasi sebelum delete, riwayat perubahan (audit log) untuk keamanan.

### 6. Demonstrasi
#### - Tunjukkan click Create New → isi form → simpan → periksa baris baru di tabel.
#### - Tunjukkan edit & toggle status untuk menonaktifkan role.

#### “Slide ini menampilkan modul Role Management. Kami menerapkan RBAC sederhana: role disimpan pada tabel roles, dan permission dihubungkan lewat role_permissions. Admin dapat membuat role baru, mengubahnya, serta mengaktifkan/menonaktifkan role sesuai kebutuhan. Ini membantu menjaga keamanan akses ke modul sensitif.”


## Slide 4 — User Management (Tampilan: daftar user)

### Judul slide: User Management — Mengelola Pengguna & Status Akses

### Deskripsi visual singkat:
#### Tampilan berupa tabel yang menunjukkan daftar pengguna (User Id, Name, Role Id, Status, Login Status, Last Login) dengan tombol aksi (edit, delete) dan tombol CREATE NEW di kanan atas. Terdapat fitur pencarian dan filter.

### Tujuan:
#### Menunjukkan bagaimana admin dapat menambah, mengubah, menonaktifkan, atau menghapus akun pengguna serta memantau status login terakhir.

### Penjelasan detail:

### 1. Kolom & Artinya
#### a.) Action: tombol untuk mengedit (ikon pensil) atau menghapus (ikon silang). Klik edit membuka form user, klik delete memunculkan konfirmasi.
#### b.) User Id: username unik yang dipakai untuk login (mis. adminit, stafit).
#### c.) Name: nama lengkap atau label deskriptif (mis. “Admin IT”).
#### d.) Role Id: referensi ke role (mis. IT DEV) — menentukan hak akses user.
#### e.) Status: checkbox atau toggle yang menandakan akun aktif/non-aktif. Non-aktif berarti user tidak bisa masuk.
#### f.) Login Status: menandakan apakah user sedang login saat ini (session aktif).
#### g.) Last Login: timestamp terakhir user berhasil masuk (bisa null jika belum pernah login).

### 2. Fungsi utama & alur kerja
#### a.) Create New → buka modal/form untuk menambah akun baru (username, nama, email, role, password, status).
#### b.) Edit → ubah profil dan role. Jika perlu, admin dapat mereset password.
#### c.) Toggle Status → menonaktifkan sementara akun tanpa menghapus datanya (recommended untuk audit trail).
#### d.) Delete → hapus permanen (harus konfirmasi & idealnya ada soft-delete).

### 3. Integrasi teknis
#### Tabel backend: users (id, username, name, email, password_hash, role_id, is_active, last_login, created_at, updated_at).

### 4. Endpoint contoh:
#### a.) GET /api/users — daftar user (support filter/pagination).
#### b.) POST /api/users — create user (validasi unik username/email).
#### c.) PUT /api/users/:id — update user.
#### d.) PATCH /api/users/:id/status — toggle status.
#### e.) DELETE /api/users/:id — hapus user (soft delete disarankan).

### 5. Keamanan & validasi
#### a.) Password harus disimpan hashed (bcrypt/argon2).
#### b.) Validasi server-side: unique username/email, minimum password policy.
#### c.)Batasi akses endpoint dengan middleware RBAC (hanya admin dengan hak tertentu).
#### d.) Logging/audit: simpan riwayat perubahan (who, when, what) untuk setiap perubahan user.

### 6. UX & aksesibilitas
#### a.) Tampilkan konfirmasi sebelum tindakan destruktif.
#### b.) Berikan pesan sukses/error yang jelas (mis. “User berhasil dibuat”, “Email sudah terdaftar”).
#### c.) Fitur pencarian & filter membantu manajemen di organisasi besar.

#### “Di sini admin dapat melihat semua akun terdaftar. Fitur pentingnya adalah ability untuk menonaktifkan sementara (toggle status) dan melihat siapa terakhir kali login. Semua aksi tervalidasi di server dan hanya bisa diakses oleh admin berwenang.”


## Slide 5 — Menu Management
### Mengatur Struktur Navigasi Aplikasi

### Deskripsi Visual:
#### - Tampilan berisi daftar menu aplikasi dalam bentuk tabel — menampilkan Menu ID, Name, Parent, Level, Sequence, Link, Icon, dan Status.
#### - Tombol “CREATE NEW” digunakan untuk menambah menu baru, dan sidebar kiri menampilkan hasil konfigurasi secara real-time.

### Tujuan:
#### Memberikan kendali penuh bagi admin untuk mengatur struktur navigasi aplikasi, mulai dari menambah menu baru, menentukan parent-child, mengatur urutan tampil (sequence), hingga menambahkan ikon dan link.

### 1. Penjelasan Kolom Utama:
#### a.) Menu ID: Identitas unik setiap menu.
#### b.) Name: Nama menu yang tampil di UI.
#### c.) Parent: Menu induk jika sub-menu, kosong jika top-level.
#### d.) Level: Kedalaman menu (0 = utama).
#### e.) Sequence: Urutan tampil di sidebar.
#### f.) Link: Halaman tujuan saat diklik.
#### g.) Icon: Kelas ikon untuk tampilan menu.
#### h.) Status: Menentukan apakah menu aktif atau disembunyikan.

### 2. Fungsi Utama:
#### a.) Create New: Tambah menu baru.
#### b.) Edit: Ubah label, link, atau urutan.
#### c.) Parent & Level: Menata struktur menu bertingkat.
#### d.) Status: Langsung memengaruhi tampilan menu di sidebar.

### 3. Struktur Data & Database:
#### a.) Data menu disimpan di tabel menus yang menyimpan semua informasi menu.
#### b.) Relasi parent-child diatur melalui parent_id, membentuk struktur bertingkat.
#### c.) Kolom sequence mengatur urutan, dan is_active menentukan menu aktif atau tidak.
#### d.) Struktur ini memudahkan sistem menampilkan menu secara dinamis tanpa pengaturan manual di kode.

### 4. Teknis & UX:
#### a.) Frontend menampilkan menu aktif berdasarkan level dan urutan.
#### b.) Prosesnya menggunakan tree builder agar membentuk struktur menu otomatis.
#### c.) Tersedia preview live dan validasi urutan, supaya hasil tampilan selalu rapi dan konsisten.

#### “Menu Management memberi keleluasaan admin untuk menyusun navigasi aplikasi — menambah menu, mengatur urutan, serta menentukan ikon dan link. Setiap perubahan langsung terlihat di sidebar, sehingga tampilan aplikasi dapat disesuaikan dengan kebutuhan organisasi.”


## Slide 6 — Menu Editor (Form input menu)

### Judul slide: Menu Editor — Formulir Membuat/Mengubah Menu

### Deskripsi visual singkat:
Form berlabel “General Info” berisi field: Menu Id, Name, Parent (dropdown), Level, Sequence, Link, Icon, Tag1, Tag2, Status (toggle), dan tombol SAVE / BACK.

Tujuan:
Menjelaskan tiap field, aturan pengisian, dan alur validasi untuk memastikan menu konsisten dan tidak merusak navigasi.

Penjelasan field-by-field:

Menu Id

Identifier unik (string). Bisa auto-generated atau format manual (mis. M10000).

Validasi: unik, tidak boleh kosong.

Name

Label yang tampil di UI. Support i18n jika aplikasi multi-bahasa.

Validasi: tidak kosong, panjang maksimum (mis. 100 char).

Parent

Dropdown berisi daftar menu yang bisa dipilih sebagai parent. Pilih Select Parent Menu jika top-level.

Catatan: saat memilih parent, Level sebaiknya dihitung otomatis (parent.level + 1).

Level

Menunjukkan kedalaman. Bila parent dipilih, isi otomatis; admin dapat override jika perlu (tapi tidak disarankan).

Validasi: integer >= 0.

Sequence

Nomor urut tampil. Sistem dapat memberikan opsi auto-fill (mis. atur ke paling akhir).

Validasi: integer positif.

Link

Route atau URL yang dituju. Bisa internal route (/admin/users) atau external URL.

Validasi: jika internal, periksa keberadaan route; jika eksternal, validasi format URL.

Icon

String kelas icon (FontAwesome contoh). Admin bisa melihat preview ikon saat mengetik.

UX: sediakan picker ikon untuk kemudahan.

Tag1 / Tag2

Opsional: untuk keperluan styling atau menandai menu (warna, badge).

Misal Tag1 = warna background kecil di menu.

Status (toggle)

Menentukan apakah menu aktif. Non-aktif menyembunyikan menu dari UI.

Buttons

SAVE: submit form (server-side validasi + simpan ke DB). Berikan feedback (success / error).

BACK: kembali ke daftar menu tanpa menyimpan.

Alur validasi & UX tambahan:

Gunakan validasi real-time di form (client-side) dan cek ulang di server.

Tampilkan pesan kesalahan dekat field terkait.

Saat menyimpan, gunakan transaksi DB bila menyertakan multiple updates (mis. reorder sequence).

Setelah simpan, redirect ke Menu Management dan tampilkan toast: “Menu berhasil disimpan”.

Script presentasi singkat:

“Menu Editor adalah tempat konfigurasi detail tiap item navigasi. Field Parent dan Sequence penting untuk membuat struktur yang rapi—kami juga menyarankan preview ikon dan validasi route agar admin tidak memasukkan link rusak.”
