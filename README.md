# Proyek Praktikum P06 · Chatbot Kantin (Versi Aman)

**Mata Kuliah:** Keamanan Sistem Informasi (PMI 1522)  
**NPM:** 24781103  
**Kasus:** LIVE-1 (Chatbot Kantin - Mitigasi Prompt Injection)  
**Versi:** AMAN (Secure)

---

## 📌 Deskripsi Proyek
Aplikasi web dummy chatbot kantin yang telah dilengkapi dengan kontrol keamanan berlapis di luar model (*defense-in-depth*) untuk menahan serangan **Direct Prompt Injection** (upaya pemaksaan peran menjadi kasir dan penerbitan voucher diskon terlarang 100%).

### Kontrol Keamanan yang Diterapkan:
1. **Hierarki Instruksi (Instruction Hierarchy):**
   - Pemisahan tegas antara instruksi sistem (`SYSTEM: ...`) dan input pengguna (`DATA_PENGGUNA: ...`).
2. **Allowlist Tool di Luar Model:**
   - Chatbot hanya diperbolehkan memanggil tool informasi menu (`jawab_info`, `tampilkan_menu`).
   - Eksekusi fungsi `buat_voucher` otomatis ditolak oleh lapisan aplikasi (`status: "ditolak"`).
3. **Validasi & Redaksi Output (Output Sanitization):**
   - Teks keluaran diperiksa di luar model. Pola kode voucher terlarang (`VOUCHER-P06-99`) disaring dan direduksi menjadi pesan penolakan resmi.

---

## 📁 Struktur Berkas
```text
24781103-kantin-voucher-aman/
├── index.html                       <- Berkas utama (otomatis tampil di GitHub Pages)
├── 24781103-kantin-voucher-aman.html<- Salinan berkas sesuai penamaan praktikum
├── 24781103-LIVE-1-aman-log.json    <- Bukti log JSON pengujian LLM
├── README.md                        <- Dokumentasi & panduan
└── .gitignore                       <- Mengabaikan file yang tidak perlu di Git
```

---

## 🚀 Cara Menjalankan di Visual Studio Code (VS Code)
1. Buka aplikasi **Visual Studio Code**.
2. Klik menu **File** -> **Open Folder...** (atau tekan `Ctrl + K`, lalu `Ctrl + O`).
3. Pilih folder `24781103-kantin-voucher-aman`.
4. Untuk menjalankan:
   - **Opsi 1 (Live Server):** Klik kanan pada file `index.html` -> pilih **Open with Live Server**.
   - **Opsi 2 (Browser langsung):** Klik dua kali file `index.html` untuk membuka di Google Chrome/Edge/Firefox.

---

## 📤 Cara Upload Manual ke GitHub

### Opsi A: Melalui Web GitHub (Drag & Drop)
1. Masuk ke [GitHub](https://github.com) dan login ke akun Anda.
2. Buat repository baru (klik tanda **+** -> **New repository**).
   - Nama repositori misal: `24781103-kantin-voucher-aman`
   - Pilih **Public**.
   - Klik **Create repository**.
3. Di halaman repositori baru, klik teks tautan **"uploading an existing file"**.
4. Drag & drop seluruh isi folder ini (`index.html`, `24781103-kantin-voucher-aman.html`, `24781103-LIVE-1-aman-log.json`, `README.md`, `.gitignore`).
5. Pada kotak commit message, tulis: `feat: upload project kantin voucher aman`.
6. Klik **Commit changes**.

### Opsi B: Mengaktifkan GitHub Pages (Hosting)
1. Pada halaman repositori GitHub Anda, klik menu **Settings** -> pilih tab **Pages** (di sidebar kiri).
2. Di bagian **Build and deployment** -> **Branch**:
   - Pilih `main` (atau `master`).
   - Pilih folder `/ (root)`.
   - Klik **Save**.
3. Tunggu 1–2 menit, web Anda akan aktif di URL:
   `https://<username-github>.github.io/<nama-repo>/`
