---
name: auto-img-prompt-v1
description: Memandu pengguna lewat konfirmasi bertahap lalu menulis prompt text-to-image (siap salin ke ChatGPT Image, Gemini, Midjourney, dll.) untuk infografis, poster, atau slide visual dari sebuah TEMA dan, bila ada, dokumen/ringkasan acuan. Gunakan skill ini setiap kali pengguna menyebut buat prompt gambar, prompt foto AI, prompt infografis, prompt poster, prompt slide visual, visualkan resume/notulen/laporan/dokumen/jadwal/SOP jadi gambar, atau memberi sebuah tema lalu meminta gambarnya dirancang, walaupun tidak menyebut kata "skill". Skill ini menghasilkan PROMPT-nya, bukan gambarnya.
---

# Auto Img Prompt v1

Mengubah tema (dan opsional dokumen/ringkasan) menjadi prompt text-to-image yang siap salin. Claude memandu pengguna lewat konfirmasi bertahap, lalu merakit prompt. Output akhir adalah PROMPT, bukan gambar.

Tujuan alur bertahap: pengguna sering belum tahu platform, rasio, atau palet yang cocok. Menanyakannya satu per satu (dengan rekomendasi bernalar) menghasilkan prompt yang jauh lebih tepat daripada menebak sekaligus.

## Berkas referensi (baca saat dibutuhkan)

| Berkas | Baca kapan |
|---|---|
| `references/recommendations.md` | Setiap kali menerapkan default/rekomendasi di suatu langkah |
| `references/palettes.md` | Langkah 3B, saat menyalin blok palet, saat QA |
| `references/platforms.md` | Langkah 1 dan Langkah 10 (format per platform) |
| `references/layouts.md` | Langkah 4 dan 7 (pola layout dan pembagian zona) |
| `references/icon-themes.md` | Langkah 5 (ikon sesuai tema) |
| `references/prompt-template.md` | Langkah 10 (template baku dan varian Midjourney/tanpa teks) |

## Aturan umum alur

- **Satu langkah per giliran.** Jangan menumpuk semua pertanyaan sekaligus. Dua pertanyaan tombol dalam satu panggilan hanya boleh bila keduanya bagian dari langkah yang sama (mis. rasio + kualitas di Langkah 2).
- **Tombol** lewat `ask_user_input_v0` untuk pertanyaan berpilihan. Maksimal 4 tombol per pertanyaan. Tandai pilihan yang direkomendasikan dengan "(disarankan)" dan beri alasan satu kalimat di pesan pembuka. Setelah memanggil tool, giliran selesai; tunggu jawaban pengguna.
- **Pilihan lebih dari 4** (mis. palet): pakai dua tingkat (kelompok dulu, lalu pilihan) atau tampilkan daftar bernomor di teks lalu minta pengguna mengetik nomor/nama.
- **Tiga mode input per pertanyaan:**
  1. TOMBOL: pilihan baku.
  2. ISI SENDIRI: pertanyaan teks biasa tanpa tombol; berhenti dan tunggu ketikan pengguna; pakai jawabannya apa adanya tanpa mengubah makna.
  3. KEDUANYA: tombol, dan pengguna boleh mengetik jawaban lain kapan saja.
- **Jalan "Isi sendiri" wajib ada** di setiap langkah berpilihan: satu tombol "Isi sendiri (ketik)" bila slot tersedia (ingat batas 4), atau tulis "atau ketik sendiri" di pesan pembuka.
- **Langkah yang SELALU textbox (tanpa tombol):** arahan gaya khusus (bila dipilih), teks/judul/frasa wajib tampil atau dibuang, dan "arahan tambahan" di Langkah 9.
- **Jangan bertanya hal yang sudah dijawab atau bisa disimpulkan** dari tema/dokumen. Sebutkan asumsinya dalam satu kalimat dan lanjut.
- **Tidak menambah fakta.** Angka, nama, tanggal, dan nominal ditulis persis seperti sumber. Bila sumber ambigu, tandai sebagai anomali, jangan diperbaiki diam-diam.
- Balas dalam bahasa yang dipakai pengguna (umumnya Indonesia). Instruksi di dalam prompt akhir berbahasa Inggris (lihat Langkah 10).

## Mode pemanduan dan "ikuti rekomendasi"

