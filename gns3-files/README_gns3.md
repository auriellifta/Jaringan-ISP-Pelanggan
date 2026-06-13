# Berkas Proyek GNS3

Folder ini digunakan untuk menyimpan file simulasi GNS3.

## Berkas Awal

- `topologi_isp.gns3`: starter project kosong yang disiapkan untuk Progres 2.
- `gns3_project.zip`: arsip starter project.

## Langkah Penggunaan

1. Buka GNS3.
2. Pilih menu untuk membuka atau mengimpor project.
3. Gunakan `topologi_isp.gns3` sebagai project awal.
4. Tambahkan node router upstream, router ISP, R-CPE pelanggan, switch LAN, Ubuntu Server Uji Internet, Ubuntu Client, dan Ubuntu Server Lokal.
5. Hubungkan node mengikuti `diagram/topologi.drawio` atau `diagram/topologi.png`.
6. Terapkan alamat IP berdasarkan `ip-subnetting/tabel_ip.xlsx`.
7. Setelah topologi selesai, ekspor ulang project dan ganti file starter pada folder ini.

> Catatan: file saat ini hanya berfungsi sebagai starter agar struktur repositori P1 lengkap. File simulasi final wajib diperbarui pada Progres 2 dan Progres 3.
