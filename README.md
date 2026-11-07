# SATPAM BOK – Paket Perbaikan Pembacaan Anggaran dan Realisasi

Paket ini memperbaiki dua penyebab utama dashboard menampilkan Rp0:
1. Frontend sebelumnya mengubah angka berformat Indonesia seperti `37.500.000` menjadi angka tidak valid.
2. Data demo April masih aktif sehingga dapat bercampur dengan data Google Sheets.

## Isi paket
- `index.html`, `style.css`, `app.js`: frontend GitHub Pages.
- `gas/Code.gs`: backend Apps Script.
- `SATPAM_BOK_Template_GoogleSheets.xlsx`: template yang sudah diisi 74 transaksi register April–September 2026 dan 15 rincian pagu tahun 2026.
- `docs/PANDUAN_INSTALASI.md`: langkah pembaruan.
- `docs/STRUKTUR_DATA.md`: struktur tab.

## Nilai sumber
- 74 transaksi register: Rp316.056.954.
- 15 rincian pagu: Rp373.180.000.
- Data SPJ tidak dibuat otomatis dari transaksi; SPJ tetap diisi/dikelola pada tab `SPJ`.

## Penting
File Excel di paket ini adalah sumber untuk mengisi Google Spreadsheet. Mengunduh paket tidak otomatis mengubah Spreadsheet yang sudah ada di Google Drive. Salin isi tab `REGISTER_BELANJA` dan `ANGGARAN` ke Spreadsheet yang ID-nya sudah tersimpan pada Script Properties `SPREADSHEET_ID`.

Jangan mengganti `SPREADSHEET_ID` bila ingin tetap menggunakan Spreadsheet lama.
