# Template baku prompt (Langkah 10)

Daftar isi: Aturan penulisan | Template lengkap | Varian Midjourney | Varian tanpa teks | Contoh format jawaban

## Aturan penulisan
- Instruksi dalam bahasa Inggris; teks di dalam gambar dalam bahasa Indonesia (atau pilihan pengguna), verbatim dalam tanda kutip.
- Sertakan kalimat: `Do not add any text that is not listed.`
- Batas teks: judul <= 12 kata; action title <= 20 kata; blok <= 12 kata; bullet <= 8 kata; modul maks 5 per gambar (kecuali pengguna meminta lain).
- Jangan menaruh panah, centang, atau simbol matematika di teks gambar. Tulis kata ("naik", "selesai") atau minta digambar sebagai ikon.
- Angka, nama, tanggal, nominal: persis seperti sumber (format Rp dan titik ribuan dipertahankan).
- Satu code block per gambar, judul "Gambar 1 dari N: ..." di luar code block.
- Tidak boleh ada instruksi yang saling bertentangan (mis. "minimalis" sekaligus "padat sekali"; "flat vector" sekaligus "photorealistic").
- Blok COLOR PALETTE disalin utuh dari `palettes.md`.

## Template lengkap

```
Create a {ratio words} {style words} infographic at {quality}, titled "{judul}". {One sentence describing layout type and overall mood.}

COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: {hex}
- Structure (header, body panels, banners, hero card; dark): {hex}
- Accent (section titles, badges, icons, key callouts): {hex}
- Highlight (ONLY for critical numbers and the hero badge): {hex}
- Secondary (dividers, card borders, neutral elements): {hex}
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers use Structure or Accent. Party A = Structure, Party B = Accent. Status: approved/done = Structure + check icon; rejected/problem = Accent + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.

TYPOGRAPHY: {serif for titles + clean sans-serif for body, or user-specified}; title bold, body regular; consistent sizes; high contrast.

HEADER (top {n}%): small label "{label}"; title "{judul}"; subtitle "{subjudul}"; action headline "{kalimat kesimpulan <= 20 kata}".

HERO ELEMENT ({n}%): "{hero metric persis}" in Highlight color on a Structure card, with caption "{label}".

LAYOUT (zones): 
Zone 1 header {n}% | Zone 2 hero {n}% | Zone 3 modules {n}% | Zone 4 bottom banner {n}% | Zone 5 footer {n}%.

MODULES ({k} total):
1. "{judul modul}" - icon: {ikon bertema}. Text: "{bullet 1}", "{bullet 2}".
2. ...

BOTTOM BANNER: Structure color band with white text: "{ringkasan/langkah berikutnya}".

FOOTER: "{sumber, tanggal}" and page marker "{1/3}" in Secondary tint.

ILLUSTRATION STYLE: {monoline / flat vector}; allowed objects only: {daftar}; not allowed: {objek tidak relevan}; colors only tints of Structure, Accent, Secondary.

STYLE RULES: clean grid, generous alignment, consistent icon stroke, text fully legible, no overlapping text, rounded-corner cards with thin Secondary borders. Do not add any text that is not listed.

NEGATIVE: any color outside the specified palette, neon colors, gradients, traffic-light status colors, photorealistic people, logos, watermarks, misspelled or extra text, decorative icons unrelated to the content, clutter.
```

Catatan: bagian yang tidak dipakai (mis. HERO ELEMENT bila tidak ada angka dominan) dihapus; jangan dibiarkan kosong. Bila tidak ada hero metric, jadikan satu pesan kunci sebagai hero berbentuk kalimat, tanpa Highlight.

## Varian Midjourney
Ringkas menjadi satu paragraf deskriptif + parameter. Contoh bentuk:

```
Landscape executive infographic, clean consultant grid, header band at top, one large hero number card, four evenly spaced icon modules, bottom banner, monoline icons of {objek}, palette strictly #..., #..., #..., #..., #... (dark structure, light background, no other colors), serif titles with sans-serif body, flat, no gradients, no neon --ar 16:9
```
Cek sintaks parameter versi terbaru bila ragu. Karena Midjourney lemah soal teks padat, prioritaskan mode tanpa teks (lihat bawah). Judul/hero singkat boleh ditulis dalam tanda kutip dengan peringatan ejaan tidak terjamin.

## Varian tanpa teks
Ganti setiap teks dengan "empty text placeholder area" dan sebut ukuran relatifnya:
- `HEADER: empty text placeholder area for a one-line title (about 60% width) and a smaller subtitle line.`
- `HERO ELEMENT: large empty text placeholder box for a big number.`
Tambahkan ke NEGATIVE: `any readable text, letters, numbers, watermarks, logos`.
Lampirkan tabel "teks untuk ditambahkan manual" (zona | teks) di catatan setelah code block.

## Contoh format jawaban akhir

> Memakai gaya elegan konsultan dengan palet McKinsey, layout executive summary grid, dan ikon monoline bertema {tema}.
>
> **Gambar 1 dari 1: {judul}**
> (code block prompt)
>
> Catatan:
> - {asumsi}
> - {bagian yang dipangkas}
> - {ambiguitas sumber}
> - {saran bila teks gambar rusak}
>
> Mau versi lebih ringkas, dipecah jadi 2-3 gambar, atau ganti palet/gaya?
