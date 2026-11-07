# Panduan pembaruan SATPAM BOK – Perbaikan data Rp0

## A. Backup
1. Buka Google Spreadsheet yang digunakan SATPAM BOK.
2. Buat salinan/backup sebelum mengganti data.
3. Pastikan Script Property `SPREADSHEET_ID` menunjuk ke Spreadsheet ini.

## B. Isi ulang tab ANGGARAN
1. Buka file `SATPAM_BOK_Template_GoogleSheets.xlsx` dari paket.
2. Buka sheet `ANGGARAN`; header ada di baris 1 dan 15 rincian data ada di baris 2–16.
3. Salin A1:G16.
4. Tempel ke tab `ANGGARAN` di Google Spreadsheet tujuan mulai A1 (replace isi lama).
5. Pastikan nilai `PAGU (Rp)` merupakan angka, bukan teks yang diketik dengan awalan Rp.

## C. Isi ulang tab REGISTER_BELANJA
1. Dari file yang sama, buka `REGISTER_BELANJA`.
2. Header berada di baris 3, data 74 transaksi mulai baris 4.
3. Salin A1:Q77.
4. Tempel ke tab `REGISTER_BELANJA` pada Spreadsheet tujuan mulai A1 (replace isi lama).
5. Pastikan baris 1–3 tetap utuh; backend membaca header di baris 3.

## D. Perbarui backend
1. Buka Apps Script yang terhubung ke Spreadsheet.
2. Ganti seluruh isi `Code.gs` dengan file `gas/Code.gs` dari paket.
3. Simpan.
4. Pilih Deploy > Manage deployments > Edit > New version > Deploy.
5. Gunakan kembali URL Web App yang sama bila deployment diperbarui, lalu pastikan URL itu masih sesuai di `app.js`.

## E. Perbarui GitHub Pages
1. Unggah/ganti `index.html`, `style.css`, dan `app.js` di root repository GitHub.
2. Jangan unggah file token atau kredensial.
3. Tunggu GitHub Pages selesai menerbitkan.
4. Buka situs dan tekan Ctrl+F5.

## F. Uji hasil
Dashboard 2026 diharapkan menampilkan:
- Pagu anggaran: Rp373.180.000
- Realisasi register: Rp316.056.954
- Sisa anggaran aritmetis: Rp57.123.046
- Transaksi register: 74

Jika angka transaksi berbeda, pastikan semua 74 baris telah disalin ke tab yang benar dan kolom TAHUN berisi 2026. Jika pagu atau realisasi masih nol, periksa bahwa header persis `PAGU (Rp)` dan `JUMLAH BELANJA (Rp)`.

Catatan: total SPJ berasal dari tab `SPJ`, bukan jumlah transaksi register. Tidak dibuatkan dokumen SPJ fiktif.
