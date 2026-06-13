# Panduan Instalasi Awal

Dokumen ini berisi persiapan perangkat lunak sebelum simulasi GNS3 dijalankan.

## Perangkat Lunak

1. GNS3 Desktop.
2. GNS3 VM apabila diperlukan oleh lingkungan perangkat.
3. VirtualBox atau VMware sesuai kebutuhan virtualisasi.
4. Image Ubuntu Server dan Ubuntu Client.
5. Draw.io untuk membuka dan mengedit diagram topologi.

## Langkah Persiapan

1. Instal GNS3 Desktop pada laptop anggota kelompok.
2. Pastikan fitur virtualisasi pada perangkat telah aktif.
3. Siapkan image Ubuntu Server dan Ubuntu Client yang akan digunakan sebagai endpoint.
4. Buka diagram pada `diagram/topologi.drawio` sebagai acuan interkoneksi.
5. Buka `ip-subnetting/tabel_ip.xlsx` sebagai acuan konfigurasi alamat.
6. Buat project GNS3 berdasarkan starter file pada folder `gns3-files/`.
7. Tambahkan node secara bertahap dan uji konektivitas setelah setiap link dikonfigurasi.

## Antisipasi Kendala

- Periksa nama interface menggunakan `ip addr` sebelum menerapkan konfigurasi.
- Aktifkan IPv4 forwarding pada node yang berfungsi sebagai router.
- Periksa default route apabila client hanya dapat mengakses LAN lokal.
- Periksa aturan NAT/PAT apabila akses menuju server uji gagal setelah routing dasar berhasil.
- Simpan screenshot konfigurasi dan hasil pengujian pada folder yang telah disediakan.
