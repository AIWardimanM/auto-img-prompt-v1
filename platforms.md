# Penyesuaian prompt per platform

Daftar isi: ChatGPT Image / Gemini | Midjourney | Platform lain | Mode tanpa teks | Bila teks gambar rusak

Kemampuan platform berubah cepat. Bila ragu soal kemampuan versi terbaru (render teks, rasio yang didukung, parameter), cari informasi terbaru dengan web search sebelum menyarankan, dan jangan menyatakan batasan dari ingatan sebagai fakta.

## ChatGPT Image / Gemini
- Prompt bahasa alami, terstruktur, panjang diperbolehkan. Pakai struktur lengkap dari `prompt-template.md`.
- Teks Indonesia ditulis verbatim dalam tanda kutip. Tambahkan "Do not add any text that is not listed."
- Rasio disebut dengan kata-kata, mis. "16:9 landscape", "4:5 vertical portrait", "A4 portrait". Jangan memakai parameter gaya Midjourney.
- Bila teks di gambar tetap salah eja: sarankan kirim ulang dengan teks lebih pendek, atau minta "tulis ulang hanya bagian yang salah" (sebutkan blok yang salah dan teks yang benar dalam tanda kutip), atau pecah jadi dua gambar.

## Midjourney
- Prompt lebih pendek dan deskriptif (kira-kira 80-150 kata): layout, gaya, palet (hex tetap ditulis eksplisit), mood, ilustrasi.
- Tambahkan parameter rasio dan gaya di akhir sesuai versi terbaru, mis. `--ar 16:9`. Cek sintaks versi terbaru bila ragu; jangan menebak nomor versi.
- Platform ini lemah untuk teks padat. Bila materi bersisi teks banyak, TAWARKAN MODE TANPA TEKS: gambar dengan area kosong untuk teks, lalu teks ditambahkan manual di Canva/PowerPoint. Tawarkan sebagai tombol: "Mode tanpa teks (disarankan)" | "Tetap dengan teks" | "Ganti platform" | "Isi sendiri".
- Teks pendek (judul 1 baris, angka hero) masih boleh dicoba, tetapi beri tahu bahwa ejaan tidak terjamin.

## Platform lain (Ideogram, Leonardo, Canva AI, dll.)
- Tanyakan apakah platform itu kuat soal teks. Bila pengguna tidak tahu atau tidak, tawarkan mode tanpa teks.
- Ikuti format ChatGPT Image bila platform menerima prompt panjang berbahasa alami; ikuti format Midjourney bila platform berbasis kata kunci.

## Mode tanpa teks
- Ganti SEMUA teks di dalam gambar dengan "empty text placeholder area" (area kosong berbentuk kotak/garis pada posisi tiap teks).
- Pertahankan layout, zona, palet, ikon, dan hero element (bentuk angka besar sebagai kotak kosong).
- Sertakan di catatan akhir: daftar teks per zona (dalam tabel Markdown) agar pengguna bisa mengetik manual di Canva/PowerPoint.
- NEGATIVE ditambah: "any readable text, letters, numbers, watermarks, logos".

## Bila teks gambar rusak
1. Kirim ulang dengan teks lebih pendek (potong bullet jadi maksimal 6 kata).
2. Minta perbaikan terarah: "Rewrite only the title block so it reads exactly: '...'. Keep everything else unchanged."
3. Pecah menjadi 2 gambar atau beralih ke mode tanpa teks.
