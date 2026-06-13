# Perencanaan IP Addressing dan Subnetting

Dokumen ini berisi rancangan pengalamatan IP untuk simulasi jaringan ISP dan pelanggan. Alamat publik yang digunakan merupakan blok dokumentasi untuk keperluan pembelajaran, bukan alamat yang digunakan pada jaringan produksi.

## Ringkasan Segmen Jaringan

| Segmen | Network Address | Prefix | Rentang Host yang Dapat Digunakan | Broadcast | Penggunaan |
|---|---:|---:|---|---:|---|
| Layanan publik simulasi | `203.0.113.64` | `/26` | `203.0.113.65 - 203.0.113.126` | `203.0.113.127` | Ubuntu Server Uji Internet dan antarmuka upstream |
| Transit upstream | `203.0.113.0` | `/30` | `203.0.113.1 - 203.0.113.2` | `203.0.113.3` | Link point-to-point R-INTERNET menuju R-ISP |
| Akses ISP-pelanggan | `198.51.100.0` | `/30` | `198.51.100.1 - 198.51.100.2` | `198.51.100.3` | Link point-to-point R-ISP menuju R-CPE Pelanggan |
| LAN privat pelanggan | `192.168.10.0` | `/24` | `192.168.10.1 - 192.168.10.254` | `192.168.10.255` | Gateway, client, dan server lokal pelanggan |

## Tabel Pengalamatan Perangkat

| Nama Perangkat | Interface | Tipe IP | IP Address | Prefix | Gateway atau Next Hop | Keterangan |
|---|---|---|---|---|---|---|
| Ubuntu Server Uji Internet | `eth0` | Public simulasi | `203.0.113.66` | `/26` | `203.0.113.65` | Server tujuan untuk pengujian akses internet simulasi |
| R-INTERNET / Upstream | `eth0` | Public simulasi | `203.0.113.65` | `/26` | - | Gateway segmen server uji |
| R-INTERNET / Upstream | `eth1` | Public simulasi | `203.0.113.1` | `/30` | - | Transit upstream menuju R-ISP |
| R-ISP | `eth0` | Public simulasi | `203.0.113.2` | `/30` | `203.0.113.1` | Transit menuju upstream |
| R-ISP | `eth1` | Public simulasi | `198.51.100.1` | `/30` | - | Akses ISP menuju pelanggan |
| R-CPE Pelanggan | `WAN` | Public simulasi | `198.51.100.2` | `/30` | `198.51.100.1` | WAN pelanggan dan alamat hasil NAT/PAT |
| R-CPE Pelanggan | `LAN` | Private | `192.168.10.1` | `/24` | - | Gateway LAN pelanggan |
| Ubuntu Client | `eth0` | Private | `192.168.10.10` | `/24` | `192.168.10.1` | Client LAN pelanggan |
| Ubuntu Server Lokal | `eth0` | Private | `192.168.10.20` | `/24` | `192.168.10.1` | Server lokal pelanggan |

## Alasan Pemilihan Prefix

Prefix `/30` digunakan pada link point-to-point karena hanya diperlukan dua alamat host aktif pada setiap jalur antar-router. Prefix `/24` digunakan pada LAN pelanggan agar tersedia ruang alamat yang cukup untuk penambahan perangkat client dan server selama simulasi. Prefix `/26` digunakan pada segmen layanan publik simulasi untuk menyediakan ruang alamat bagi server uji dan pengembangan skenario lanjutan.

## Rencana NAT/PAT

Router `R-CPE Pelanggan` direncanakan menggunakan NAT/PAT masquerading. Ketika Ubuntu Client `192.168.10.10` mengakses Ubuntu Server Uji Internet `203.0.113.66`, alamat sumber akan diterjemahkan menjadi alamat WAN router pelanggan `198.51.100.2`.
