# Katalog palet dan aturan warna baku

Daftar isi: Peran warna | Katalog (3 kelompok, 9 palet) | Aturan warna baku | Palet buatan pengguna | Blok COLOR PALETTE untuk prompt

## Peran warna

| Peran | Fungsi |
|---|---|
| Latar | Background halaman |
| Struktur | Header, badan, banner, kartu hero. Selalu warna gelap |
| Aksen | Judul seksi, badge, ikon, callout kunci |
| Highlight | HANYA angka kritis dan badge hero |
| Sekunder | Garis pembagi, border kartu, elemen netral |

## Katalog

Semua palet memuat warna gelap untuk Struktur.

### Kelompok Formal-korporat
1. **McKinsey (baku)**: Latar #F7F4EF | Struktur #0B1F3A | Aksen #5A0F1E | Highlight #C9A227 | Sekunder #D9DCE1
2. **Refined Professionalism**: Latar #F7F9F9 | Struktur #2C3E50 | Aksen #16A085 | Highlight #F39C12 | Sekunder #34495E (dipakai sebagai tint 20-30% untuk garis dan border)
3. **Timeless Elegance**: Latar #F0E5D8 | Struktur #2E4052 | Aksen #C84B31 | Highlight #D9BF77 | Sekunder #A5C9CA
4. **Cool Blues**: Latar #F0F4F8 | Struktur #1B2631 | Aksen #3F4E4F | Highlight #A5C8D6 | Sekunder #D9E4E0

### Kelompok Hangat-natural
5. **Warm Earth Tones**: Latar #E8DAB2 | Struktur #6B4226 | Aksen #A45A3D | Highlight #D9BF77 | Sekunder #C4B6A6
6. **Serene Nature**: Latar #F1F1F1 | Struktur #1D3557 | Aksen #ED553B | Highlight #F6D55C | Sekunder #A8D8B9
7. **Urban Chic**: Latar #F2E9E4 | Struktur #22223B | Aksen #4A4E69 | Highlight #C9ADA7 (dipakai di atas kartu gelap) | Sekunder #9A8C98

### Kelompok Netral-minimalis
8. **Elegant Minimalism**: Latar #FFFFFF | Struktur #333333 | Aksen #707070 | Highlight #333333 (ditandai lewat ukuran dan ketebalan huruf, bukan warna) | Sekunder #B0B0B0 (isi kartu #F0F0F0)
9. **Serene Workspace**: Latar #EAEDED | Struktur #5D6D7E | Aksen #85929E | Highlight #5D6D7E (ditandai lewat ukuran dan ketebalan huruf, bukan warna) | Sekunder #D5DBDB (garis #AAB7B8)

Catatan peta khusus:
- Palet 8 dan 9: Highlight sama dengan Struktur. Sampaikan ke model gambar bahwa penekanan angka kritis dilakukan lewat ukuran dan ketebalan huruf. Hex tambahan (#F0F0F0, #AAB7B8) yang tertulis di katalog adalah bagian resmi palet itu dan boleh ditulis.
- Palet 2: #34495E dipakai sebagai tint untuk garis dan border, bukan sebagai blok warna penuh.
- Palet 7: Highlight #C9ADA7 hanya terbaca di atas kartu gelap (Struktur).

## Aturan warna baku (berlaku untuk SEMUA palet; tidak boleh dilonggarkan)

Aturan ini diwarisi dari skill McKinsey. Alasannya: model gambar cenderung menambah warna sendiri dan memakai hijau/merah/kuning untuk status bila tidak dilarang tegas.

- Tulis hex persis seperti katalog di setiap prompt. Dilarang memakai varian hex (mis. #F5F2EE untuk #F7F4EF).
- Hanya 5 warna palet terpilih. Teks terang di atas Struktur/Aksen memakai putih. Variasi nilai hanya lewat opasitas/tint dari warna yang sama (mis. latar ilustrasi 8-10% opacity); tidak ada hex baru.
- Highlight hanya untuk angka kritis dan badge hero. Dilarang untuk lingkaran langkah, ikon, atau dekorasi. Lingkaran langkah/nomor memakai Struktur atau Aksen.
- Penandaan pihak/kategori konsisten di seluruh gambar: pihak A = Struktur, pihak B = Aksen.
- Status: boleh/setuju/selesai = Struktur + ikon centang; dilarang/ditolak/bermasalah = Aksen + ikon silang atau segitiga peringatan. Tidak ada warna lampu lalu lintas (hijau/merah/kuning) untuk menandai status. Warna hijau, merah-oranye, atau kuning yang kebetulan ada di palet (mis. Refined Professionalism, Serene Nature) hanya dipakai menurut perannya, tidak pernah sebagai penanda baik/waspada/buruk. Gaya "lampu lalu lintas" cukup lewat susunan kolom dan ikon.
- Blok COLOR PALETTE disalin utuh ke setiap prompt. Tidak ada neon dan tidak ada gradien murahan.

Contoh pemakaian peran pada palet yang punya warna "berisiko":
- Serene Nature: Sekunder #A8D8B9 (hijau muda) hanya untuk garis/border/netral, bukan tanda "setuju". Highlight #F6D55C (kuning) hanya untuk angka kritis/badge hero, bukan tanda "waspada". Aksen #ED553B dipakai untuk pihak B, judul seksi, dan item ditolak lewat ikon silang, bukan sebagai "lampu merah".
- Refined Professionalism: Aksen #16A085 (hijau tosca) adalah warna judul seksi dan badge; centang "setuju" tetap berwarna Struktur #2C3E50.

## Palet buatan pengguna

1. Petakan tiap hex ke lima peran. Latar = paling terang; Struktur = paling gelap; Highlight = yang paling mencolok dan hanya untuk angka kritis; Aksen = warna merek/judul; Sekunder = netral.
2. Wajib ada minimal satu warna gelap untuk Struktur. Bila semua hex pengguna terang/sedang, sarankan satu warna gelap yang selaras (turunan gelap dari hue Aksen), nyatakan bahwa itu usulan, dan minta persetujuan sebelum dipakai.
3. Bila total lebih dari 5, minta pengguna memilih mana yang dibuang atau digabung. Jangan membuang diam-diam.
4. Tampilkan pemetaan sebagai tabel kecil agar pengguna bisa mengoreksi. Setelah disetujui, perlakukan seperti palet katalog (hex eksak, aturan baku penuh).

## Blok COLOR PALETTE (disalin utuh ke setiap prompt)

```
COLOR PALETTE (use exactly these hex values, no other colors, no variants):
- Background: {Latar}
- Structure (header, body panels, banners, hero card; dark): {Struktur}
- Accent (section titles, badges, icons, key callouts): {Aksen}
- Highlight (ONLY for critical numbers and the hero badge): {Highlight}
- Secondary (dividers, card borders, neutral elements): {Sekunder}
White for text on dark colors. Variation only through opacity/tint of these same colors. Step numbers/circles use Structure or Accent, never Highlight. Party A = Structure, Party B = Accent. Status: approved/allowed/done = Structure color + check icon; rejected/forbidden/problem = Accent color + cross or warning-triangle icon. No neon, no cheap gradients, no traffic-light green/red/yellow status colors.
```

Untuk palet 8 dan 9, tambahkan baris: "Highlight equals Structure; emphasize critical numbers through larger size and heavier weight, not color."
