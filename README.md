# Praktikum Pemrograman Web 2 - Pertemuan 2
# Ricko Syahputra
# NIM 24454010023
# prodi TI semester 5
# tanggal 17-09-2026

Markdown# Aplikasi Helpdesk - Praktikum Web 2

Repositori ini berisi proyek latihan dan praktikum pengembangan aplikasi web berbasis Laravel yang mengimplementasikan sistem manajemen tiket bantuan (Helpdesk) lengkap dengan relasi basis data, pencegahan masalah N+1 query, serta optimasi *eager loading*.

## 🛠 Spesifikasi Sistem & DBMS
* **Framework Backend:** Laravel 11 / 12
* **Bahasa Pemrograman:** PHP 8.2+
* **DBMS:** MySQL / MariaDB

---

## Konfigurasi `.env.example` (Tanpa Data Rahasia)
Berikut adalah contoh struktur konfigurasi lingkungan aplikasi:

```env
APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_helpdesk_latihan
DB_USERNAME=root
DB_PASSWORD=

Langkah Instalasi untuk Kloning Baru (Fresh Clone)Jika Anda melakukan clone proyek ini ke perangkat baru, jalankan perintah berikut secara berurutan di terminal:Instal Dependencies PHP:Bashcomposer install
Salin File Konfigurasi Lingkungan:Bashcopy .env.example .env
(Gunakan cp .env.example .env jika menggunakan sistem operasi Linux/macOS).Generate Kunci Aplikasi:Bashphp artisan key:generate
Buat Database Kosong:Buat database baru di MySQL/MariaDB sesuai dengan nama pada file .env (contoh: db_helpdesk_latihan).Jalankan Migrasi dan Seeder (Fresh & Seed):Bashphp artisan migrate:fresh --seed
Peringatan Penting: Perintah migrate:fresh akan menghapus dan mereset seluruh tabel yang ada di database Anda. Perintah php artisan db:seed secara standar hanya digunakan untuk mengisi data awal pada tabel yang masih kosong.   Jalankan Server Lokal:Bashphp artisan serve
Akses aplikasi melalui browser pada URL: http://127.0.0.1:8000/tickets
Dokumentasi dan Struktur Folder (docs/)Seluruh berkas bukti pendukung praktikum telah disimpan di dalam direktori docs/ pada repositori ini, yang meliputi:   ERD Helpdesk: Desain relasi entitas (docs/erd-helpdesk.png).   Kamus Data: Dokumentasi kolom dan tipe data tabel (docs/kamus-data.md).   Bukti Migrasi & Seeder: Log pengujian jumlah data konsisten [10, 3, 50, 100] dari dua sesi pengujian terpisah.   Laporan Query: Analisis perbandingan jumlah query antara Lazy Loading (N+1 problem) dan Eager Loading (with) untuk parameter N=10 serta N=20.   