Setelah Langkah 0, tanyakan SATU kali (tombol):
- Dipandu penuh (tanya tiap langkah)
- Ikuti rekomendasi semua (cepat, langsung ke ringkasan)
- Campuran (rekomendasi untuk yang teknis; tanya hanya gaya, konten, dan penyajian data)

Di langkah mana pun pengguna boleh mengetik "rekomendasi", "terserah", "bingung", atau "lewati": terapkan default yang disarankan untuk langkah itu (lihat `references/recommendations.md`), jelaskan alasannya dalam satu kalimat, lalu lanjut. Bila pengguna berkata "ikuti rekomendasi semua" kapan saja, terapkan default untuk seluruh langkah tersisa dan tampilkan ringkasan (Langkah 8).

**Pengecualian platform:** platform tujuan tidak bisa disimpulkan dari tema. Pada mode "ikuti rekomendasi semua", tanyakan platform satu kali (tombol) kecuali pengguna sudah menyebutnya. Bila ia menjawab tidak tahu, rekomendasikan ChatGPT Image atau Gemini untuk infografis bersisi teks.

Mode Campuran: teknis = platform, ukuran, layout, ilustrasi (diambil dari rekomendasi); ditanyakan = gaya (3A), konten (6), penyajian data (7).

## Alur

### Langkah 0: Input

Terima tema dan sumber (dokumen, ringkasan, atau keduanya). Ekstrak diam-diam: judul, tanggal/lokasi, pihak, angka kunci, jadwal, daftar tindak lanjut, dan HERO METRIC (1 angka terpenting). Bila tidak ada sumber, tanya apakah pengguna ingin menempelkan materi atau cukup bertema umum; untuk tema umum, jangan mengarang angka, pakai placeholder teks atau modul tanpa angka.

Lakukan DETEKSI ANOMALI dan simpan untuk Langkah 6 dan 7 (jangan diumumkan panjang lebar sekarang):
- tanggal tidak berurutan atau hari kosong dalam rentang
- total tidak sama dengan jumlah rincian (hitung sendiri)
- status TBC/TBD/menunggu konfirmasi
- istilah, satuan, atau nama yang ambigu atau tidak konsisten

Lalu tanyakan mode pemanduan.

### Langkah 1: Platform tujuan
Mode: tombol + ketik sendiri. Pilihan: ChatGPT Image | Gemini | Midjourney | Lainnya (ketik: Ideogram, Leonardo, Canva AI, dll). Detail penyesuaian ada di `references/platforms.md`; bila ragu soal kemampuan versi terbaru sebuah platform, cari informasi terbaru lebih dulu. Midjourney dan platform yang lemah soal teks: tawarkan MODE TANPA TEKS bila materi bersisi teks padat.

### Langkah 2: Ukuran dan resolusi
Mode: tombol + ketik sendiri (dua pertanyaan dalam satu panggilan).
- Rasio: 16:9 landscape | 4:5 vertikal | 9:16 vertikal | A4/A3 portrait cetak | Isi sendiri (mis. 1:1, 3:2, piksel khusus). Karena batas 4 tombol, bila slot habis tulis "atau ketik sendiri" di pesan pembuka.
- Kualitas: standar (1920x1080 atau setara) | tinggi (2K-4K, untuk cetak) | Isi sendiri.

### Langkah 3: Gaya dan palet
**3A. Gaya** (tombol + ketik sendiri): (a) Elegan konsultan ala McKinsey (grid rapi, action title, serif + sans) | (b) Ilustratif (adegan dan karakter) | (c) Ikuti gaya dokumen/ringkasan acuan | (d) Arahan sendiri. Bila (d): TEXTBOX, pengguna mengetik bebas (mood, font, referensi, larangan); jangan beri tombol; pakai apa adanya, tetapi aturan warna baku tetap berlaku.

**3B. Palet** (dua tingkat, lalu ketik sendiri). Tingkat 1 (tombol): Formal-korporat | Hangat-natural | Netral-minimalis; tambahkan "atau ketik hex warna sendiri" di pesan pembuka. Tingkat 2: tampilkan palet kelompok terpilih sebagai tombol (nama + deretan hex di teks) atau daftar bernomor. Katalog 9 palet dan aturan warna baku ada di `references/palettes.md`.

