# Instruction-language A/B — English-guided vs Indonesian-guided (2026-10-31, loop 7)

The owner's original question (2026-10-31, the one that opened this
repo's arc): *does writing the skill in Indonesian help the LLM's
Indonesian?* First measured answer below. Design and validity controls:
[`../instrlang/README.md`](../instrlang/README.md).

## Arms

- **English-guided:** `id-copy` (SKILL.md with English rules + one-line
  Indonesian glosses; English components). Same base model.
- **Indonesian-guided:** [`../instrlang/id-copy-id/`](../instrlang/id-copy-id/)
  — a native-written twin carrying the SAME rules, sources, examples,
  and weights; instruction language is the only variable. Built and
  native-lens-critic-passed BEFORE the A/B (rule parity and register
  neutrality verified clean; the plan's named risk — formal-baku
  instructions priming formal-baku output — was the thing to watch).
- **Protocol:** id-bench's. Fresh persona judges, blind VERSION 1/2,
  orders randomized per sample and recorded, forced PICK, process notes
  + tag blocks stripped before judging. n=3 — **directional, not
  statistics**. **No rerun.** Same co-evolution/authorship caveats as
  ab-test.md: one builder authored samples, both skill variants, and
  the judge personas.
- **Reuse disclosure:** the English-guided outputs are the SAME outputs
  produced for this loop's sample expansion (copy-3/4/5 Arm B, retained
  verbatim in [`loop7-arms.md`](loop7-arms.md)) — not re-run.

## Samples + orders (recorded)

| Sample | Judge persona | Order shown | Pick |
|---|---|---|---|
| copy-3 (WA flash-sale promo) | wa-buyer | V1=EN-guided, V2=ID-guided | **V2 — Indonesian-guided** |
| copy-4 (IG skincare caption) | shopee-ibu | V1=ID-guided, V2=EN-guided | **V1 — Indonesian-guided** |
| copy-5 (marketplace air-fryer listing) | shopee-ibu | V1=EN-guided, V2=ID-guided | **V2 — Indonesian-guided** |

## Result: Indonesian-guided 3/3 — and the priming risk did not show

The judges' own words localize the difference:

- copy-3, on the ID-guided version: *"Dibuka 'Halo Kak!' — langsung
  personal… 'nggak', 'nya', 'Yuk' — ini bahasa chat, bukan bahaya
  spanduk… Ini yang bikin aku bales, bukan skip."* (The EN-guided arm
  lost partly on hashtags leaking into the WA surface.)
- copy-5: *"'Garing' bukan 'renyah'… 'tombol Beli Sekarang' itu emang
  tombol yang ada di Shopee — gak nyasar."* — the ID-guided output used
  the marketplace's actual button name and the shopper's word.
