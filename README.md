# Nalar Harian

Latihan PU UTBK-SNBT 2027 sekitar 30 menit sehari: 20 soal bagian Deduktif dan Induktif, disusun dari kode kemampuan Brief Kunci Pola. Satu file `index.html`, tanpa instalasi.

## Isi
- **Hari ini** – **Set PU** 20 soal (Deduktif 10 lalu Induktif 10, 60 detik per soal), lalu varian Error Book bila ada yang jatuh tempo. Paket versi 3 lama (kasus 3 langkah + 3 jembatan) yang masih di stok tetap berjalan.
- **Main** – 5 mini game pendamping yang punya kode kemampuan Brief: Arsir Venn (PU-DED-3), Detektif Chat (PU-DED-5, PU-DED-4), Hakim Simpulan (PU-DED-4), Beli Petunjuk (PU-KUA-5), Lompat Batu (PU-KUA-2). Untuk waktu luang setelah sesi; tidak mengubah rencana harian.
- **Peta** – 11 kemampuan PU (PU-DED-1…5, PU-IND-1…6): 10 soal terakhir, akurasi L dan B+M, Indeks Kesiapan, dan status (Mode Dasar, porsi B/M naik, dalam target, data belum cukup).
- **Rekap** – Kesiapan 2027 (tabel L/G/B/M: benar/total, persen, waktu rata-rata; akurasi total, Indeks Kesiapan, waktu bentuk baru dengan targetnya), jebakan terbanyak, Set PU per bagian, status kemampuan, ringkasan Error Book.
- **Error Book** (`#eb`) – butir salah dari kasus dan jembatan masuk otomatis beserta jawabanmu dan jebakan yang menjerat (J1–J13). Tiga langkah:
  1. *Diagnosis*: pilih apa yang terjadi di kepalamu (belum paham aturannya, kata kunci terlewat, pakai pengetahuan luar, terpancing opsi, simpulan kelewat jauh, terburu-buru, menebak), lalu tulis aturan "Kalau …, aku …". Aturan yang terlalu umum diberi peringatan.
  2. *Ulang berjarak tanpa kunci*: mulai besok, lalu 3, 7, 14 hari (paling banyak 10 butir per putaran, urutan diacak). Aturanmu baru ditampilkan setelah menjawab.
  3. *Lulus* setelah benar 4 kali berjarak; salah lagi berarti mulai dari awal dan diagnosis diperbarui.
  - *Pola 30 hari*: penyebab, jebakan, dan keterampilan yang paling sering salah, fokus minggu ini, dan prompt analisis pola untuk Claude. Kartu pengingat muncul di halaman Hari ini.
- **Jurnal** – catatan klaim yang kamu dengar (opsional, di luar sesi harian); bisa disalin untuk diulas Claude.
- **Paket** (tombol "Paket" di kartu Sesi pada halaman Hari ini) – salin prompt ke proyek Claude "Nalar Harian", tempel JSON, cek format, stok, cadangan data.
  - Paket versi 4 per hari: 20 soal (`soal`), tiap soal membawa `kemampuan` (PU-DED-1…5, PU-IND-1…6), `jenis_pola` (L/G/B/M), `bentuk_dekat`, `format` (J1–J7), `bidang`, `latar`, `tokoh`. Komposisi per bagian 3 L / 4 G / 2 B / 1 M; paling banyak 2 soal di luar J1 per bagian; satu soal "kasus nyata" per hari.
  - Rencana harian: semua kemampuan muncul tiap hari. Per kemampuan (±20 soal terakhir): akurasi L < 70% → hanya soal L; Indeks Kesiapan < 0,75 → porsi B dan M naik.
  - Pewaktu Set PU: 10 menit per bagian; waktu tiap soal dicatat (detik) dan berhenti saat membaca pembahasan, keluar misi, atau aplikasi tidak terlihat. Lewat 10 menit, soal tetap bisa dikerjakan tetapi ditandai "lewat waktu". Posisi soal tersimpan, jadi muat ulang melanjutkan dari soal terakhir.
  - Varian Error Book (bagian `ulang` di paket): untuk paling banyak 3 butir Error Book yang jatuh tempo (paling lama tertunda dulu), prompt meminta satu varian dengan kemampuan dan jebakan sama dan satu tuas diubah (ganti konteks → balik arah tanya → tambah satu syarat, bergilir). Varian dikerjakan sebagai langkah terakhir sesi; sesi baru selesai setelah varian dikerjakan. Skornya terpisah dari 20 soal dan menggeser kotak ulang berjarak butir itu.
  - Bila balasan Claude terpotong, ketik "lanjutkan" di chat, lalu tempel kedua potongan sekaligus; aplikasi menyambungnya sendiri.
  - Jebakan ditampilkan dengan namanya; kode J1–J13 hanya dipakai di data. Kode "J…" yang tampil hanya kode format di baris label.
  - Prompt memberi target huruf kunci per soal, aturan anti-tebak, dan daftar kerangka yang sudah dipakai. Saat menyimpan, aplikasi menolak paket dengan pelanggaran berat: kunci menjadi opsi terpanjang di lebih dari 1 dari 5 soal, pengecoh tanpa label jebakan, opsi kembar, opsi baku yang diubah atau diacak, "tepat dua" yang dilanggar, nomor/huruf kalimat di stimulus, atau stimulus lebih dari 8 kalimat. Pelanggaran ringan cukup diberi peringatan: selisih kata opsi lebih dari 30%, kunci satu-satunya yang berhati-hati, stimulus 7–8 kalimat atau kurang dari 2, frasa khas tulisan AI, dan huruf kunci yang menumpuk.

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

Data utama ada di kunci `nalarHarian.v1`.

## Penyimpanan dan perampingan
Semua app di `faiqdk07-tech.github.io` berbagi satu kuota localStorage (±5 MB). Pengaturan → Penyimpanan menampilkan pemakaian semua app dan app ini, daftar data yang bisa dirampingkan, serta tombol cadangan.
- Perampingan baru aktif setelah cadangan pertama ("Salin cadangan dulu" atau "Unduh berkas cadangan"); setelah itu berjalan otomatis sekali sehari saat app dibuka, atau lewat "Rampingkan sekarang".
- Aturan (data lebih dari 30 hari, key tidak berubah): paket soal dibuang; butir Error Book yang sudah lulus diringkas (butir aktif tetap utuh); riwayat jawaban tidak dihapus, hanya kolom kosong dibuang; sesi lama kehilangan data tampilan saja. Data 30 hari terakhir utuh.
- Bila penyimpanan penuh, muncul tanda "Belum tersimpan" yang membuka Pengaturan.
- Cadangan berbentuk `{"app","key","dibuat","data"}`; "Pulihkan dari cadangan" menerima bentuk ini dan bentuk lama.
