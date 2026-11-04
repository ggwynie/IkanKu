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

## Screenshot Aplikasi

### Admin Web Dashboard

#### Login Admin
<img src="screenshot/img346.jpg" alt="Login Admin" width="60%">

*Halaman login untuk admin mengakses dashboard pengelolaan platform*

---

#### Dashboard Home Admin
<img src="screenshot/img349.jpg" alt="Home Admin" width="80%">

*Dashboard utama menampilkan ringkasan aktivitas, pending verifikasi, live session, dan komplain*

---

#### Verifikasi Akun Jastip
<table>
<tr>
<td width="50%">
<img src="screenshot/img350.jpg" alt="Daftar Verifikasi" width="100%">
<br><b>Daftar Pengajuan Jastip</b>
</td>
<td width="50%">
<img src="screenshot/img353.jpg" alt="Detail Verifikasi" width="100%">
<br><b>Detail Verifikasi & Dokumen KTP</b>
</td>
</tr>
</table>

*Admin dapat mereview dan menyetujui/menolak pengajuan jastiper*

---

#### Moderasi Konten
<img src="screenshot/img356.jpg" alt="Moderasi" width="80%">

*Monitoring live session, deteksi pelanggaran, dan aksi moderasi*

---

#### Keuangan & Escrow
<table>
<tr>
<td width="50%">
<img src="screenshot/img359.jpg" alt="Dashboard Keuangan" width="100%">
<br><b>Dashboard Keuangan</b>
</td>
<td width="50%">
<img src="screenshot/img360.jpg" alt="Detail Transaksi" width="100%">
<br><b>Detail Transaksi Escrow</b>
</td>
</tr>
</table>

*Monitoring dana escrow dan persetujuan penarikan saldo jastiper*

---

#### Komplain & Dispute
<table>
<tr>
<td width="50%">
<img src="screenshot/img363.jpg" alt="Daftar Komplain" width="100%">
<br><b>Daftar Komplain Masuk</b>
</td>
<td width="50%">
<img src="screenshot/img366.jpg" alt="Detail Komplain" width="100%">
<br><b>Detail & Resolusi Komplain</b>
</td>
</tr>
</table>

*Admin mediasi dispute dan proses refund*

---

#### Logistik & Tracking
<table>
<tr>
<td width="50%">
<img src="screenshot/img369.jpg" alt="Logistik" width="100%">
<br><b>Manajemen Logistik</b>
</td>
<td width="50%">
<img src="screenshot/img370.jpg" alt="Profile Admin" width="100%">
<br><b>Profile Admin</b>
</td>
</tr>
</table>

*Tracking pengiriman dan manajemen kurir*

---

### User Mobile App

#### Login & Register User
<table>
<tr>
<td width="33%">
<img src="screenshot/img244.jpg" alt="Login Before" width="100%">
<br><b>Login (Before)</b>
</td>
<td width="33%">
<img src="screenshot/img467.jpg" alt="Login After" width="100%">
<br><b>Login & Register (After)</b>
</td>
<td width="33%">
<img src="screenshot/img248.jpg" alt="Beranda" width="100%">
<br><b>Halaman Beranda</b>
</td>
</tr>
</table>

*Perbaikan UX pada login dan tampilan beranda dengan live session aktif*

---

#### Jastip & Live Streaming
<table>
<tr>
<td width="33%">
<img src="screenshot/img252.jpg" alt="Jastip List" width="100%">
<br><b>Halaman Jastip</b>
</td>
<td width="33%">
<img src="screenshot/img256.jpg" alt="Live Before" width="100%">
<br><b>Isi Live (Before)</b>
</td>
<td width="33%">
<img src="screenshot/img470.jpg" alt="Live After" width="100%">
<br><b>Isi Live (After)</b>
</td>
</tr>
</table>

*Browse jastiper dan menonton live streaming dari pasar*

---

#### Katalog & Chat
<table>
<tr>
<td width="50%">
<img src="screenshot/img260.jpg" alt="Katalog" width="100%">
<br><b>Katalog Ikan di Live</b>
</td>
<td width="50%">
<img src="screenshot/img277.jpg" alt="Chat" width="100%">
<br><b>Chat dengan Jastiper</b>
</td>
</tr>
</table>

*Browse produk dan komunikasi langsung dengan jastiper*

---

