# Nalar Harian

Latihan logika PU 15 menit sehari: situasi nyata dulu, soal UTBK kemudian. Satu file `index.html`, tanpa instalasi.

## Isi
- **Hari ini** – sesi 4 bagian: pemanasan kilat (8 kartu, dibuat aplikasi sendiri), kasus hari ini (3 langkah), jembatan UTBK (3 soal), satu kalimat nalar.
- **Main** – 5 mini game pendamping: Geser Setara, Penjaga Gerbang, Venn Kilat, Detektif Chat, Kasir Jebakan. Tidak menggantikan sesi harian dan tidak mengubah tahap.
- **Peta** – N1–N8, tahap (Terang, Tersembunyi, Berantakan), akurasi 10 butir terakhir. Naik tahap bila ≥80%.
- **Rekap** – jebakan terbanyak (J1–J12), kasus nyata vs jembatan, butir salah untuk diulang.
- **Jurnal** – kalimat nalar harian; bisa disalin untuk diulas Claude.
- **Paket** (ikon kotak di kanan atas) – salin prompt ke proyek Claude "Nalar Harian", tempel JSON, cek format, stok, cadangan data.

## Pasang di GitHub Pages
1. Buat repo baru `nalar-harian`, unggah `index.html` dan `README.md`.
2. Settings → Pages → Branch `main`, folder `/ (root)` → Save.
3. Buka `https://<username>.github.io/nalar-harian/`.

## Sambungan ke Progres Harian
Setelah sesi selesai, aplikasi menulis ke `localStorage` kunci `nalarHarian:ringkasan`:

```json
{"app":"nalar-harian","tgl":"2026-11-13","selesai":true,"lengkap":true,"butir":14,"benar":11,"akurasi":79,"beruntun":3,"riwayat":{"2026-11-13":{"selesai":true,"butir":14,"akurasi":79}}}
```

Karena semua aplikasi ada di domain `github.io` yang sama, Progres Harian bisa membaca kunci ini untuk tugas "Nalar Harian".

Data utama ada di kunci `nalarHarian.v1`. Salin cadangan dari halaman Paket sesekali.
