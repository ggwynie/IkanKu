# IKANKU - Platform Jasa Titip Hasil Laut

<div align="center">

![Platform Status](https://img.shields.io/badge/Status-Prototype-blue)
![Platform](https://img.shields.io/badge/Platform-Web%20%26%20Mobile-green)
![Design](https://img.shields.io/badge/Design-User--Centered-orange)

**Platform Informasi Harga dan Jasa Titip Hasil Laut Berbasis User-Centered Design**

</div>

---

## Daftar Isi

- [Tentang Proyek](#tentang-proyek)
- [Latar Belakang](#latar-belakang)
- [Permasalahan yang Diselesaikan](#permasalahan-yang-diselesaikan)
- [Fitur Utama](#fitur-utama)
- [Teknologi](#teknologi)
- [Arsitektur Sistem](#arsitektur-sistem)
- [Screenshot](#screenshot)
- [Tim Pengembang](#tim-pengembang)
- [Lisensi](#lisensi)

---

## Tentang Proyek

**IKANKU** adalah platform multi-platform (Website Admin & Mobile App) yang menghubungkan konsumen urban dengan hasil tangkapan laut segar dari Muara Karang melalui sistem Jasa Titip (Jastip) yang terverifikasi. Platform ini dikembangkan menggunakan pendekatan **User-Centered Design (UCD)** untuk memastikan antarmuka yang inklusif dan mudah digunakan.

### Tujuan Proyek

1. **Transparansi Harga** - Menyediakan informasi harga ikan real-time yang akurat dan mudah diakses
2. **Akses Produk Segar** - Memfasilitasi jasa titip dari Muara Karang untuk konsumen urban yang sibuk
3. **Edukasi Konsumen** - Memberikan panduan memilih dan membedakan jenis ikan segar

---

## Latar Belakang

Indonesia memiliki potensi maritim yang sangat besar dengan garis pantai terpanjang kedua di dunia (99.083 km), namun:

- **Rantai distribusi panjang**: Nelayan → Pengepul → Pedagang → Konsumen
- **Ketimpangan margin**: Nelayan dapat porsi keuntungan terkecil
- **Kesejahteraan rendah**: Rata-rata pendapatan nelayan hanya Rp 3.480.000/bulan
- **Resistensi digitalisasi**: Pedagang grosir menolak platform e-commerce konvensional

### Pivot Konsep

Platform awalnya dirancang sebagai marketplace-fintech masif, namun setelah riset lapangan di **Pasar Modern Muara Angke** dan **Kawasan Pesisir Muara Karang**, tim melakukan pivot ke model **Jasa Titip (Crowdsourced Delivery)** karena:

1. Tidak mengganggu ekosistem transaksi tradisional yang sudah berjalan
2. Mengatasi karakteristik produk laut yang mudah rusak
3. Mempertahankan sistem verifikasi berbasis kepercayaan (video call/foto)
4. Efektif memotong rantai distribusi tanpa memaksa digitalisasi penuh

---

## Permasalahan yang Diselesaikan

### 1. Ketidaktransparanan Harga
- **Masalah**: Konsumen tidak punya acuan harga wajar, rentan manipulasi
- **Solusi**: Grafik tren harga pasar harian per jenis ikan

### 2. Akses Produk Segar Terbatas
- **Masalah**: Jarak jauh, macet, waktu operasional pasar subuh
- **Solusi**: Sistem Jastip terverifikasi dengan live streaming dari pasar

### 3. Kurangnya Edukasi
- **Masalah**: Konsumen sulit membedakan ikan segar vs diawetkan
- **Solusi**: Direktori karakteristik fisik spesies ikan & tips kesegaran

---

## Fitur Utama

### Untuk Pembeli (User App)

| Fitur | Deskripsi |
|-------|-----------|
| Registrasi & Login | Autentikasi aman dengan validasi email |
| Live Streaming | Menonton jastiper live dari pasar real-time |
| Chat Real-Time | Komunikasi langsung dengan filter kata kasar otomatis |
| Katalog Ikan | Browse produk dengan detail harga & informasi kesegaran |
| Checkout Otomatis | Kalkulasi otomatis (Harga + Ongkir + Fee Jastip) |
| Escrow Payment | Dana ditahan sistem hingga barang diterima |
| Lacak Pesanan | Live tracking kurir dengan peta real-time |
| WavePay Wallet | E-wallet internal dengan top-up & riwayat transaksi |
| Notifikasi | Update status pesanan real-time |

### Untuk Jastiper (Jastip User App)

| Fitur | Deskripsi |
|-------|-----------|
| Pendaftaran Jastiper | Verifikasi identitas & dokumen oleh admin |
| Start Live Session | Streaming langsung dari lokasi pasar |
| Pin Produk Unggulan | Highlight produk pilihan saat live |
| Kelola Etalase | Manajemen katalog produk dengan foto & harga |
| Respon Order | Konfirmasi/tolak pesanan dengan verifikasi barang |
| Serah Terima | Validasi kode pesanan ke kurir dengan foto bukti |
| Dashboard Pendapatan | Laporan keuangan & penarikan saldo |

### Untuk Admin (Web Dashboard)

| Fitur | Deskripsi |
|-------|-----------|
| Verifikasi Akun Jastip | Review & approve pendaftaran jastiper |
| Moderasi Konten | Take down live, banned user melanggar |
| Keuangan & Escrow | Monitoring dana, approve penarikan saldo |
| Handle Komplain | Mediasi dispute & pengembalian dana |
| Logistik & Tracking | Manajemen kurir & monitoring pengiriman |
| Dashboard Analitik | Statistik transaksi & performa platform |

---

## Teknologi

### Mobile App
- **Framework**: Android Native (Kotlin)
- **UI/UX**: Material Design, Jetpack Compose
- **Networking**: Retrofit, OkHttp
- **Database**: Room Database (local cache)
- **Maps**: Google Maps SDK

### Web Admin
- **Frontend**: PHP, HTML5, CSS3, JavaScript
- **Framework**: Bootstrap 5
- **Backend**: PHP 7.4+
- **Database**: MySQL 8.0
- **Server**: XAMPP (Apache + MySQL)

### Design Tools
- **Prototyping**: Figma (High-Fidelity)
- **Low-Fi Prototype**: Paper Sketches
- **Diagram**: Draw.io (Use Case, Activity Diagram)
- **Database**: MySQL Workbench (ERD)

---

## Arsitektur Sistem

### Sistem Terintegrasi

```
┌─────────────────┐      ┌──────────────────┐      ┌─────────────────┐
│   User Mobile   │◄────►│  MySQL Database  │◄────►│  Admin Web      │
│   (Pembeli)     │      │   (IkanKu DB)    │      │  (Dashboard)    │
└─────────────────┘      └──────────────────┘      └─────────────────┘
         ▲                        ▲                          ▲
         │                        │                          │
         └────────────────────────┼──────────────────────────┘
                                  │
                         ┌────────▼────────┐
                         │ Jastiper Mobile │
                         │  (Live & Order) │
                         └─────────────────┘
```

### Database Schema (11 Tabel)

1. **users** - Data pengguna (pembeli, jastiper, admin)
2. **jastip** - Profil & verifikasi jastiper
3. **produk_etalase** - Katalog produk ikan
4. **live_sessions** - Sesi live streaming
5. **jastip_orders** - Data pemesanan
6. **payments** - Transaksi & escrow
7. **pengiriman** - Status & tracking pengiriman
8. **kurir** - Data kurir
9. **chat_messages** - Pesan chat live
10. **komplain** - Laporan & dispute
11. **pengajuan_jastip** - Pengajuan verifikasi jastiper

---

## Screenshot

### Login & Register
<table>
<tr>
<td width="50%">
<b>Login (Before)</b><br>
<img src="screenshot/img244.jpg" alt="Login Before" width="100%">
</td>
<td width="50%">
<b>Login & Register (After)</b><br>
<img src="screenshot/img467.jpg" alt="Login After" width="100%">
</td>
</tr>
</table>

*Perbaikan: Penambahan validasi real-time, perbaikan UX form, dan integrasi dengan sistem escrow*

---

### User App - Beranda & Jastip

<table>
<tr>
<td width="50%">
<b>Beranda User</b><br>
<img src="screenshot/img248.jpg" alt="Beranda" width="100%">
</td>
<td width="50%">
<b>Halaman Jastip</b><br>
<img src="screenshot/img252.jpg" alt="Jastip List" width="100%">
</td>
</tr>
</table>

*Fitur: Live session aktif, katalog jastiper terverifikasi, pencarian & filter*

---

### Live Streaming & Katalog

<table>
<tr>
<td width="33%">
<b>Isi Live Before</b><br>
<img src="screenshot/img256.jpg" alt="Live Before" width="100%">
</td>
<td width="33%">
<b>Isi Live After</b><br>
<img src="screenshot/img470.jpg" alt="Live After" width="100%">
</td>
<td width="33%">
<b>Katalog Live</b><br>
<img src="screenshot/img260.jpg" alt="Katalog" width="100%">
</td>
</tr>
</table>

*Perbaikan: Data realistis, tampilan produk lebih informatif, integrasi chat real-time*

---

### Checkout & Pembayaran

<table>
<tr>
<td width="33%">
<b>Checkout</b><br>
<img src="screenshot/img264.jpg" alt="Checkout" width="100%">
</td>
<td width="33%">
<b>Proses Berhasil</b><br>
<img src="screenshot/img269.jpg" alt="Success" width="100%">
</td>
<td width="33%">
<b>Detail Pesanan</b><br>
<img src="screenshot/img272.jpg" alt="Order Detail" width="100%">
</td>
</tr>
</table>

*Fitur: Kalkulasi otomatis, escrow payment, konfirmasi order real-time*

---

### Chat & Komunikasi

<table>
<tr>
<td width="100%">
<b>Fitur Chat Jastip</b><br>
<img src="screenshot/img277.jpg" alt="Chat" width="50%">
</td>
</tr>
</table>

*Fitur: Chat real-time, filter kata kasar otomatis, riwayat percakapan*

---

### Profile & Pesanan

<table>
<tr>
<td width="33%">
<b>Profile User</b><br>
<img src="screenshot/img284.jpg" alt="Profile" width="100%">
</td>
<td width="33%">
<b>Pesanan Saya</b><br>
<img src="screenshot/img288.jpg" alt="My Orders" width="100%">
</td>
<td width="33%">
<b>Lacak Pesanan</b><br>
<img src="screenshot/img292.jpg" alt="Track Order" width="100%">
</td>
</tr>
</table>

*Fitur: Edit profile, riwayat pesanan, live tracking dengan map*

---

### WavePay E-Wallet

<table>
<tr>
<td width="33%">
<b>WavePay Dashboard</b><br>
<img src="screenshot/img297.jpg" alt="WavePay" width="100%">
</td>
<td width="33%">
<b>Isi Saldo</b><br>
<img src="screenshot/img302.jpg" alt="Top Up" width="100%">
</td>
<td width="33%">
<b>Payment Gateway</b><br>
<img src="screenshot/img307.jpg" alt="Payment" width="100%">
</td>
</tr>
</table>

*Fitur: E-wallet internal, top-up, riwayat transaksi, integrasi payment gateway*

---

### Notifikasi

<table>
<tr>
<td width="100%">
<b>Notifikasi Real-Time</b><br>
<img src="screenshot/img314.jpg" alt="Notifikasi" width="50%">
</td>
</tr>
</table>

*Fitur: Update status pesanan, promo, informasi penting real-time*

---

### Jastiper App

<table>
<tr>
<td width="33%">
<b>Daftar Jadi Jastiper</b><br>
<img src="screenshot/img319.jpg" alt="Register Jastiper" width="100%">
</td>
<td width="33%">
<b>Login Jastiper</b><br>
<img src="screenshot/img330.jpg" alt="Login Jastiper" width="100%">
</td>
<td width="33%">
<b>Beranda Jastiper</b><br>
<img src="screenshot/img332.jpg" alt="Home Jastiper" width="100%">
</td>
</tr>
</table>

*Fitur: Pendaftaran terverifikasi, dashboard khusus jastiper*

---

### Jastiper - Live & Katalog

<table>
<tr>
<td width="33%">
<b>Live Jastiper Before</b><br>
<img src="screenshot/img335.jpg" alt="Live Jastiper Before" width="100%">
</td>
<td width="33%">
<b>Live Jastiper After</b><br>
<img src="screenshot/img475.jpg" alt="Live Jastiper After" width="100%">
</td>
<td width="33%">
<b>Katalog Jastiper</b><br>
<img src="screenshot/img336.jpg" alt="Katalog Jastiper" width="100%">
</td>
</tr>
</table>

*Perbaikan: UI lebih intuitif, data realistis, kontrol streaming lebih baik*

---

### Jastiper - Chat & Order

<table>
<tr>
<td width="50%">
<b>Chat dengan Pembeli</b><br>
<img src="screenshot/img337.jpg" alt="Chat Jastiper" width="100%">
</td>
<td width="50%">
<b>Daftar Pesanan</b><br>
<img src="screenshot/img340.jpg" alt="Order List" width="100%">
</td>
</tr>
</table>

*Fitur: Respon order real-time, verifikasi ketersediaan barang*

---

### Jastiper - Dashboard & Keuangan

<table>
<tr>
<td width="33%">
<b>Profile Jastiper</b><br>
<img src="screenshot/img341.jpg" alt="Profile Jastiper" width="100%">
</td>
<td width="33%">
<b>Dashboard Pendapatan</b><br>
<img src="screenshot/img344.jpg" alt="Dashboard Income" width="100%">
</td>
<td width="33%">
<b>Tarik Saldo</b><br>
<img src="screenshot/img345.jpg" alt="Withdraw" width="100%">
</td>
</tr>
</table>

*Fitur: Laporan keuangan lengkap, unduh PDF, penarikan saldo ke bank*

---

### Admin Dashboard

<table>
<tr>
<td width="50%">
<b>Login Admin</b><br>
<img src="screenshot/img346.jpg" alt="Admin Login" width="100%">
</td>
<td width="50%">
<b>Home Dashboard</b><br>
<img src="screenshot/img349.jpg" alt="Admin Home" width="100%">
</td>
</tr>
</table>

*Platform: Web-based admin panel dengan statistik lengkap*

---

### Verifikasi Jastip

<table>
<tr>
<td width="50%">
<b>Daftar Verifikasi</b><br>
<img src="screenshot/img350.jpg" alt="Verification List" width="100%">
</td>
<td width="50%">
<b>Detail Verifikasi</b><br>
<img src="screenshot/img353.jpg" alt="Verification Detail" width="100%">
</td>
</tr>
</table>

*Fitur: Review dokumen, approve/reject dengan alasan, notifikasi otomatis*

---

### Moderasi & Banned

<table>
<tr>
<td width="100%">
<b>Moderasi Konten</b><br>
<img src="screenshot/img356.jpg" alt="Moderation" width="50%">
</td>
</tr>
</table>

*Fitur: Take down live session, banned user, riwayat pelanggaran*

---

### Keuangan & Escrow

<table>
<tr>
<td width="50%">
<b>Dashboard Keuangan</b><br>
<img src="screenshot/img359.jpg" alt="Finance Dashboard" width="100%">
</td>
<td width="50%">
<b>Detail Transaksi</b><br>
<img src="screenshot/img360.jpg" alt="Transaction Detail" width="100%">
</td>
</tr>
</table>

*Fitur: Monitoring escrow, approve penarikan saldo, laporan keuangan*

---

### Komplain & Dispute

<table>
<tr>
<td width="50%">
<b>Daftar Komplain</b><br>
<img src="screenshot/img363.jpg" alt="Complaint List" width="100%">
</td>
<td width="50%">
<b>Detail & Resolusi</b><br>
<img src="screenshot/img366.jpg" alt="Complaint Detail" width="100%">
</td>
</tr>
</table>

*Fitur: Handle dispute, mediasi, approve refund, dokumentasi resolusi*

---

### Logistik & Tracking

<table>
<tr>
<td width="50%">
<b>Logistik Management</b><br>
<img src="screenshot/img369.jpg" alt="Logistic" width="100%">
</td>
<td width="50%">
<b>Profile Admin</b><br>
<img src="screenshot/img370.jpg" alt="Admin Profile" width="100%">
</td>
</tr>
</table>

*Fitur: Alokasi kurir, live tracking, update status pengiriman*

---

## Fitur Aksesibilitas

Platform IKANKU dirancang dengan prinsip **inklusivitas** untuk pengguna dengan kebutuhan khusus:

### Typography
- Font size minimum: **16px** (body text)
- Line height: **1.5** untuk readability
- Font family: **Inter/Roboto** (high legibility)

### Color Contrast
- Rasio kontras minimum: **4.5:1** (WCAG AA)
- Primary: `#0066CC` on `#FFFFFF`
- Error: `#D32F2F` with icon support

### Touch Target
- Minimum size: **48x48px** (WCAG 2.1)
- Spacing: **8px** antar-elemen interaktif
- Suitable untuk pengguna dengan keterbatasan motorik

### Screen Reader Support
- Semantic HTML (`<header>`, `<nav>`, `<main>`)
- ARIA labels pada elemen interaktif
- Alt text deskriptif pada gambar

### Keyboard Navigation
- Tab order yang logis
- Focus indicator yang jelas
- Skip to main content link

---

## Metodologi Pengembangan

### Data Gathering
- **Survei Lapangan**: Pasar Modern Muara Angke & Muara Karang
- **Wawancara**: Nelayan, pedagang grosir, konsumen urban
- **Kuesioner**: 100+ responden (fokus konsumen)

### User Persona
- **Persona 1**: Ibu Rumah Tangga (35-45 tahun) - Butuh kesegaran & efisiensi waktu
- **Persona 2**: Mahasiswa/Pekerja Kantoran (22-35 tahun) - Harga transparan & praktis

### Design Process
```
Sketsa Low-Fi → Wireframe → High-Fi Prototype (Figma) → User Testing → Iterasi
```

### User Acceptance Testing (UAT)
- **Responden**: 20 pengguna (10 pembeli, 10 jastiper)
- **Metode**: Task-based observation + survey
- **Tools**: Google Form, screen recording
- **Hasil**: Rata-rata skor kegunaan **85%** (kategori "Sangat Baik")

### Iterasi Perbaikan
- Perbaikan halaman login (validasi & UX)
- Optimalisasi data realistis (harga, stok, waktu)
- Penyempurnaan alur checkout & payment
- Peningkatan responsivitas UI mobile

---

## Cara Menjalankan Proyek

### Prerequisites
- **Android Studio** (Arctic Fox atau lebih baru)
- **XAMPP** (Apache + MySQL)
- **PHP 7.4+**
- **MySQL 8.0**
- **Android Device/Emulator** (API 24+)

### Setup Database
1. Buka **phpMyAdmin** (`http://localhost/phpmyadmin`)
2. Import file `setup_database.sql` (jika tersedia)
3. Atau buat database manual dengan nama `ikanku_db`

### Setup Web Admin
```bash
# Manual setup (utility scripts sudah dihapus untuk production)
# 1. Copy file PHP ke C:\xampp\htdocs\IkanKu\
# 2. Import database dari phpMyAdmin
# 3. Update koneksi.php dengan kredensial database Anda

# Test koneksi
# Buka browser: http://localhost/IkanKu/test_koneksi.php
```

### Setup Mobile App
1. Open project di **Android Studio**
2. Sync Gradle dependencies
3. Update `BASE_URL` di konfigurasi (sesuaikan IP lokal)
4. Build & Run di device/emulator

### Login Credentials (Testing)
```
Admin:
Email: admin@ikanku.com
Password: admin123

Jastiper:
Email: jastiper@test.com
Password: jastiper123

User:
Email: user@test.com
Password: user123
```

---

## Tim Pengembang

Proyek ini dikembangkan sebagai Ujian Akhir Semester (UAS) Mata Kuliah **Interaksi Manusia & Komputer** - TIF18 4PTI1

| NIM | Nama | Role |
|-----|------|------|
| 32240155 | Febriani Adeline | UI/UX Designer & Researcher |
| 32240119 | **Gwyneth Eunice Widjaja** | Mobile Developer & System Analyst |
| 32240127 | Corinthia Angie | Database Designer & Backend |
| 32240144 | Chelsea Arlyn | Frontend Developer & Tester |

**Dosen Pengampu**: Jusia Amanda Ginting, S.Kom., M.Kom

**Institusi**: Universitas Bunda Mulia - Fakultas Teknologi dan Desain

---

## Dokumentasi Lengkap

Untuk dokumentasi lengkap, lihat:
- **Laporan IMK**.md - Laporan lengkap proyek (96 halaman)
- **Laporan IMK**.pdf - Versi PDF untuk presentasi
- [Figma Prototype](link-figma) - High-fidelity interactive prototype
- [Google Drive](link-gdrive) - Demo video, UAT results, wawancara

---

## Link Penting

- [Form Data Gathering (Konsumen)](link-gform-1)
- [Form Feedback User](link-gform-2)
- [Form Feedback Jastiper](link-gform-3)
- [Demo Admin & App](link-gdrive-demo)
- [Download APK](link-gdrive-apk)
- [Web Admin Demo](http://localhost/IkanKu/admin_dashboard.php)

---

## Lisensi

Project ini dikembangkan untuk keperluan akademik. Hak cipta dilindungi © 2025 Tim IKANKU - Universitas Bunda Mulia

---

## Ucapan Terima Kasih

Terima kasih kepada:
- Dosen pengampu yang telah membimbing
- Pedagang & nelayan Muara Angke dan Muara Karang
- Responden UAT yang telah memberikan feedback
- Seluruh pihak yang telah membantu proyek ini

---

<div align="center">

**Bersama IKANKU, Ikan Segar Langsung ke Tangan Anda**

Made with love by Tim IKANKU - Universitas Bunda Mulia

</div>
