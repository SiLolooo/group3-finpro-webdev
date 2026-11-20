# Group 3 - Kalkulator & Simulasi Jejak Karbon Listrik Rumah (SDG 7.3 & 13.3)

Final Project Web Development - HITLAB 26.2  
**Studi Kasus:** Jalur A — Rumah Tangga (Pencatatan kWh bulanan & perbandingan skenario pengurangan konsumsi listrik)

## Tim & Pembagian Peran
- **[Anggota 1]** - **Frontend 1 (Halaman Informasi & Form Input kWh)**  
  Membangun halaman utama, edukasi mode latihan, dropdown faktor emisi, dan form input catatan kWh bulanan rumah tangga.
- **[Anggota 2]** - **Frontend 2 (Tabel Riwayat CRUD, Ringkasan & Simulasi)**  
  Membangun tabel riwayat konsumsi (edit/hapus), kartu ringkasan total emisi per bulan, dan perbandingan skenario hemat energi (misal skenario pengurangan 20%).
- **[Anggota 3]** - **Frontend Logic & Integrasi (DOM & Fetch API)**  
  Menghubungkan antarmuka ke Backend API, mengatur validasi UI, state loading/empty/error, timestamp, serta logika simulasi tanpa menimpa catatan asli.
- **[Anggota 4]** - **Backend, API Contract & Deployment**  
  Membangun server Express.js (`GET /api/faktor-emisi`, `POST /api/emisi`, CRUD `/api/readings`), validasi input negatif, deploy Vercel, serta menjaga repositori GitHub.

## Konvensi Repositori
- **Struktur Folder:**
  - `/frontend` : Halaman antarmuka (HTML, Tailwind CSS, JavaScript)
  - `/backend` : Server API (Node.js & Express.js)
- **Aturan Git:**
  - Dilarang push langsung ke `main` setelah setup awal selesai.
  - Gunakan format branch: `feat/nama-fitur` (contoh: `feat/form-input`, `feat/api-readings`).
  - Lakukan Pull Request untuk menggabungkan kode ke `main`.

## Batasan Demo & Mode Latihan
- Aplikasi ini menggunakan faktor emisi sintetis berlabel **"latihan"** (`0.87 kg CO2/kWh`) untuk tujuan pembelajaran dan simulasi.
- Hasil perhitungan merupakan estimasi edukatif (SDG 7.3 & 13.3) dan bukan inventarisasi emisi karbon resmi/tersertifikasi.
