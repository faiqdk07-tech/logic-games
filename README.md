# Nalar Harian

Latihan logika PU 15 menit sehari: situasi nyata dulu, soal UTBK kemudian. Satu file `index.html`, tanpa instalasi.

## Isi
- **Hari ini** – sesi 4 bagian: pemanasan kilat (8 kartu, dibuat aplikasi sendiri), kasus hari ini (3 langkah), jembatan UTBK (3 soal), satu kalimat nalar.
- **Main** – 11 mini game pendamping: Arsir Venn, Lampu Berantai, Rantai Kunci, Inspektur Bandara, Satu Bukti, Detektif Chat, Belanja Hemat, Hakim Simpulan, Beli Petunjuk, Kursi Rapat, Lompat Batu. Tidak menggantikan sesi harian dan tidak mengubah tahap.
- **Peta** – N1–N8, tahap (Terang, Tersembunyi, Berantakan), akurasi 10 butir terakhir. Naik tahap bila ≥80%.
- **Rekap** – jebakan terbanyak (J1–J13), kasus nyata vs jembatan, ringkasan Error Book.
- **Error Book** (`#eb`) – butir salah dari kasus dan jembatan masuk otomatis beserta jawabanmu dan jebakan yang menjerat (J1–J13). Tiga langkah:
  1. *Diagnosis*: pilih apa yang terjadi di kepalamu (belum paham aturannya, kata kunci terlewat, pakai pengetahuan luar, terpancing opsi, simpulan kelewat jauh, terburu-buru, menebak), lalu tulis aturan "Kalau …, aku …". Aturan yang terlalu umum diberi peringatan.
  2. *Ulang berjarak tanpa kunci*: mulai besok, lalu 3, 7, 14 hari (paling banyak 10 butir per putaran, urutan diacak). Aturanmu baru ditampilkan setelah menjawab.
  3. *Lulus* setelah benar 4 kali berjarak; salah lagi berarti mulai dari awal dan diagnosis diperbarui.
  - *Pola 30 hari*: penyebab, jebakan, dan keterampilan yang paling sering salah, fokus minggu ini, dan prompt analisis pola untuk Claude. Kartu pengingat muncul di halaman Hari ini.
- **Jurnal** – kalimat nalar harian; bisa disalin untuk diulas Claude.
- **Paket** (tombol "Paket" di kartu Sesi pada halaman Hari ini) – salin prompt ke proyek Claude "Nalar Harian", tempel JSON, cek format, stok, cadangan data.
  - Paket versi 3 per hari: 1 kasus, 3 jembatan, 4 kartu `pemanasan`, 1 ronde `detektif`. Dua bagian terakhir opsional; paket lama tetap terbaca.
  - Prompt memberi target huruf kunci per soal, aturan anti-tebak, dan daftar kerangka yang sudah dipakai. Saat menyimpan, aplikasi memperingatkan pola yang mudah ditebak (kunci selalu terpanjang, huruf kunci menumpuk).

## Paket mini game mingguan
- Bank kata Lampu Berantai, Rantai Kunci, Inspektur Bandara, Arsir Venn, Hakim Simpulan, dan Beli Petunjuk diganti tiap minggu (Senin–Minggu).
- Halaman Main → "Paket mingguan" (atau `#mingguan`): salin prompt mingguan → jalankan di proyek Claude "Nalar Harian" → tempel JSON → Cek & simpan. Paket minggu depan bisa disiapkan lebih awal.
- Pengingat: mulai Jumat muncul kartu "Saatnya ganti paket mini game" bila paket minggu depan belum ada; mulai Senin tanpa paket muncul "Paket mini game terlambat" dan game memakai bank bawaan.
- Status ditulis ke kunci `paketMingguan:nalar-harian` (`{"app","nama","minggu":["YYYY-MM-DD" hari Senin, ...],"diperbarui"}`) supaya Progres Harian ikut mengingatkan.

## Pasang di GitHub Pages
1. Unggah `index.html` dan `README.md` ke repo `logic-games` (nama ini dipakai menu teleport Bloki untuk menandai app yang sedang dibuka).
2. Settings → Pages → Branch `main`, folder `/ (root)` → Save.
3. Buka `https://<username>.github.io/logic-games/`.

## Sambungan ke Progres Harian
Setelah sesi selesai, aplikasi menulis ke `localStorage` kunci `nalarHarian:ringkasan`:

```json
{"app":"nalar-harian","tgl":"2026-11-13","selesai":true,"lengkap":true,"butir":14,"benar":11,"akurasi":79,"beruntun":3,"riwayat":{"2026-11-13":{"selesai":true,"butir":14,"akurasi":79}}}
```

Karena semua aplikasi ada di domain `github.io` yang sama, Progres Harian bisa membaca kunci ini untuk tugas "Nalar Harian".

Data utama ada di kunci `nalarHarian.v1`. Salin cadangan dari halaman Paket sesekali.
