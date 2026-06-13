# Cara Mengunggah Struktur Repositori ke GitHub

Repositori tujuan:

```text
https://github.com/auriellifta/Jaringan-ISP-Pelanggan
```

## Metode Git melalui CMD atau PowerShell

1. Pastikan Git sudah terpasang.
2. Buka CMD atau PowerShell pada folder kerja.
3. Jalankan perintah berikut:

```bash
git clone https://github.com/auriellifta/Jaringan-ISP-Pelanggan.git
cd Jaringan-ISP-Pelanggan
```

4. Salin seluruh isi folder `jaringan-isp-pelanggan` dari paket ZIP ke dalam folder hasil clone. Pilih **Replace** apabila diminta mengganti `README.md`.
5. Jalankan:

```bash
git add .
git commit -m "docs: tambahkan struktur repositori dan artefak P1"
git push origin main
```

## Pemeriksaan Setelah Push

Pastikan berkas P1 berikut terlihat pada GitHub:

- `proposal-analisis/proposal.pdf`
- `proposal-analisis/analisis_kebutuhan.pdf`
- `diagram/topologi.drawio`
- `diagram/topologi.png`
- `diagram/topologi.pdf`
- `ip-subnetting/tabel_ip.xlsx`
- `ip-subnetting/subnetting.md`

Folder P2, P3, dan Final sudah disiapkan dengan README atau template agar dapat dilengkapi pada progres berikutnya.
