# Hasil uji auto-img-prompt-v1 (iterasi 1)

Cara uji: saya menjalankan skill sendiri untuk tiap skenario (memerankan Claude dan pengguna dalam satu alur), jadi ini sanity check, bukan uji dengan pengguna nyata. Prompt gambar belum dirender di platform AI sungguhan. Semua data uji fiktif.

| # | Skenario | Hasil | Catatan utama |
|---|---|---|---|
| 1 | Tema saja | Lulus | Tidak ada angka karangan; hero berupa pesan kunci |
| 2 | Dokumen padat + anomali | Lulus | 3 anomali terdeteksi; dipecah 2 gambar; ada temuan #1 (sudah diperbaiki) |
| 3 | Arahan sendiri + hex sendiri | Lulus | Struktur gelap disarankan lalu disetujui |
| 4 | Ikuti rekomendasi semua | Lulus dengan catatan | Tetap menanyakan platform; butuh keputusan Anda (#3) |
| 5 | Midjourney + teks padat | Lulus | Mode tanpa teks ditawarkan; 6 langkah dipecah 3+3 |
| 6 | Serene Nature + status | Lulus dengan catatan | Tanpa warna lampu lalu lintas; ada risiko makna Aksen (#2) |

---

## Skenario 1: Tema saja tanpa dokumen

**Pesan pengguna:** "Buatkan prompt infografis tentang keselamatan di persimpangan jalan hauling."

**Alur:**
1. Langkah 0: tidak ada sumber. Claude bertanya (tombol): "Ada materi untuk ditempel, atau cukup tema umum?" Pengguna: "Cukup tema umum." Tanpa sumber, tidak ada angka, hero metric = tidak ada.
2. Mode pemanduan (tombol): pengguna memilih "Campuran".
3. Teknis diambil dari rekomendasi: platform ditanyakan (ChatGPT Image), 16:9 standar, layout Executive summary grid (banyak kategori), 1 gambar, ilustrasi "Secukupnya, profesional", penataan seimbang.
4. Gaya (ditanya): Elegan konsultan. Palet: McKinsey (tema K3/operasional formal).
5. Konten: "Lengkap" (tidak ada anomali). Teks wajib/dibuang: "tidak ada".

**Ringkasan Langkah 8:** ChatGPT Image | 16:9, 1920x1080 | Elegan konsultan | McKinsey #F7F4EF / #0B1F3A / #5A0F1E / #C9A227 / #D9DCE1 | Executive summary grid | 1 gambar | Ikon monoline + 1 adegan kecil | Lengkap | Tanpa angka | Anomali: tidak ada.

**Keluaran:**

Memakai gaya elegan konsultan dengan palet McKinsey, layout grid ringkasan eksekutif, dan ikon monoline bertema jalan tambang.

**Gambar 1 dari 1: Keselamatan di Persimpangan Jalan Hauling**

```
Create a 16:9 landscape executive-consultant infographic at standard resolution (1920x1080), titled "Keselamatan di Persimpangan Jalan Hauling". Clean grid of four equal cards under a header, calm and authoritative mood.

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: #F7F4EF
- Structure (header, body panels, banners, hero card; dark): #0B1F3A
- Accent (section titles, badges, icons, key callouts): #5A0F1E
- Highlight (ONLY for critical numbers and the hero badge): #C9A227
- Secondary (dividers, card borders, neutral elements): #D9DCE1
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.

TYPOGRAPHY: elegant serif for titles, clean sans-serif for body text; bold titles, regular body; consistent sizes; high contrast; fully legible.

HEADER (top 15%): small uppercase label "K3 JALAN TAMBANG" in Accent; title "Keselamatan di Persimpangan Jalan Hauling"; subtitle "Empat kebiasaan yang menjaga semua unit tetap aman"; action headline "Persimpangan aman bila rambu, kecepatan, komunikasi, dan pengawasan berjalan bersama."

HERO ELEMENT (15%): Structure card with white text "Satu persimpangan, empat pengaman." and a round badge showing the number "4" in Highlight color.

LAYOUT (zones): Zone 1 header 15% | Zone 2 hero 15% | Zone 3 four module cards in one row 55% | Zone 4 bottom banner 10% | Zone 5 footer 5%.

MODULES (4 total; cards with thin Secondary border and a circular number marker in Structure):
1. "Rambu dan marka jelas" - icon: warning-triangle road sign. Text: "Mudah terlihat dari jauh", "Selalu bersih dan terawat".
2. "Kecepatan aman" - icon: dump truck approaching an intersection. Text: "Kurangi kecepatan sebelum persimpangan", "Siap berhenti kapan saja".
3. "Komunikasi antar unit" - icon: radio handset. Text: "Informasikan posisi lewat radio", "Pastikan unit lain mengetahui".
4. "Pengawasan rutin" - icon: clipboard with magnifier. Text: "Inspeksi persimpangan secara berkala", "Tindak lanjuti temuan segera".

BOTTOM BANNER: Structure band with white text: "Berhenti, lihat, pastikan, baru lanjut."

FOOTER: "Materi umum untuk diskusi keselamatan" and page marker "1/1" in Secondary tint.

ILLUSTRATION STYLE: monoline icons plus one small flat-vector haul-road intersection scene at 8-10% opacity behind the hero card; allowed objects only: dump truck, excavator, helmet, warning-triangle sign, radio handset, clipboard, road intersection, bench contour lines; not allowed: people faces, brand logos, unrelated decorative icons; colors only tints of Structure, Accent, Secondary.

STYLE RULES: clean grid, precise alignment, consistent icon stroke, text fully legible, no overlapping text, rounded-corner cards with thin Secondary borders. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

Catatan:
- Materi bersifat umum dan tanpa angka, jadi hero berupa pesan kunci; tukar dengan aturan resmi lokasi Anda bila ada.
- Isi empat modul adalah praktik umum, bukan kutipan SOP tertentu.
- Bila ejaan teks bergeser, kirim ulang hanya blok yang salah.

Mau versi lebih ringkas, dipecah jadi 2 gambar, atau ganti palet/gaya?

**QA:** hex persis; Highlight hanya di badge "4"; nomor lingkaran Struktur; tanpa penanda status; tidak ada angka dari luar sumber; batas kata terpenuhi; ikon relevan. Lulus.

---

## Skenario 2: Dokumen padat, jadwal 3 hari, angka anggaran tidak cocok

**Sumber yang ditempel:**
> Gathering Tim Engineering. Lokasi: Villa Bukit Indah (TBC). Peserta: 42 orang.
> Hari 1, Sabtu 12 Desember 2026: 07.00 berangkat, 11.00 check-in, 13.00 sesi sharing, 19.00 api unggun.
> Hari 2, Minggu 13 Desember 2026: 06.00 olahraga pagi, 09.00 outbound, 14.00 lomba antar seksi, 20.00 malam apresiasi.
> Hari 3, Selasa 15 Desember 2026: 07.00 sarapan, 09.00 evaluasi, 12.00 check-out, 15.00 tiba kembali.
> Anggaran: Transport Rp 18.000.000; Akomodasi Rp 24.500.000; Konsumsi Rp 9.000.000; Kegiatan Rp 7.500.000; Total Rp 61.000.000.

**Langkah 0 (diam-diam):** hero metric = Rp 61.000.000. Anomali: (a) tanggal 13 ke 15 Desember, 14 Desember kosong; (b) jumlah rincian Rp 59.000.000 tidak sama dengan total tertulis Rp 61.000.000 (selisih Rp 2.000.000); (c) lokasi berstatus TBC.

**Alur:**
1. Mode: "Dipandu penuh".
2. Platform: ChatGPT Image. Ukuran: 16:9 standar (jadwal mendatar).
3. Gaya: Ilustratif (disarankan, tema acara). Palet tingkat 1: Claude menyebut "Serene Nature (Hangat-natural) atau Timeless Elegance (Formal-korporat)"; pengguna memilih Formal-korporat, lalu Timeless Elegance.
4. Layout: kartu per hari; jumlah gambar: Claude menyarankan 2 karena materi padat (lebih dari 150 kata, lebih dari 5 modul): gambar 1 jadwal, gambar 2 anggaran + catatan. Penataan seimbang.
5. Ilustrasi: adegan flat vector.
6. Konten: Lengkap + catatan; anomali ditawarkan sebagai panel "Catatan", pengguna setuju. Wajib tampil: "Villa Bukit Indah". Dibuang: tidak ada.
7. Data: kartu per hari dengan jam kunci (4 per hari); biaya: tabel + hero number.
8. Arahan tambahan: "lanjut".

**Ringkasan Langkah 8:** ChatGPT Image | 16:9 standar | Ilustratif | Timeless Elegance #F0E5D8 / #2E4052 / #C84B31 / #D9BF77 / #A5C9CA | Kartu per hari + tabel biaya | 2 gambar | Adegan flat vector | Lengkap + catatan | Hero: Rp 61.000.000 | Anomali: tanggal loncat, selisih total, lokasi TBC.

**Keluaran:**

Memakai gaya ilustratif dengan palet Timeless Elegance, kartu per hari dan tabel anggaran, bertema acara luar ruang (bus, tenda, api unggun).

**Gambar 1 dari 2: Jadwal Kegiatan Tiga Hari**

```
Create a 16:9 landscape illustrative infographic at standard resolution (1920x1080), titled "Jadwal Kegiatan Tiga Hari". Three day-cards side by side with a thin timeline connector, warm and lively outdoor-event mood. This is image 1 of 2 and shares palette, fonts, header position, icon style and footer with image 2.

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: #F0E5D8
- Structure (header, body panels, banners, hero card; dark): #2E4052
- Accent (section titles, badges, icons, key callouts): #C84B31
- Highlight (ONLY for critical numbers and the hero badge): #D9BF77
- Secondary (dividers, card borders, neutral elements): #A5C9CA
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.

TYPOGRAPHY: friendly serif for titles, clean sans-serif for body; bold titles, regular body; consistent sizes; high contrast.

HEADER (top 15%): small uppercase label "GATHERING TIM ENGINEERING" in Accent; title "Jadwal Kegiatan Tiga Hari"; subtitle "Villa Bukit Indah"; action headline "Tiga hari penuh: sharing, outbound, apresiasi, lalu evaluasi dan kepulangan."

HERO ELEMENT (15%): Structure card with the number "42" in Highlight color and caption "peserta" in white.

LAYOUT (zones): Zone 1 header 15% | Zone 2 hero 15% | Zone 3 three day-cards in a row 55% | Zone 4 bottom banner 10% | Zone 5 footer 5%.

MODULES (3 day-cards; circular day marker in Structure):
1. "Hari 1: Sabtu, 12 Desember 2026" - icon: bus. Text: "07.00 Berangkat", "11.00 Check-in", "13.00 Sesi sharing", "19.00 Api unggun".
2. "Hari 2: Minggu, 13 Desember 2026" - icon: tent. Text: "06.00 Olahraga pagi", "09.00 Outbound", "14.00 Lomba antar seksi", "20.00 Malam apresiasi".
3. "Hari 3: Selasa, 15 Desember 2026" - icon: flag. Text: "07.00 Sarapan", "09.00 Evaluasi", "12.00 Check-out", "15.00 Tiba kembali".
Between card 2 and card 3, draw a small warning-triangle icon in Accent on the timeline connector (no text).

BOTTOM BANNER: Structure band with white text: "Lokasi villa masih menunggu konfirmasi."

FOOTER: "Sumber: rencana gathering tim Engineering" and page marker "1/2" in Secondary tint.

ILLUSTRATION STYLE: flat vector scenes, no gradients, small scene at 8-10% opacity behind each card; allowed objects only: bus, tent, campfire, flag, dining table, people silhouettes without faces; not allowed: brand logos, photorealistic elements, unrelated decorative icons; colors only tints of Structure, Accent, Secondary.

STYLE RULES: clean grid, precise alignment, consistent icon stroke, text fully legible, no overlapping text, rounded-corner cards with thin Secondary borders. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

**Gambar 2 dari 2: Anggaran dan Catatan**

```
Create a 16:9 landscape illustrative infographic at standard resolution (1920x1080), titled "Anggaran dan Catatan". Left side a clean budget table, right side a notes panel, warm and orderly mood. This is image 2 of 2 and shares palette, fonts, header position, icon style and footer with image 1.

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: #F0E5D8
- Structure (header, body panels, banners, hero card; dark): #2E4052
- Accent (section titles, badges, icons, key callouts): #C84B31
- Highlight (ONLY for critical numbers and the hero badge): #D9BF77
- Secondary (dividers, card borders, neutral elements): #A5C9CA
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.

TYPOGRAPHY: friendly serif for titles, clean sans-serif for body; bold titles, regular body; consistent sizes; high contrast.

HEADER (top 15%): small uppercase label "GATHERING TIM ENGINEERING" in Accent; title "Anggaran dan Catatan"; subtitle "Rincian biaya dan hal yang perlu dikonfirmasi"; action headline "Total anggaran tercantum perlu dicocokkan dengan jumlah rincian biaya."

HERO ELEMENT (15%): Structure card with "Rp 61.000.000" in Highlight color and caption "total tercantum" in white.

LAYOUT (zones): Zone 1 header 15% | Zone 2 hero 15% | Zone 3 table (left 55% width) and notes panel (right 45% width) 55% | Zone 4 bottom banner 10% | Zone 5 footer 5%.

MODULES (2):
1. "Rincian anggaran" - icon: coins. Table with Structure header row and white text, rows alternate Secondary tint: "Transport" "Rp 18.000.000"; "Akomodasi" "Rp 24.500.000"; "Konsumsi" "Rp 9.000.000"; "Kegiatan" "Rp 7.500.000"; final row on Structure with white text: "Total tercantum" "Rp 61.000.000".
2. "Catatan" - icon: warning triangle in Accent. Text: "Jumlah rincian Rp 59.000.000", "Selisih dengan total: Rp 2.000.000", "Tanggal 14 Desember tanpa kegiatan", "Lokasi villa belum dikonfirmasi".

BOTTOM BANNER: Structure band with white text: "Mohon konfirmasi total, tanggal, dan lokasi."

FOOTER: "Sumber: rencana gathering tim Engineering" and page marker "2/2" in Secondary tint.

ILLUSTRATION STYLE: flat vector, one small coins-and-calculator scene at 8-10% opacity behind the table; allowed objects only: coins, calculator, invoice document, bus, tent; not allowed: brand logos, photorealistic elements, unrelated decorative icons; colors only tints of Structure, Accent, Secondary.

STYLE RULES: clean grid, precise alignment, consistent icon stroke, text fully legible, no overlapping text, rounded-corner cards with thin Secondary borders. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

Catatan:
- Angka tabel dan total ditulis persis seperti sumber. Rp 59.000.000 dan Rp 2.000.000 adalah hitungan saya dari rincian, bukan angka sumber; hapus dari panel bila tidak diinginkan.
- Hanya jam kunci (4 per hari) yang dimuat agar terbaca.
- Hari 1 sampai 3 memakai nama hari yang sesuai kalender 2026.

**QA:** hex persis di kedua prompt; Highlight hanya di angka "42" dan "Rp 61.000.000"; penanda hari Struktur; peringatan memakai Aksen + segitiga; angka sama dengan sumber; elemen konsisten lintas gambar; anomali masuk. Lulus.

---

## Skenario 3: "Arahan sendiri" dan palet hex buatan sendiri

**Pesan pengguna:** "Buatkan prompt poster ajakan menanam bibit untuk reklamasi lahan bekas tambang."

**Alur:**
1. Langkah 0: tidak ada sumber, tema umum; mode "Dipandu penuh".
2. Platform: Gemini. Ukuran: 4:5 vertikal (poster), kualitas standar.
3. Gaya (3A): pengguna memilih "Arahan sendiri". Claude bertanya tanpa tombol; pengguna mengetik: "Poster retro koran 70-an, font slab serif tebal, tekstur kertas halus, tanpa foto, kesan hangat dan optimis." Dipakai apa adanya.
4. Palet (3B): pengguna mengetik "hex sendiri": #F4EDE4, #3D8361, #F2B5A7, #E5D9C8.
5. Claude memetakan: Latar #F4EDE4 | Aksen #3D8361 | Highlight #F2B5A7 | Sekunder #E5D9C8, lalu: "Belum ada warna gelap untuk Struktur. Saya sarankan #1F3D2E (hijau tua selaras Aksen). Setuju?" Pengguna: "Setuju." Total tepat 5 warna, tidak ada yang dibuang.
6. Layout: Process flow (4 langkah menanam), 1 gambar. Ilustrasi: ikon monoline + 1 ilustrasi besar bibit. Konten: Ringkas. Tanpa angka.
7. Arahan tambahan: "lanjut".

**Keluaran:**

Memakai gaya retro koran 70-an sesuai arahan Anda dengan palet buatan sendiri (Struktur hijau tua #1F3D2E ditambahkan atas persetujuan), layout alur empat langkah, dan ikon monoline bertema reklamasi.

**Gambar 1 dari 1: Mari Tanam Harapan di Lahan Reklamasi**

```
Create a 4:5 vertical portrait retro 1970s newspaper-style poster at standard resolution, titled "Mari Tanam Harapan di Lahan Reklamasi". Heavy slab-serif masthead, fine subtle paper grain at 5% opacity using the Secondary tint, no photographs, warm and optimistic mood, a vertical process flow of four steps.

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: #F4EDE4
- Structure (header, body panels, banners, hero card; dark): #1F3D2E
- Accent (section titles, badges, icons, key callouts): #3D8361
- Highlight (ONLY for critical numbers and the hero badge): #F2B5A7
- Secondary (dividers, card borders, neutral elements): #E5D9C8
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.

TYPOGRAPHY: heavy slab serif for the masthead and titles, clean condensed sans-serif for body; strong contrast; newspaper-column rhythm.

HEADER (top 18%): Structure masthead band with thin Secondary double rule; small uppercase label "AJAKAN REKLAMASI" in white; title "Mari Tanam Harapan di Lahan Reklamasi" in white slab serif; subtitle "Satu bibit hari ini, hijau untuk esok hari".

HERO ELEMENT (22%): large flat-vector seedling growing from layered soil inside a Structure-colored circle, with a round hero badge reading "AYO TANAM" in Highlight color.

LAYOUT (zones): Zone 1 masthead 18% | Zone 2 hero 22% | Zone 3 four steps stacked vertically 45% | Zone 4 bottom banner 10% | Zone 5 footer 5%.

MODULES (4 steps; circular number markers in Structure):
1. "Siapkan lahan" - icon: layered soil with shovel. Text: "Rapikan dan gemburkan tanah".
2. "Tanam bibit" - icon: seedling in a planting hole. Text: "Tanam bibit pada lubang tanam".
3. "Siram dan rawat" - icon: water drop and watering can. Text: "Siram dan jaga bibit tetap sehat".
4. "Pantau pertumbuhan" - icon: leaf with magnifier. Text: "Amati pertumbuhan secara berkala".

BOTTOM BANNER: Accent band with white text: "Ayo bergerak bersama untuk lahan yang kembali hijau."

FOOTER: "Poster ajakan reklamasi" and page marker "1/1" in Secondary tint.

ILLUSTRATION STYLE: monoline icons and one flat-vector seedling hero illustration; allowed objects only: seedling, leaf, soil layers, shovel, water drop, watering can, magnifier; not allowed: photographs, brand logos, people faces, unrelated decorative icons; colors only tints of Structure, Accent, Secondary.

STYLE RULES: retro newspaper column feel, clean alignment, consistent icon stroke, text fully legible, no overlapping text. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, photographs, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

Catatan:
- Isi langkah menanam bersifat umum dan tanpa angka; sesuaikan dengan prosedur reklamasi lokasi Anda.
- #1F3D2E adalah usulan saya untuk Struktur dan sudah Anda setujui; tidak ada hex lain di luar lima warna.
- Highlight pink #F2B5A7 hanya terbaca di atas warna gelap, jadi ditaruh pada badge hero.

**QA:** arahan gaya dipakai apa adanya; 5 hex persis; Highlight hanya di badge hero; lingkaran nomor Struktur; "tekstur kertas" dibatasi 5% opacity memakai tint Sekunder sehingga tidak menambah hex atau gradien. Lulus.

---

## Skenario 4: "Ikuti rekomendasi semua"

**Pesan pengguna:** "Buatkan prompt infografis dari ringkasan ini, ikuti rekomendasi semua. Ringkasan kinerja produksi Triwulan III 2026: produksi 1,2 juta ton; target 1,1 juta ton; pencapaian 109%; stripping ratio 6,8; kendala utama hujan 14 hari."

**Alur:**
1. Langkah 0 diam-diam: hero = 109%; pengecekan 1,2 / 1,1 = sekitar 109%, konsisten, anomali tidak ada.
2. Mode sudah ditentukan pengguna ("ikuti rekomendasi semua"), jadi pertanyaan mode dilewati.
3. Satu-satunya pertanyaan: platform (tombol). Pengguna: ChatGPT Image.
4. Default diterapkan dengan alasan satu kalimat per baris, lalu Langkah 8 langsung ditampilkan.

**Ringkasan Langkah 8 (yang ditampilkan):**

| Item | Pilihan | Alasan |
|---|---|---|
| Platform | ChatGPT Image | dipilih pengguna |
| Ukuran | 16:9, 1920x1080 (rekomendasi otomatis) | laporan mendatar untuk presentasi |
| Gaya | Elegan konsultan (rekomendasi otomatis) | materi kinerja formal |
| Palet | McKinsey (rekomendasi otomatis) | dokumen korporat |
| Layout | Metric dashboard (rekomendasi otomatis) | angka/KPI dominan |
| Jumlah gambar | 1 (rekomendasi otomatis) | materi hanya sekitar 25 kata |
| Ilustrasi | Secukupnya, profesional (rekomendasi otomatis) | gaya konsultan |
| Konten | Lengkap (rekomendasi otomatis) | tidak ada anomali |
| Data | Hero number + kartu KPI + bar chart 2 batang (rekomendasi otomatis) | satu angka dominan |
| Anomali | tidak ada | |

Langkah 9: "Ada arahan tambahan? Ketik, atau tulis 'lanjut'." Pengguna: "lanjut."

**Keluaran:**

Memakai gaya elegan konsultan dengan palet McKinsey, layout dashboard metrik, dan ikon monoline bertema produksi tambang.

**Gambar 1 dari 1: Kinerja Produksi Triwulan III**

```
Create a 16:9 landscape executive-consultant metric dashboard at standard resolution (1920x1080), titled "Kinerja Produksi Triwulan III". One dominant hero number, four small KPI cards, and one two-bar chart, authoritative and calm mood.

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: #F7F4EF
- Structure (header, body panels, banners, hero card; dark): #0B1F3A
- Accent (section titles, badges, icons, key callouts): #5A0F1E
- Highlight (ONLY for critical numbers and the hero badge): #C9A227
- Secondary (dividers, card borders, neutral elements): #D9DCE1
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.

TYPOGRAPHY: elegant serif for titles and hero number, clean sans-serif for body; bold titles, regular body; consistent sizes; high contrast.

HEADER (top 15%): small uppercase label "LAPORAN KINERJA" in Accent; title "Kinerja Produksi Triwulan III"; subtitle "Triwulan III 2026"; action headline "Produksi melampaui target, namun hujan 14 hari menjadi kendala utama."

HERO ELEMENT (25%): Structure card with "109%" in very large Highlight numerals and caption "pencapaian terhadap target" in white.

LAYOUT (zones): Zone 1 header 15% | Zone 2 hero (left 40% width) and bar chart (right 60% width) 25% | Zone 3 four KPI cards in one row 40% | Zone 4 bottom banner 10% | Zone 5 footer 10% including source line.

MODULES (4 KPI cards, thin Secondary border):
1. "Produksi" - icon: dump truck. Text: "1,2 juta ton".
2. "Target" - icon: bullseye. Text: "1,1 juta ton".
3. "Stripping ratio" - icon: bench pit contour. Text: "6,8".
4. "Hari hujan" - icon: rain cloud. Text: "14 hari".
Bar chart: two vertical bars, "Produksi" in Structure and "Target" in Secondary, labeled directly "1,2 juta ton" and "1,1 juta ton".

BOTTOM BANNER: Structure band with white text: "Target terlampaui meski ada kendala hujan 14 hari."

FOOTER: "Sumber: ringkasan kinerja produksi Triwulan III 2026" and page marker "1/1" in Secondary tint.

ILLUSTRATION STYLE: monoline icons only, one small flat-vector pit scene at 8-10% opacity behind the hero card; allowed objects only: dump truck, excavator, bullseye, bench contour lines, rain cloud, helmet; not allowed: people faces, brand logos, unrelated decorative icons; colors only tints of Structure, Accent, Secondary.

STYLE RULES: clean grid, precise alignment, consistent icon stroke, text fully legible, no overlapping text, rounded-corner cards with thin Secondary borders. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

Catatan:
- Semua angka sama dengan ringkasan; tidak ada angka tambahan.
- Banner hanya mengulang fakta sumber (target terlampaui, hujan 14 hari), tanpa rekomendasi baru.
- Platform tetap ditanya satu kali; lihat temuan #3.

**QA:** hex persis; Highlight hanya di "109%"; tidak ada penanda status; angka sesuai sumber; hero dan NEGATIVE ada. Lulus.

---

## Skenario 5: Midjourney dengan materi bersisi teks padat

**Pesan pengguna:** "Buatkan prompt Midjourney untuk infografis SOP P2H ini: 1) periksa kondisi ban dan velg; 2) periksa level oli mesin dan air radiator; 3) periksa rem dan klakson; 4) periksa lampu dan alarm mundur; 5) periksa kebocoran hidrolik; 6) isi form dan laporkan temuan ke pengawas."

**Alur:**
1. Langkah 0: 6 langkah berurutan, tidak ada angka, tidak ada anomali. Mode: "Campuran".
2. Platform (tombol): Midjourney. Claude mendeteksi materi bersisi teks padat dan menawarkan tombol: "Mode tanpa teks (disarankan)" | "Tetap dengan teks" | "Ganti platform" | "Isi sendiri". Alasan satu kalimat: Midjourney lemah merender teks padat, jadi teks lebih aman ditambahkan manual di Canva/PowerPoint. Pengguna memilih "Mode tanpa teks".
3. Teknis dari rekomendasi: 16:9 standar; layout Process flow; karena 6 langkah melebihi 5 modul, Claude menyarankan 2 gambar (3+3) beserta alasannya; ilustrasi ikon monoline.
4. Gaya (ditanya): Elegan konsultan; palet McKinsey.

**Keluaran:**

Memakai gaya elegan konsultan dengan palet McKinsey, alur langkah horizontal, ikon monoline bertema pemeriksaan unit, dalam mode tanpa teks untuk Midjourney.

**Gambar 1 dari 2: Langkah 1 sampai 3**

```
Landscape process infographic on a clean consultant grid, dark header band at top with an empty text placeholder area for a title and a smaller empty text placeholder area for a subtitle, three evenly spaced step cards left to right joined by a thin drawn line, each card with an empty circle marker (no digits), a monoline icon (1: tire and wheel rim, 2: engine oil dipstick and radiator, 3: brake pedal and horn), an empty text placeholder area for a heading and two empty text placeholder lines, a dark bottom banner with an empty text placeholder area, a thin footer strip with an empty text placeholder area. Palette strictly #F7F4EF background, #0B1F3A dark structure and circle markers, #5A0F1E accent for icons and badge outline, #C9A227 highlight only for one small round badge near the title, #D9DCE1 dividers and card borders, no other colors, no variants, white on dark areas, flat monoline style, thin borders, no gradients, no neon, no traffic-light colors, no readable text, no letters, no numbers, no logos, no watermarks --ar 16:9
```

**Gambar 2 dari 2: Langkah 4 sampai 6**

```
Landscape process infographic on a clean consultant grid, dark header band at top with an empty text placeholder area for a title and a smaller empty text placeholder area for a subtitle, three evenly spaced step cards left to right joined by a thin drawn line, each card with an empty circle marker (no digits), a monoline icon (4: headlight and reverse alarm speaker, 5: hydraulic hose with a drop, 6: clipboard form with pen), an empty text placeholder area for a heading and two empty text placeholder lines, a dark bottom banner with an empty text placeholder area, a thin footer strip with an empty text placeholder area. Palette strictly #F7F4EF background, #0B1F3A dark structure and circle markers, #5A0F1E accent for icons and badge outline, #C9A227 highlight only for one small round badge near the title, #D9DCE1 dividers and card borders, no other colors, no variants, white on dark areas, flat monoline style, thin borders, no gradients, no neon, no traffic-light colors, no readable text, no letters, no numbers, no logos, no watermarks --ar 16:9
```

**Teks untuk ditambahkan manual (Canva/PowerPoint):**

| Zona | Gambar 1 | Gambar 2 |
|---|---|---|
| Judul | Pemeriksaan Unit Harian (P2H) | Pemeriksaan Unit Harian (P2H) |
| Subjudul | Langkah 1 sampai 3 | Langkah 4 sampai 6 |
| Kartu 1 | Ban dan velg: periksa kondisi | Lampu dan alarm mundur: periksa |
| Kartu 2 | Oli mesin dan air radiator: periksa level | Kebocoran hidrolik: periksa |
| Kartu 3 | Rem dan klakson: periksa | Form: isi dan laporkan temuan ke pengawas |
| Banner | (isi sendiri) | (isi sendiri) |
| Footer | 1/2 | 2/2 |

Catatan:
- Mode tanpa teks: gambar berisi area kosong; semua teks Anda ketik sendiri memakai tabel di atas.
- Cek sintaks parameter Midjourney versi terbaru sebelum menjalankan; `--ar 16:9` saya pakai sesuai spesifikasi.
- Enam langkah dipecah 3+3 agar tiap gambar tetap longgar.

**QA:** hex persis; Highlight hanya untuk satu badge; tidak ada teks terbaca di prompt; parameter rasio ada; pecahan konsisten (palet, ikon, posisi header sama). Lulus.

---

## Skenario 6: Serene Nature dengan konten status

**Pesan pengguna:** "Prompt infografis status persetujuan usulan: A) Penambahan jam kerja alat, disetujui; B) Relokasi sump, ditolak; C) Perpanjangan kontrak vendor, disetujui; D) Penambahan unit dump truck, ditolak (menunggu anggaran). Pakai palet Serene Nature."

**Alur:**
1. Langkah 0: hero = "2 dari 4 usulan disetujui"; tanpa anomali. Mode: "Campuran".
2. Platform: ChatGPT Image; 16:9; layout Tabel visual (daftar dengan status); 1 gambar; ikon monoline; konten Lengkap.
3. Gaya: Elegan konsultan. Palet: Serene Nature diminta langsung oleh pengguna, jadi tidak ditanya.
4. Claude memetakan peran dan menetapkan aturan status: Disetujui = Struktur #1D3557 + ikon centang; Ditolak = Aksen #ED553B + ikon silang. Hijau muda Sekunder #A8D8B9 dan kuning Highlight #F6D55C tidak dipakai untuk status. Garis belang tabel diberi merata di semua baris (tidak mengikuti status) agar hijau muda tidak terbaca sebagai "setuju".

**Keluaran:**

Memakai gaya elegan konsultan dengan palet Serene Nature, layout tabel status, dan ikon monoline bertema persetujuan dokumen.

**Gambar 1 dari 1: Status Persetujuan Usulan**

```
Create a 16:9 landscape executive-consultant infographic at standard resolution (1920x1080), titled "Status Persetujuan Usulan". A clean visual table of four proposals with a status column, one hero number card, calm and authoritative mood.

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: #F1F1F1
- Structure (header, body panels, banners, hero card; dark): #1D3557
- Accent (section titles, badges, icons, key callouts): #ED553B
- Highlight (ONLY for critical numbers and the hero badge): #F6D55C
- Secondary (dividers, card borders, neutral elements): #A8D8B9
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.
Role restrictions for this image: Secondary (light green) is used ONLY for dividers, card borders and uniform alternating row stripes applied identically to every row regardless of status, never to mark approval. Highlight (yellow) is used ONLY for the hero number, never to mark caution. Accent (orange-red) is used ONLY for the small label, the badge outline and "Ditolak" items with a cross icon, never as a generic alert color. Section titles use Structure.

TYPOGRAPHY: elegant serif for titles and hero number, clean sans-serif for table text; bold titles, regular body; consistent sizes; high contrast.

HEADER (top 15%): small uppercase label "PERSETUJUAN USULAN" in Accent; title "Status Persetujuan Usulan"; subtitle "Perubahan rencana kerja"; action headline "Dua dari empat usulan disetujui, dua lainnya ditolak."

HERO ELEMENT (20%): Structure card with "2 dari 4" in large Highlight numerals and caption "usulan disetujui" in white.

LAYOUT (zones): Zone 1 header 15% | Zone 2 hero 20% | Zone 3 table 50% | Zone 4 bottom banner 10% | Zone 5 footer 5%.

MODULES (1 table, header row in Structure with white text, columns "Kode", "Usulan", "Status", "Catatan"):
- Row A: "Penambahan jam kerja alat" | status pill in Structure with white check icon and the word "Disetujui".
- Row B: "Relokasi sump" | status pill in Accent with white cross icon and the word "Ditolak".
- Row C: "Perpanjangan kontrak vendor" | status pill in Structure with white check icon and the word "Disetujui".
- Row D: "Penambahan unit dump truck" | status pill in Accent with white cross icon and the word "Ditolak" | note "Menunggu anggaran".
Row codes "A", "B", "C", "D" in circular markers in Structure.

BOTTOM BANNER: Structure band with white text: "Dua usulan disetujui, dua usulan ditolak."

FOOTER: "Sumber: daftar usulan perubahan rencana kerja" and page marker "1/1" in Secondary tint.

ILLUSTRATION STYLE: monoline icons only (document with check, document with cross, helmet, truck); allowed objects only: document, stamp, clipboard, dump truck, excavator, sump pond outline; not allowed: logos, people faces, unrelated decorative icons; colors only tints of Structure, Accent, Secondary.

STYLE RULES: clean grid, precise alignment, consistent icon stroke, text fully legible, no overlapping text, rounded-corner cards with thin Secondary borders. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, green for approved, yellow for warning, red as generic alert, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

Catatan:
- Status dibedakan lewat ikon dan kontras Struktur versus Aksen, bukan lewat hijau/kuning/merah.
- "Menunggu anggaran" ditulis seperti pada keterangan Anda.
- Judul seksi saya buat Struktur dan Aksen dibatasi (lihat temuan #2).

**QA:** hex persis; tidak ada hijau/merah/kuning sebagai penanda status; setuju = Struktur + centang, ditolak = Aksen + silang; Highlight hanya di hero "2 dari 4"; NEGATIVE memuat larangan traffic-light. Lulus.

---

## Temuan dan keputusan yang saya minta

1. **Sudah diperbaiki.** Rekomendasi palet bisa lintas kelompok (Timeless Elegance direkomendasikan untuk acara, tetapi ada di Formal-korporat). Sekarang pesan tingkat 1 menyebut nama palet rekomendasi beserta kelompoknya. Ini muncul di skenario 2.
2. **Butuh keputusan Anda.** Pada palet yang Aksen-nya merah-oranye (Serene Nature), memakai Aksen untuk judul seksi di gambar bernuansa status membuat Aksen terbaca sebagai "ditolak". Di skenario 6 saya memakai Struktur untuk judul seksi. Usul: jadikan aturan tetap, "pada konten status, judul seksi memakai Struktur dan Aksen khusus untuk item bermasalah". Ini memperketat aturan, bukan melonggarkan, tetapi mengubah peran Aksen yang Anda tetapkan, jadi saya tidak memasukkannya tanpa persetujuan Anda.
3. **Butuh keputusan Anda.** Pada "ikuti rekomendasi semua", saya tetap menanyakan platform satu kali karena tidak bisa disimpulkan dari tema (sesuai aturan platform Anda). Bila Anda ingin nol pertanyaan, defaultnya bisa ChatGPT Image.
4. **Keterbatasan uji.** Saya memerankan dua sisi percakapan dan belum merender prompt di platform gambar nyata, jadi akurasi teks Indonesia di gambar belum teruji.
