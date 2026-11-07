# Struktur data SATPAM BOK

- `REGISTER_BELANJA`: header pada baris 3, data mulai baris 4; kolom utama mencakup TAHUN, BULAN, NO BUKTI REGISTER, KODE REKENING, dan JUMLAH BELANJA (Rp).
- `ANGGARAN`: header pada baris 1, data mulai baris 2; total 15 baris pagu 2026 pada file template paket.
- `SPJ`: header pada baris 1; hanya memuat dokumen SPJ yang benar-benar didaftarkan.
- `JADWAL_KEGIATAN`: header pada baris 1.
- `PENGGUNA`: daftar akun yang berwenang (jika dipakai oleh kebijakan aplikasi).

Jumlah realisasi dihitung dari kolom `JUMLAH BELANJA (Rp)`. Pagu dihitung dari kolom `PAGU (Rp)`. Nilai uang disimpan sebagai angka, bukan teks berawalan `Rp`.
