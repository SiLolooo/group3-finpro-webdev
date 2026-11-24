# Group 3 - Kalkulator & Simulasi Jejak Karbon Listrik Rumah (SDG 7.3 & 13.3)

Final Project Web Development - HITLAB 26.2  
**Studi Kasus:** Jalur A — Rumah Tangga (Pencatatan kWh bulanan & perbandingan skenario pengurangan konsumsi listrik)

## Link Aplikasi (Kalian nanti edit sesuai dengan versi yang kalian buat) 
- **Live App deployment (Vercel):** `[Isi URL deploy Vercel]`
- **Initial Repo Check (GitHub Pages):** https://silolooo.github.io/group3-finpro-webdev/

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
  - `/backend` : Server API (Node.js, Express.js, dan `storageAdapter.js`)
  - `/data` : Snapshot data cadangan faktor emisi (`snapshot-faktor-emisi.json`)
- **Aturan Git:**
  - Dilarang push langsung ke `main` setelah setup awal selesai.
  - Gunakan format branch: `feat/nama-fitur` (contoh: `feat/form-input`, `feat/api-readings`).
  - Lakukan Pull Request untuk menggabungkan kode ke `main`.

## Batasan Demo & Mode Latihan
- Aplikasi ini menggunakan faktor emisi sintetis berlabel **"latihan"** (`0.87 kg CO2/kWh`) untuk tujuan pembelajaran dan simulasi.
- Hasil perhitungan merupakan estimasi edukatif (SDG 7.3 & 13.3) dan bukan inventarisasi emisi karbon resmi/tersertifikasi.

## Alur Penggunaan Aplikasi (User Flow)
1. **Edukasi & Faktor Emisi:** Pengguna membuka web dan melihat penjelasan mode latihan (`0.87 kg CO2/kWh`) serta cakupan target SDG 7.3 & 13.3.
2. **Input Catatan Bulanan:** Pengguna mengisi formulir pemakaian listrik rumah tangga (bulan/tahun dan angka `kWh`). Validasi mencegah angka negatif/kosong.
3. **Kalkulasi & Riwayat (CRUD):** Sistem otomatis menghitung estimasi emisi (`kWh × 0.87`) dan menyimpannya ke tabel riwayat (bisa dilihat, diedit, atau dihapus).
4. **Simulasi Skenario Hemat:** Pengguna memilih catatan atau memasukkan target pengurangan (misal hemat `10%`, `20%`, atau `30%`) untuk melihat perbandingan emisi sebelum vs sesudah penghematan—tanpa mengubah data catatan asli.

## Alur Data & Arsitektur Sistem
- **Frontend (`index.html` + `app.js`)** ──(HTTP Fetch)──► **Backend Express**
- **Backend (`GET /api/faktor-emisi`)** ──(Baca)──► `/data/snapshot-faktor-emisi.json`
- **Backend (`POST /api/emisi`)** ──(Hitung)──► Estimasi emisi karbon (`kWh × 0.87`)
- **Backend (`CRUD /api/readings`)** ──(Simpan)──► `storageAdapter.js` (JSON)

## Daftar Endpoint API (Backend)
- `GET /api/faktor-emisi` — Mengambil daftar faktor emisi mode latihan (`0.87 kg CO2/kWh`)
- `POST /api/emisi` — Menghitung estimasi emisi karbon berdasarkan input konsumsi `kWh`
- `GET /api/readings` — Menampilkan seluruh riwayat catatan kWh bulanan
- `POST /api/readings` — Menambah catatan kWh bulanan baru
- `PUT /api/readings/:id` — Mengubah catatan kWh berdasarkan ID
- `DELETE /api/readings/:id` — Menghapus catatan kWh berdasarkan ID

## Tahapan Pengerjaan (Roadmap)
- **Tahap 1 (Setup & Git):** Accept collaborator, clone repo, isi nama anggota di `README.md` via Pull Request.
- **Tahap 2 (Frontend UI & Simulasi Awal):** Buat layout responsif (HTML + Tailwind CSS) dan logika kalkulator/simulasi sementara di JavaScript.
- **Tahap 3 (Backend & Integrasi API):** Buat server Express.js, hubungkan endpoint CRUD dengan `storageAdapter.js`, dan ganti data dummy frontend dengan `fetch()` ke API.
- **Tahap 4 (Deploy & Finalisasi):** Deploy backend ke Vercel, update link live demo di `README.md`, dan uji seluruh skenario (termasuk mode snapshot cadangan).

## Cara Menjalankan di Lokal
1. Clone repositori ini dengan command:
   `git clone [https://github.com/SiLolooo/group3-finpro-webdev.git](https://github.com/SiLolooo/group3-finpro-webdev.git)`
   *(Kamu bisa jalanin di terminal vscode nya langsung)*
2. Masuk ke folder backend dan install dependencies *(saat tahap Sesi 7–8)*:
   `cd backend && npm install && npm start`
3. Buka file antarmuka di folder `frontend/` menggunakan **Live Server** di VS Code.
