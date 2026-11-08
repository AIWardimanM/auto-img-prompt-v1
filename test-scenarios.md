# Skenario uji auto-img-prompt-v1

Semua data uji fiktif. Tiap skenario punya prompt pengguna dan kriteria lulus.

## 1. Tema saja tanpa dokumen
Prompt: "Buatkan prompt infografis tentang keselamatan di persimpangan jalan hauling."
Lulus bila: skill menanyakan apakah ada materi untuk ditempel (bukan langsung mengarang), tidak menciptakan angka/statistik, hero berupa pesan kunci (bukan angka karangan), isi ditandai sebagai materi umum.

## 2. Dokumen padat, jadwal 3 hari, angka anggaran tidak cocok
Prompt: tempel dokumen gathering 3 hari + anggaran (rincian dijumlah 59.000.000, total tertulis 61.000.000, tanggal loncat 13 ke 15 Desember, lokasi TBC).
Lulus bila: ketiga anomali terdeteksi diam-diam di Langkah 0 lalu ditawarkan sebagai panel "Catatan"; materi dipecah jadi 2 gambar; angka ditulis persis seperti sumber; elemen konsisten lintas gambar.

## 3. "Arahan sendiri" (textbox) dan palet hex buatan sendiri
Prompt: pengguna memilih gaya "Arahan sendiri" dan mengetik 4 hex tanpa warna gelap.
Lulus bila: arahan dipakai apa adanya; hex dipetakan ke lima peran; skill menyarankan warna gelap untuk Struktur dan meminta persetujuan; aturan warna baku tetap berlaku.

## 4. Pengguna langsung berkata "ikuti rekomendasi semua"
Lulus bila: pertanyaan hanya platform (bila belum disebut), lalu langsung ke ringkasan Langkah 8 dengan label rekomendasi otomatis, tiap rekomendasi punya alasan satu kalimat.

## 5. Midjourney dengan materi bersisi teks padat
Lulus bila: skill menawarkan MODE TANPA TEKS sebagai tombol; prompt memakai "empty text placeholder area" dan parameter rasio; materi lebih dari 5 modul dipecah; teks untuk manual disertakan sebagai tabel.

## 6. Palet berwarna hijau/merah/kuning di palet (Serene Nature) dengan status setuju/ditolak
Lulus bila: tidak ada hijau/merah/kuning sebagai penanda status; setuju = Struktur + centang, ditolak = Aksen + silang; NEGATIVE memuat larangan traffic-light.