#### Checkout & Pemesanan
<table>
<tr>
<td width="33%">
<img src="screenshot/img264.jpg" alt="Checkout" width="100%">
<br><b>Halaman Checkout</b>
</td>
<td width="33%">
<img src="screenshot/img269.jpg" alt="Success" width="100%">
<br><b>Pemesanan Berhasil</b>
</td>
<td width="33%">
<img src="screenshot/img272.jpg" alt="Detail Order" width="100%">
<br><b>Detail Pemesanan</b>
</td>
</tr>
</table>

*Proses checkout dengan kalkulasi otomatis dan konfirmasi pesanan*

---

#### Profile & Pesanan
<table>
<tr>
<td width="33%">
<img src="screenshot/img284.jpg" alt="Profile" width="100%">
<br><b>Profile User</b>
</td>
<td width="33%">
<img src="screenshot/img288.jpg" alt="My Orders" width="100%">
<br><b>Pesanan Saya</b>
</td>
<td width="33%">
<img src="screenshot/img292.jpg" alt="Track" width="100%">
<br><b>Lacak Pesanan</b>
</td>
</tr>
</table>

*Manajemen profile dan tracking pesanan real-time*

---

#### WavePay E-Wallet
<table>
<tr>
<td width="33%">
<img src="screenshot/img297.jpg" alt="WavePay" width="100%">
<br><b>WavePay Dashboard</b>
</td>
<td width="33%">
<img src="screenshot/img302.jpg" alt="Top Up" width="100%">
<br><b>Isi Saldo</b>
</td>
<td width="33%">
<img src="screenshot/img307.jpg" alt="Payment" width="100%">
<br><b>Payment Gateway</b>
</td>
</tr>
</table>

*E-wallet internal untuk transaksi dalam aplikasi*

---

#### Notifikasi
<img src="screenshot/img314.jpg" alt="Notifikasi" width="40%">

*Notifikasi real-time untuk update status pesanan*

---

### Jastiper Mobile App

#### Register & Login Jastiper
<table>
<tr>
<td width="33%">
<img src="screenshot/img319.jpg" alt="Register Jastiper" width="100%">
<br><b>Daftar Jadi Jastiper</b>
</td>
<td width="33%">
<img src="screenshot/img330.jpg" alt="Login Jastiper" width="100%">
<br><b>Login Jastiper</b>
</td>
<td width="33%">
<img src="screenshot/img332.jpg" alt="Home Jastiper" width="100%">
<br><b>Beranda Jastiper</b>
</td>
</tr>
</table>

*Pendaftaran dengan verifikasi dokumen dan dashboard jastiper*

---

#### Live Streaming Jastiper
<table>
<tr>
<td width="33%">
<img src="screenshot/img335.jpg" alt="Live Before" width="100%">
<br><b>Live Jastiper (Before)</b>
</td>
<td width="33%">
<img src="screenshot/img475.jpg" alt="Live After" width="100%">
<br><b>Live Jastiper (After)</b>
</td>
<td width="33%">
<img src="screenshot/img336.jpg" alt="Katalog" width="100%">
<br><b>Katalog Produk</b>
</td>
</tr>
</table>

*Jastiper dapat memulai live dan menampilkan katalog produk*

---

#### Chat & Pesanan Jastiper
<table>
<tr>
<td width="50%">
<img src="screenshot/img337.jpg" alt="Chat" width="100%">
<br><b>Chat dengan Pembeli</b>
</td>
<td width="50%">
<img src="screenshot/img340.jpg" alt="Orders" width="100%">
<br><b>Daftar Pesanan</b>
</td>
</tr>
</table>

*Komunikasi dengan pembeli dan manajemen pesanan masuk*

---

#### Dashboard Keuangan Jastiper
<table>
<tr>
<td width="33%">
<img src="screenshot/img341.jpg" alt="Profile" width="100%">
<br><b>Profile Jastiper</b>
</td>
<td width="33%">
<img src="screenshot/img344.jpg" alt="Income" width="100%">
<br><b>Dashboard Pendapatan</b>
</td>
<td width="33%">
<img src="screenshot/img345.jpg" alt="Withdraw" width="100%">
<br><b>Tarik Saldo</b>
</td>
</tr>
</table>

*Monitoring pendapatan dan penarikan saldo ke rekening bank*

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