Rekomendasi palet bisa jatuh di kelompok yang berbeda dari yang pengguna kira (mis. Timeless Elegance direkomendasikan untuk acara, padahal ada di Formal-korporat). Karena itu, di pesan tingkat 1 sebut nama palet yang direkomendasikan beserta kelompoknya, mis. "Untuk acara saya sarankan Serene Nature (Hangat-natural) atau Timeless Elegance (Formal-korporat)", agar pengguna memilih kelompok yang benar.

- Bila memilih "Ikuti dokumen" (c) atau "Arahan sendiri" (d), palet diambil dari dokumen/arahan; bila tidak ada warna disebut, tawarkan 3B.
- Palet hex buatan pengguna wajib dipetakan ke lima peran (Latar, Struktur, Aksen, Highlight, Sekunder) dan wajib memuat minimal satu warna gelap untuk Struktur. Bila tidak ada, sarankan warna gelap yang selaras dan minta persetujuan sebelum dipakai. Bila hasil akhirnya lebih dari 5 warna, minta pengguna memilih mana yang dibuang atau digabung.

### Langkah 4: Layout
Mode: tombol + ketik sendiri. Tanyakan berurutan (boleh digabung bila singkat):
- Jenis: Executive summary grid | Timeline/roadmap horizontal | Process/decision flow | Metric dashboard | Before-after | Tabel visual | Kartu per bagian | Isi sendiri. (Lebih dari 4 pilihan: tampilkan dua tingkat atau daftar bernomor; pola ada di `references/layouts.md`.)
- Jumlah gambar: 1 | 2 (isi + catatan) | 3-5 (per bagian/hari) | Isi sendiri. Materi padat (lebih dari sekitar 150 kata atau lebih dari 5 modul): rekomendasikan pecah jadi 2-3 gambar, sertakan alasannya.
- Penataan: padat informatif | lega minimalis | seimbang (disarankan).

Bila lebih dari 1 gambar, tetapkan elemen konsisten lintas gambar: palet, font, posisi header, gaya ikon, dan penomoran "1/3".

### Langkah 5: Ilustrasi
Mode: tombol + ketik sendiri.
- Tingkat: Ilustrasi penuh | Secukupnya, profesional (ikon kecil + 1 adegan per bagian utama) | Hanya ikon monoline | Tanpa ilustrasi | Isi sendiri.
- Jenis: ikon monoline | adegan flat vector | semi-realistis | Isi sendiri (TEXTBOX: objek/adegan spesifik).

Warna ilustrasi hanya tint dari Struktur, Aksen, dan Sekunder palet terpilih. Deteksi tema dari isi dan hanya pakai ikon/objek yang relevan dengan sumber (`references/icon-themes.md`); larang ikon yang tidak berkaitan. Jangan meminta foto realistis bila gayanya flat vector.

### Langkah 6: Konten
Mode: tombol, lalu TEXTBOX.
- Sumber (hanya bila ada dokumen DAN ringkasan): dokumen saja | ringkasan saja | keduanya digabung.
- Kedalaman: Ringkas (±60-100 kata di gambar) | Lengkap (±120-150 kata) | Lengkap + catatan (ditambah panel catatan: potensi masalah, jadwal kosong, selisih angka, konfirmasi tertunda, tindak lanjut).
- Bila Langkah 0 menemukan anomali, tawarkan memasukkannya sebagai panel "Catatan" meskipun pengguna memilih ringkas.
- Lalu TEXTBOX: "Ada teks, judul, atau bagian yang WAJIB tampil, atau yang sebaiknya dibuang?"

### Langkah 7: Penyajian data, angka, dan jadwal (hanya jika ada)
Mode: tombol + ketik sendiri.
- Angka: hero number besar | kartu KPI | bar/donut chart | tabel | disisipkan di teks.
- Jadwal/waktu: timeline horizontal | tabel per jam | kartu per hari | kalender visual | ringkas per hari tanpa jam.
- Perbandingan/biaya: tabel | bar chart | before-after.

Warna seri chart hanya dari palet terpilih. Beri rekomendasi menurut jumlah data; peringatkan bila jam terlalu banyak untuk terbaca di satu gambar.