- copy-4 was the closest: the EN-guided arm lost on a checkable-urgency
  line ("Jangan sampai kehabisan!" — the judge: *"urgency kosong… aku
  selalu cek dan ini nggak bisa dicek"*), while crediting the
  ID-guided arm's honesty line (*"bukan yang instan, tapi hasilnya
  nyata"* — *"jarang iklan ngaku gitu"*).

**Priming check (the plan's named risk):** no baku-drift observed. If
anything, the Indonesian-guided outputs ran MORE colloquial at the same
declared register (chat particles, "garing", "Yuk") — consistent with
the twin's instruction register being functionally matched (lugas,
not ceremonial), which the pre-A/B native-lens critic verified.

**Honest limits:** n=3, one skill (id-copy), one builder, one model
family; two of three judges are shopee-ibu; copy-3's EN-guided arm had
a surface-handling wobble (hashtags on WA) that colored its loss. This
is a directional YES to the owner's question, not a settled one.
Re-measuring = new samples, more skills (the twin exists only for
id-copy), per the no-rerun rule.

## All six verdict JSONs (verbatim, unedited)

### copy-3 (wa-buyer · V1=EN-guided, V2=ID-guided · PICK: V2)

V1: {"persona":"wa-buyer","understood":"yes — diskon up to 70%, gratis ongkir kalau belanja Rp150rb, stok terbatas","trusted":"half — tau infonya, tapi rasanya kayak flyer yang di-blast, bukan orang","would_act":"no — simpan dulu, kalau minat balik tanya dulu sebelum checkout","lost_me_at":"baris hashtag #FlashSale1212 — itu caption IG yang di-paste ke WA, bukan chat","cheese_flags":["hashtag di WhatsApp","'Diskon hingga 70% untuk semua item' — bahasa iklan, bukan bahasa orang","rasa broadcast massal","seru-seru di akhir 'buruan checkout ya, Kak! tapi baru nyapa di situ"],"in_my_words":"Toko Verra Closet lagi flash sale 12.12, semua item diskon sampai 70%, gratis ongkir min belanja 150rb.","verdict_note":"Infonya jelas dan singkat, tapi yang ngirim ini kayak admin yang nge-blast ke ratusan orang. Satu-satunya 'Kak' ada di ujung, sisanya poster. Kena folderPromo, bukan hati."}

V2: {"persona":"wa-buyer","understood":"yes — flash sale 12.12, semua item diskon sampai 70%, gratis ongkir mulai 150rb, stok tinggal dikit","trusted":"yes — gayanya kayak seller yang emang ngobrol, bukan mesin","would_act":"yes — balas dulu 'Kak, yang di highlight masih ada?' terus checkout kalau dibales cepet","lost_me_at":"nggak sampai ilang — paling 'SEMUA' kapital itu sedikit promo banget, tapi masih wajar di chat","cheese_flags":["'SEMUA' huruf kapital","'checkout sekarang sebelum kehabisan' agak dorong, tapi biasa di promo"],"in_my_words":"Kak Verra Closet lagi flash sale 12.12, semuanya diskon sampai 70%, belanja 150rb ke atas gratis ongkir, tapi stoknya udah tipis.","verdict_note":"Dibuka 'Halo Kak!' — langsung personal. 'nggak', 'nya', 'Yuk' — ini bahasa chat, bukan bahaya spanduk. Keliatan masih broadcast, tapi broadcast yang ditulis tangan manusia. Nggak ada hashtag ngalor-ngidul. Ini yang bikin aku bales, bukan skip."}

Hesitation (verbatim): "Version 1 padat dan infonya sama persis — kalau cuma soal cepat tangkap info, seri. Tapi yang menentukan aku eksekusi atau bukan itu rasa 'ada manusia di seberang', dan itu cuma Version 2 yang punya. Version 1 kalah bukan karena salah kata, tapi karena hashtag-nya nunjukin ini copy-paste massal — dan pesan massal adalah pesan yang paling gampang kucekal."

### copy-4 (shopee-ibu · V1=ID-guided, V2=EN-guided · PICK: V1)

V1: {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":"lemah — nggak ada harga, voucher, atau alasan buat buruan mampir","lost_me_at":"nggak sampai lost, tapi pas 'khusus untuk kamu yang ingin kulit sehat bercahaya' kerasa kayak kalimat template iklan sebentar","cheese_flags":["opener 'bentuk paling sederhana dari cinta diri' agak poster motivasi, masih kewajar","'bercahaya' plus sparkle di akhir — minor","nggak ada satu pun angka (harga, isi berapa ml, berapa kali pakai sehari)"],"in_my_words":"Serum vitamin C lokal, katanya kalau dipakai rutin bisa cerahin kulit kusam dan ratain warna. Yang aku suka: mereka jujur bilang hasilnya nggak instan. Yang bikin males: nggak tau harganya sama sekali, disuruh mampir doang.","verdict_note":"Kalimat 'bukan yang instan, tapi hasilnya nyata' itu yang bikin aku nggak tutup aplikasi — jarang iklan ngaku gitu. Sisanya biasa aja, nggak ada yang maksa. Kalau mau aku klik, kasih tau harga atau free ongkir."}

V2: {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":"mungkin — nama produk dan mereknya jelas jadi gampang kucari langsung di Shopee, tapi bukan karena UGD-nya","lost_me_at":"'Jangan sampai kehabisan!' — darimana tau kehabisan? Nggak ada info stok, nggak ada flash sale, cuma kata-kata","cheese_flags":["'Jangan sampai kehabisan!' — urgency kosong, aku selalu cek dan ini nggak bisa dicek","'glowing' masuk kategori wajar di skincare, cuma buzzword","paragraf 'Merawat diri nggak harus ribet' agak muter-muter ngomongin hal yang sama"],"in_my_words":"Serum Vitamin C merek Rupa, ngomongnya santai kayak seller yang baek, dan jujur juga sih — 'asal dipakai rutin'. Tapi di akhir kok maksa 'jangan kehabisan' padahal nggak ada buktinya. Iklan yang ngomongnya enak tapi ujungnya kayak sales.","verdict_note":"Suara paling mirip manusia dari keduanya, dan sebut nama produk jelas — itu nilai plus buat aku yang mau cari di marketplace. Tapi kalimat penutupnya ngerusak. Kalau baris terakhir dibuang, ini jelas menang."}

Hesitation (verbatim): "Versi 2 lebih enak dibaca dan kayak orang beneran ngajak ngobrol, dan dia satu-satunya yang nyebut nama produk (gampang kucari di Shopee). Tapi sebagai pembaca yang tiap hari lihat trik 'buruan kehabisan' di flash sale — kalimat itu bikin aku nggak percaya sedikit, sedangkan Versi 1 justru bilang jujur 'bukan yang instan'. Jujur di awal menang daripada ramah tapi maksa di akhir. Kalau Versi 1 ditambahin harga atau free ongkir, nggak ada pertandingan."

### copy-5 (shopee-ibu · V1=EN-guided, V2=ID-guided · PICK: V2)

V1: {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Pembukaannya 'Suka gorengan tapi ingin yang lebih sehat?' — nada iklan yang sama di tiap listing, langsung kerasa jadi template","'kami bantu dengan senang hati' agak kaku, kayak teks CS","Emoji keranjang di akhir agak jualan banget","'Checkout sekarang' — orang Shopee bilang 'Beli Sekarang', 'checkout' agak asing di mulut seller"],"in_my_words":"Air fryer 4 liter buat sekeluarga, masak pakai udara panas jadi renyah tanpa banyak minyak. Kompak, gampang dibersihkan, hemat listrik. Garansi 1 tahun, harga 389 ribu. Bisa chat dulu kalau mau tanya.","verdict_note":"Jelas semua: harga, garansi, kapasitas — bullet-nya yang aku baca dua kali. Judulnya bagus, langsung ada benefitnya. Tapi rasanya kayak iklan yang rapi banget, agak kurang 'manusia seller'-nya. Tetap akan aku beli kalau bintangnya bagus."}

V2: {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["'Cocok untuk kamu yang tiap hari memasak untuk keluarga' — sedikit-raysa pujian, tapi masih wajar dan emang kena ke aku","Judul polos banget, kalau muncul di daftar pencarian tidak nongol bedanya dari toko sebelah"],"in_my_words":"Air fryer 4 liter, masak pakai udara panas, hasilnya garing dan matang merata, minyaknya dikit. Buat yang tiap hari masak buat keluarga — ya aku ini. Kompak, gampang dibersihkan, hemat listrik. Garansi resmi 1 tahun, 389 ribu. Tinggal pencet Beli Sekarang, atau chat kalau mau tanya.","verdict_note":"Ini kayak seller sungguhan yang biasa balas chat. 'Garing' bukan 'renyah', 'jadi hasilnya' kayak orang ngomong, dan 'tombol Beli Sekarang' itu emang tombol yang ada di Shopee — gak nyasar. 'Garansi resmi' juga nambah percaya. Kalau ada bintang dan ongkirnya oke, aku langsung pesan."}

Hesitation (verbatim): "kedua versi hampir sama isinya — harga, garansi, bullet yang persis sama, tidak ada yang bocor harga atau maksa urgency, jadi dua-duanya lolos. Yang bikin miring: Versi 2 bunyinya kayak penjual asli di Shopee (register 'kamu', 'garing', 'tombol Beli Sekarang'), Versi 1 bunyinya kayak copy iklan yang rapi dengan pertanyaan pembuka klise. Satu-satunya hal yang bikin aku ragu: judul Versi 1 ('Renyah Tanpa Banyak Minyak') lebih menjual di halaman pencarian daripada judul polos Versi 2 — tapi kalau harus jadi satu listing utuh yang kubaca sebagai pembeli, badan copy Versi 2 yang bikin aku percaya dan gerak."

## The Indonesian-guided arm outputs, verbatim (retention)

copy-3 (ID-guided, full output incl. tag block; process preamble: register 3 chat-santai chosen per the twin's register.md rule 1):

Halo Kak! 🛍️
Flash sale 12.12 di Verra Closet, SEMUA item diskon sampai 70%.
Belanja Rp150rb ke atas juga gratis ongkir, Kak.
Stoknya nggak banyak, jangan sampai nyesel ya.
Yuk, checkout sekarang sebelum kehabisan! 🔥

```
register: chat-santai (tingkat 3) · media: broadcast WhatsApp · checked: id-copy-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

copy-4 (ID-guided; preamble: register dipilih dulu, draf dicek terhadap ke-16 entri tells.md — pembuka era, "penawaran menarik" tanpa isi, Anda di copy sosial, pasif "diformulasikan", emoji berlebih — dan barisnya diperbaiki, bukan dihapus diam-diam):

Merawat kulit itu bentuk paling sederhana dari cinta diri.

Kami meracik serum vitamin C ini khusus untuk kamu yang ingin kulit sehat bercahaya. Pakai rutin, vitamin C membantu mencerahkan kulit kusam dan meratakan warna kulit. Bukan yang instan, tapi hasilnya nyata.

Yuk, mampir ke toko kami! Link-nya ada di bio ✨

#RupaSkincare #SelfLove #GlowingSkin #SkincareLokal

```
register: semi-formal santai (tingkat 2) · media: caption IG · checked: id-copy-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

copy-5 (ID-guided):

Air Fryer Kompak 4 Liter

Gorengan favorit keluarga, tanpa perlu banyak minyak. Air fryer ini memasak dengan sirkulasi udara panas, jadi hasilnya garing dan matang merata. Cocok untuk kamu yang tiap hari memasak untuk keluarga.

Spesifikasi:
- Kapasitas 4 liter, cukup untuk porsi sekeluarga
- Desain kompak dan modern, hemat tempat di dapur
- Mudah dibersihkan
- Hemat listrik

Garansi resmi 1 tahun. Harga Rp389.000.

Pesan langsung lewat tombol Beli Sekarang. Masih ada yang ingin ditanyakan? Chat kami saja. 😊

```
register: tingkat 2 — semi-formal santai · media: deskripsi produk marketplace · checked: id-copy-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

The English-guided arms of this experiment are the copy-3/4/5 Arm B
texts retained verbatim in [`loop7-arms.md`](loop7-arms.md) (per the
reuse disclosure above).

## What happens with this finding

Directional yes → logged as the answer to the plan's wave-2 question.
Migration of shipped components to Indonesian-guided is a **v2
decision** (the twin stays an experiment artifact under
`eval/instrlang/`); the cheapest next trust step is more samples and a
second skill twinned (id-social or id-humanizer), not a rewrite on
n=3.