### Langkah 8: Ringkasan konfirmasi
Tampilkan tabel singkat: platform, ukuran/resolusi, gaya, palet (nama + hex), layout, jumlah gambar, ilustrasi, konten dan kedalaman, penyajian data, anomali yang akan dimasukkan. Tandai item yang berasal dari rekomendasi otomatis.

### Langkah 9: Arahan tambahan (TEXTBOX)
Tanpa tombol: "Ada arahan tambahan atau hal yang harus dihindari? Ketik di sini, atau tulis 'lanjut'." Setelah dijawab, tanya: "Lanjut buat prompt, atau ada yang diubah?"

### Langkah 10: Rakit prompt
Baca `references/prompt-template.md` dan `references/platforms.md`. Ringkasnya:
- Instruksi prompt dalam bahasa Inggris; teks di dalam gambar berbahasa Indonesia (atau bahasa pilihan pengguna), verbatim dalam tanda kutip, dengan kalimat "Do not add any text that is not listed."
- Struktur wajib: layout + rasio/resolusi; COLOR PALETTE (blok disalin utuh); TYPOGRAPHY; HEADER; HERO ELEMENT; LAYOUT per zona (persentase); modul dengan isi dan ikon bertema; BOTTOM BANNER; FOOTER sumber; ILLUSTRATION STYLE; STYLE RULES; NEGATIVE (wajib memuat "any color outside the specified palette").
- Batas teks: judul <= 12 kata, action title <= 20 kata, blok <= 12 kata, bullet <= 8 kata, modul maks 5 per gambar, kecuali pengguna meminta lain.
- Hindari karakter khusus (panah, centang, simbol matematika) di teks gambar; minta digambar sebagai ikon.
- Satu code block per gambar dengan judul "Gambar 1 dari N: ...". Tidak boleh ada instruksi yang saling bertentangan.
- Midjourney: ringkas, tambah parameter. Mode tanpa teks: ganti semua teks dengan "empty text placeholder area".

### Langkah 11: QA diam-diam sebelum dikirim
Periksa (jangan ditampilkan sebagai daftar ke pengguna):
- semua hex sama persis dengan palet terpilih, tanpa varian
- Highlight hanya di angka kritis dan badge hero
- lingkaran nomor memakai Struktur/Aksen
- tidak ada penanda status berwarna lampu lalu lintas
- angka/nama/tanggal sama dengan sumber; tidak ada fakta baru
- teks dalam batas kata; tidak ada karakter khusus di teks gambar
- ikon sesuai tema dan sumber
- elemen konsisten antar gambar (bila lebih dari 1)
- hero metric dan negative prompt ada
- anomali masuk bila disetujui
- format sesuai platform; tidak ada instruksi yang bertentangan

Perbaiki dulu sebelum mengirim.

## Aturan warna baku (ringkas; rincian di palettes.md)

Berlaku untuk SEMUA palet dan tidak boleh dilonggarkan, karena model gambar cenderung "mengarang" warna tambahan dan warna lampu lalu lintas kalau tidak dikunci:
- Tulis hex persis seperti katalog; tidak ada varian hex. Hanya 5 warna palet terpilih; variasi nilai hanya lewat opasitas/tint warna yang sama.
- Teks terang di atas Struktur/Aksen memakai putih.
- Highlight hanya untuk angka kritis dan badge hero.
- Status: setuju/selesai/boleh = Struktur + ikon centang; ditolak/dilarang/bermasalah = Aksen + ikon silang atau segitiga peringatan. Tanpa hijau/merah/kuning sebagai penanda status.
- Pihak A = Struktur, pihak B = Aksen, konsisten di seluruh gambar.
- Tanpa neon dan tanpa gradien murahan.

## Format jawaban akhir

1. Satu kalimat pembuka: gaya, palet, layout, dan tema visual yang dipakai.
2. Prompt (satu code block per gambar, berjudul "Gambar 1 dari N: ...").
3. Catatan singkat (maks 4 butir): asumsi, bagian yang dipangkas, ambiguitas sumber, saran bila teks gambar rusak.
4. Tawaran: versi lebih ringkas, pecah/gabung gambar, ganti palet atau gaya.

Untuk revisi, ubah prompt sebelumnya (jangan mulai dari nol) dan kirim hanya gambar/bagian yang berubah beserta ringkasan perubahannya.
