# loop 7 — retained arms + verdict JSONs (2026-10-31)

Companion to the loop-7 sample expansion (per-skill n=2 → 5): all 30
expansion arm outputs verbatim (15 samples × no-skill/skill) + all 30
verdict JSONs (15 fresh judges × 2 versions). The instruction-language
experiment's arms/JSONs live in
[`instrlang-ab.md`](instrlang-ab.md) (its English-guided outputs are
the copy-3/4/5 Arm B texts below, reused per the disclosed design).
Arm construction, blinding, order randomization, and no-rerun per
id-bench's protocol; same co-evolution/authorship caveats as
ab-test.md. Two judges expressed verdict dimensions as prose
strings rather than strict booleans (humanize-4 and longform-3,
noted at their verdict blocks below); their PICKs are unambiguous.
A third (social-5) wrote its closing hesitation in Chinese — retained
verbatim at its block.

## Copy sample copy-3 (WA flash-sale promo · judge wa-buyer · V1=ArmA V2=ArmB · PICK: V2 = skill)

### Arm A (no skill)

PERHATIAN BUAT KAKAK-KAKAK SEMUA! 🔥🔥🔥
Verra Closet ngadain Flash Sale 12.12 paling hebat tahun ini!
Semua item diskon hingga 70% — iya, SEMUA! Sayang banget kalau sampai nyesel, kak.
Ada bonusnya lagi: gratis ongkir minimal belanja Rp150rb. Mantap, kan?
Tapi ingat, stoknya terbatas — buruan checkout sebelum kehabisan!
Kesempatan kayak gini gak datang dua kali. Siapa cepat, dia dapat! 🛍️💖🔥

### Arm B (id-copy) — full output incl. process notes (stripped for judging: only the copy + hashtags were shown)

Flow notes: "All flow steps are complete: INTAKE (surface asked and answered — IG caption), REGISTER chosen, DRAFT written against codeswitch/platforms norms, TELLS checked line-by-line (ceremonial 'KAK-KAK SEKALIAN' → single Kak address; unnamed superlative 'paling hebat tahun ini' and false-scarcity 'tidak akan terulang lagi'/'siapa cepat dia dapat' cut in favor of the named offer and the real, stock-based urgency; emoji cut to budget)."

**Register: 3 — chat-santai** (sapaan Kak, gramatika kamu, partikel *ya*; emoji hemat) — seller-run shop, promo broadcast, bukan konten youth-meme level 4, bukan korporat level 1-2.

Flash Sale 12.12 di Verra Closet! 🔥 Diskon hingga 70% untuk semua item.

Gratis ongkir juga, minimal belanja Rp150rb.

Stoknya terbatas. Biar gak nyesel, buruan checkout ya, Kak! 🛍️

#FlashSale1212 #VerraCloset #Diskon70 #GratisOngkir

```
register: chat-santai (3) · surface: IG caption · checked: id-copy@v1
⚠️ hand to a native Indonesian reader before publishing.
```

Runner note (recorded, not shown to judge): the dispatch prompt did
not pin the surface; this arm inferred "IG caption" (sample's intended
surface was WA broadcast) — against its own INTAKE rule of
ask-never-guess. Kept as run per no-rerun; the judge's hashtag flag is
the visible consequence.

### Verdicts

V1: {"persona":"wa-buyer","understood":true,"trusted":false,"would_act":false,"lost_me_at":"Baris pertama. 'PERHATIAN BUAT KAKAK-KAKAK SEMUA! 🔥🔥🔥' — caps semua plus api tiga, itu persis broadcast yang biasa langsung kuhapus sebelum baca.","cheese_flags":["Caps opener + 6 emoji total — register broadcast scam","'paling hebat tahun ini'","'iya, SEMUA!' — nge-tegasin sendiri","'Mantap, kan?' — ngajak setuju kayak infomercial","'Kesempatan kayak gini gak datang dua kali. Siapa cepat, dia dapat!' — dua kalimat pamungkas penjual preloved yang pressure","'Sayang banget kalau sampai nyesel' dipakai sebagai ancaman, bukan obrolan"],"in_my_words":"Broadcast lagi. Isinya jelas sih — diskon 70% semua item, gratis ongkir min belanja 150rb, stok terbatas — tapi caranya ngirim kayak pengeras suara, bukan kayak orang yang bakal hati-hati sama pesananku. Enam baris, teriak-teriak, ditutup 'siapa cepat dia dapat'. Aku gak delete sih kalau seller-nya kukenal, tapi gak akan langsung checkout juga.","verdict_note":"Aku ngerti penawarannya dalam lima detik, itu poin buat dia. Dan tengah-tengahnya sebenernya ada rasa — 'ngadain', 'buruan checkout', panggil 'kak' — jadi bukan bahasa buku. Tapi pembungkusnya bunuh semua: caps, api numpuk, terus ditutup dua kalimat arisan-penjual ('gak datang dua kali', 'siapa cepat dia dapat') yang persis nada broadcast attempted-scam yang pernah kudapetin. Pesan sepanjang ini di WA terasa kayak pengumuman sekolah. Kalau aku gak kenal sellernya, ini langsung mute. Kalau kenal, paling aku baca doang dan tunggu dia ngirim pesan yang lebih personal."}

V2: {"persona":"wa-buyer","understood":true,"trusted":true,"would_act":true,"lost_me_at":"Baris hashtag di ujung. Sempat kara ini chat sungguhan dari seller, terus '#FlashSale1212 #VerraCloset...' — oh, caption IG yang ditempel ke WA. Sedikit begitu bot-nya kelihatan.","cheese_flags":["Blokhast hashtag di chat WA — jelas copy-paste caption, bukan tulisan tangan seller","'Diskon hingga 70% untuk semua item' — 'hingga' sama 'untuk' agak baku untuk chat; kalau orang WA nulis 'sampe' dan 'buat'","Enter dobel antar baris — rapi kelewat, kayak template"],"in_my_words":"Singkat, jelas, gak teriak: diskon 70% semua item, gratis ongkir kalau belanja 150rb ke atas, stok terbatas, buruan checkout 'ya Kak'. Ada 'ya Kak'-nya, itu nempel. Kalau aku memang lagi nyari baju, aku screenshot terus tanya seller-nya langsung: 'Kak, masih ada stok ya? Total ke kotaku berapa?' Kalau dia jawab cepet dan kasih total plus nama rekening yang jelas, aku bayar. Tapi hashtag di ujung bikin aku inget ini broadcast ke ratusan orang, bukan ke aku.","verdict_note":"Jujur, ini baru tiga baris tapi bentuknya kayak chat, bukan spanduk — itu udah ngelewatin filter pertamaku. Semua info yang kubutuhkan ada: angka diskonnya, syarat ongkirnya, stok terbatas, tanpa drama 'siapa cepat dia dapat'. 'Biar gak nyesel, buruan checkout ya, Kak' itu pas — pas banget nada orang yang tiap hari jualan di WA. Hesitasi aku dua: hashtag di ujung itu bikin pesan terasa caption yang salah alamat ke chat, dan kalimatnya sedikit terlalu rapi/baku dibanding seller yang kukenal. Tapi keduanya kubilang 'agak', bukan 'hapus'. Aku tetap akan konfirmasi dulu sebelum transfer — itu kebiasaan, bukan salah pesannya."}

## Copy sample copy-4 (IG skincare caption · judge shopee-ibu · V1=ArmA V2=ArmB · PICK: V2 = skill)

### Arm A (no skill)

Di zaman self-love kayak sekarang, merawat kulit bukan cuma kebutuhan — itu bentuk cinta diri! ✨💕 Rupa hadir buat kamu yang pengen punya kulit sehat dan bercahaya. Serum vitamin C kami diformulasikan khusus untuk memberikan hasil terbaik, bakal bikin kamu jatuh cinta! Yuk, mampir ke toko kami sekarang dan dapatkan penawaran menariknya. Jangan sampai kehabisan ya! 🧴✨

#RupaSkincare #SelfLove #GlowingSkin #SkincareLokal

### Arm B (id-copy) — flow note: "REGISTER: Semi-formal santai — level 2, kamu-led (IG caption, lokal skincare, promo, self-love angle → santai promo register, not baku-Anda, not gaul; 'Anda' in the source is the register-lock tell)"

Cinta diri bisa dimulai dari hal kecil. Misalnya, serum vitamin C. ✨

Kami racik Serum Vitamin C Rupa buat kamu yang pengen mulai merawat kulit. Vitamin C di dalamnya bantu jaga kulit tetap sehat dan glowing, asal dipakai rutin.

Merawat diri nggak harus ribet, kok. Mulai dari satu langkah kecil aja sudah cukup.

Yuk, mampir ke toko kami dan cek serumnya sendiri. Jangan sampai kehabisan!

#RupaSkincare #SelfLove #GlowingSkin #SkincareLokal

register: semi-formal santai (level 2, kamu) · surface: IG caption · checked: id-copy@v1
⚠️ hand to a native Indonesian reader before publishing.

### Verdicts

V1: {"persona":"shopee-ibu","understood":true,"trusted":false,"would_act":false,"lost_me_at":"diformulasikan khusus untuk memberikan hasil terbaik","cheese_flags":["emoji beruntun di awal dan akhir, kayak iklan spam","tanda seru numpuk tiga kalimat berturut-turut","'diformulasikan khusus untuk memberikan hasil terbaik' — kosong, semua iklan skincare bilang begitu","'bakal bikin kamu jatuh cinta' — janji berlebihan tanpa bukti","'penawaran menariknya' — penawaran apa? angkanya mana?","'jangan sampai kehabisan' tanpa alasan percaya, urgency asal tempel","satu blok padat, capek dibaca di HP"],"in_my_words":"Iklan serum vitamin C merek Rupa. Katanya zamannya self-love, katanya formulanya spesial, bakal bikin jatuh cinta, ada penawaran, buruan sebelum habis. Harganya berapa, isinya berapa ml, nggak disebut. Kayak iklan yang lewat di feed tiap hari, aku scroll saja.","verdict_note":"Dua baris pertama masih lazim tapi nggak nyangkut. Begitu masuk 'diformulasikan khusus', otakku bilang: ini iklan generik. Nggak ada satu angka pun — harga, isi, jumlah review. Nggak ada alasan buat percaya 'kehabisan'. Mungkin aku kasih bintang 3 kalau dipaksa, tapi nggak klik."}

V2: {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["'Jangan sampai kehabisan!' — tetap urgency asal tempel, walau cuma sekali dan ringan"],"in_my_words":"Serum vitamin C merek Rupa, buat yang baru mau mulai merawat kulit. Katanya bantu kulit sehat dan glowing, asal dipakai rutin. Disuruh mampir ke toko buat cek sendiri. Kelihatannya brand kecil-kecilan yang meracik sendiri, jadi kayak gitu.","verdict_note":"Baris pertama pendek, baris kedua langsung produk — pas buat baca sambil nungguin apa pun. 'Kami racik' dan 'asal dipakai rutin' itu yang bikin aku nggak curiga: kayak orang yang jujur soal hasilnya nggak instan. 'Cek serumnya sendiri' cocok sama kebiasaanku (aku emang selalu baca review dulu). Kurangnya sama: tetap nggak ada harga, isi berapa, gratis ongkir apa nggak — jadi aku klik buat lihat, bukan langsung checkout. 'Jangan sampai kehabisan' bikin alis naik dikit, tapi cuma dikit."}

## Copy sample copy-5 (marketplace air-fryer listing · judge shopee-ibu · V1=ArmA V2=ArmB · PICK: V2 = skill)

### Arm A (no skill)

Air Fryer Kompak 4L — Gorengan Renyah Tanpa Rasa Bersalah 🍟✨

Masih mikir dua kali tiap pengin makan gorengan? Sekarang nggak perlu lagi. Air Fryer Kompak memakai teknologi udara panas sehingga makanan tetap garing di luar, lembut di dalam, dengan minyak jauh lebih sedikit. Pisang goreng, kentang, ayam crispy — semua bisa lebih sehat untuk keluarga di rumah.

Alasan pas banget buat dibawa pulang:
- Kapasitas 4 liter, muat untuk satu keluarga
- Desain modern dan elegan di dapur
- Bersih-bersihnya praktis, nggak ribet
- Hemat pemakaian listrik

Harganya cuma Rp389rb dan sudah dilindungi garansi 1 tahun. Sayang kan kalau kehabisan? Pesan sekarang sebelum stoknya habis! 🛒🔥

### Arm B (id-copy) — flow note: "Register dipilih: Level 2 — Semi-formal santai, dengan 'kami' sebagai subjek (register.md aturan 4 + platforms.md: deskripsi produk marketplace tetap menggunakan 'kami' di level 1–2; 'Kak'/kamu ada di obrolan toko, bukan di sini; emoji minimal, struktur tiga bagian berupa apa/spesifikasi/kebijakan)."

**Air Fryer Kompak 4L — Renyah Tanpa Banyak Minyak**

Suka gorengan tapi ingin yang lebih sehat? Air fryer ini memasak dengan sirkulasi udara panas: hasilnya renyah di luar, matang merata di dalam, cukup dengan sedikit minyak.

**Keunggulan**
- Kapasitas 4 liter, pas untuk kebutuhan keluarga
- Desain kompak dan modern, hemat tempat di dapur
- Mudah dibersihkan
- Hemat listrik

**Garansi & Harga**
- Garansi 1 tahun
- Rp389.000

Checkout sekarang, pesanan langsung kami proses. Masih ada yang ingin ditanyakan? Chat kami saja, kami bantu dengan senang hati. 🛒

```
register: semi-formal santai (level 2, kami-led) · surface: marketplace product description · checked: id-copy@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Verdicts

V1: {"persona":"shopee-ibu","understood":true,"trusted":false,"would_act":false,"lost_me_at":"\"Sayang kan kalau kehabisan? Pesan sekarang sebelum stoknya habis!\" — plus emoji dan seru-seruan di penutup","cheese_flags":["\"Tanpa Rasa Bersalah\" di judul — drama ringan, gorengan kok dipolosin jadi dosa","Emoji di judul dan ditumpuk lagi di penutup — rasa 'penawaran menarik!!!'","Urgensi stok yang tidak masuk akal — air fryer kan gampang didapat, saya tahu stoknya banyak"],"in_my_words":"Air fryer 4 liter, goreng tetap renyah tapi minyaknya dikit, cocok buat masak keluarga. Rp389rb, garansi setahun. Awalnya asyik bacanya, tapi pas disuruh buruan beli kata stok habis, saya langsung diam. Kalau emang bagus, nggak perlu dipaksa-paksa.","verdict_note":"Dua baris awalnya enak, bahasanya kayak penjual ramah — saya masuk. Harga dan garansi juga kelihatan, itu bagus. Tapi penutupnya rusak semua: tekanan 'sayang kehabisan' plus emoji dobel itu persis trik toko yang tidak jujur. Saya tidak checkout dari copy begini; palingan saya cari review dulu, dan kalau ratingnya biasa saja saya tinggal."}

V2: {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":[],"in_my_words":"Air fryer 4 liter, masaknya pakai udara panas jadi minyaknya sedikit, matangnya rata. Garansi setahun, harganya Rp389.000 — angkanya jelas, bukan cuma '389rb'. Mudah dibersihkan juga. Bisa chat duluan kalau ada yang mau ditanya. Oke, ini masuk pertimbangan serius.","verdict_note":"Nggak ada yang dipaksain. Penjelasan udara panasnya masuk akal, garansi dan harga dipisah jadi bagian sendiri — itu yang saya baca dua kali. Rp389.000 ditulis penuh, kesannya lebih resmi. Ajakan chat di akhir itu memang begitulah penjual Shopee yang beneran ngerjain. Kurangnya: agak kering dan nggak ada soal ongkir atau alasan beli sekarang — tapi nggak ada yang bikin saya curiga, dan itu yang lebih penting."}

Hesitation (verbatim): "pembukaan Versi 1 lebih terasa hidup dan dekat — 'masih mikir dua kali tiap pengin makan gorengan?' itu benar-benar bahasa saya. Kalau baris terakhirnya dibuang atau diganti voucher/free ongkir yang beneran, duel ini jadi berat. Tapi sebagai pembaca, kepercayaan lebih menentukan daripada kehangatan: Versi 1 kehilangan saya di detik terakhir, Versi 2 tidak pernah kehilangan saya."

## Translate sample translate-3 (EN changelog + error docs · judge dev-docs · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-translate) — register mapping note: "Source register is professional product docs (release notes + error troubleshooting, imperative instructions, casual-professional 'you') → target: level 2 semi-formal santai per register.md/structures.md §D (docs default: consistent kamu). UI strings (Schedule, Settings → Appearance, Dashboard → API) kept English per structures.md #21 — app UI language unverified, flagged here as prescribed."

## Yang baru (v2.4)

Kini kamu bisa menjadwalkan pesan: tekan lama *chat* mana pun, lalu pilih **Schedule**. Laporan CSV hasil ekspor menyertakan stempel waktu secara bawaan. Mode gelap pindah ke **Settings → Appearance**.

## Galat 429 ("rate limited")

Kamu mengirim permintaan terlalu cepat. Tunggu 60 detik sebelum mencoba lagi. Kalau galatnya masih muncul, cek kunci API kamu di halaman **Dashboard → API**. Kunci lama di *workspace* yang sudah dirotasi muncul sebagai galat 429.

```
register: semi-formal santai (from professional product docs) · surface: app release notes + error troubleshooting docs · structures changed: "how-to" sequence restructured into colon + short imperatives; source em dash before the key-rotation explanation split into its own sentence; UI strings kept English (unverified app UI language) · ledger: 10/10 lines verified · checked: id-translate@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Arm A (no skill)

## Yang baru (v2.4)

Kini Anda dapat menjadwalkan pesan: tekan lama obrolan mana pun, lalu pilih **Jadwalkan**. Laporan CSV yang diekspor kini menyertakan stempel waktu secara bawaan. Mode gelap dipindahkan ke **Pengaturan → Tampilan**.

## Kesalahan 429 ("batas laju terlampaui")

Anda mengirim permintaan terlalu cepat. Tunggu 60 detik sebelum mencoba lagi. Jika kesalahan masih berlanjut, periksa kunci Anda di halaman **Dasbor → API** — kunci lama pada workspace yang kuncinya telah dirotasi akan muncul sebagai kesalahan 429.

### Verdicts

V1 (skill): {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Kunci lama di workspace yang sudah dirotasi — workspace-nya yang dirotasi? maksudnya kuncinya. Lolos sih, tapi sempat jeda 0.5 detik."],"in_my_words":"Tekan lama chat, pilih Schedule buat jadwalin pesan. Ekspor CSV sekarang ada timestamp-nya default. Dark mode pindah ke Settings → Appearance. Kalau kena 429: kecepatan saya yang salah, tunggu 60 detik, coba lagi. Masih 429 juga berarti kunci API lama di workspace yang kuncinya udah dirotasi — cek di Dashboard → API.","verdict_note":"Ini kayak dibaca teman satu tim. 'Kamu' konsisten, chat/workspace/API dibiarkan Inggris, dan — paling penting — label tombol dan path menu (Schedule, Settings → Appearance, Dashboard → API) persis kayak yang ada di layar. Saya nggak perlu nebak mau klik apa. Baris terakhir soal rotasi kunci agak longgar, tapi nggak sampai bikin saya buka halaman English. Nggak ada kalimat yang bikin saya mikir 'ini terjemahan'."}

V2 (no skill): {"persona":"dev-docs","understood":true,"trusted":false,"would_act":false,"lost_me_at":"Kini Anda dapat menjadwalkan pesan — 'Anda dapat' di paragraf pertama. Baru satu barit, udah kerasa surat dari bank.","cheese_flags":["'Anda' — register bank letter, bukan doc buat dev.","'obrolan' buat chat — chat itu istilah teknis, diterjemahin jadi kayak kamus.","Label UI diterjemahin: 'Jadwalkan', 'Pengaturan → Tampilan', 'Dasbor' — pas saya cari tombolnya di aplikasi, teksnya kan 'Schedule' dan 'Settings'. Instruksinya berubah, bukan cuma bahasanya.","'batas laju terlampaui' — calque 'rate limited'. Dev Indonesia bilang 'kena rate limit'.","'dipindahkan ke' — pasif, aktornya siapa.","Kalimat terakhir panjang pake em-dash, gaya makalah."],"in_my_words":"Intinya ngerti: schedule pesan via long-press, CSV ada timestamp, dark mode pindah menu, 429 = tunggu 60 detik / cek kunci API. Tapi pas mau praktik, saya harus translate-balik sendiri semua nama tombol ke bahasa aplikasi.","verdict_note":"Ini terjemahan. Trigger-nya nembak di 'Anda dapat', terus semua yang aneh berikutnya saya salahin ke terjemahan — dan memang beneran: obrolan, batas laju, Dasbor. Yang fatal buat saya: label UI ikut diterjemahin, jadi instruksi klik-nya rusak. Satu-satunya hal yang lebih bagus di versi ini: 'workspace yang kuncinya telah dirotasi' lebih presisi daripada versi santainya. Tapi nggak nyelametin. Saya balik ke halaman English."}

Hesitation (verbatim): "Version 2's final clause ('workspace yang kuncinya telah dirotasi') is genuinely more precise than Version 1's ('workspace yang sudah dirotasi' — you rotate keys, not workspaces). If Version 1's author fixed that one noun attachment, this pick would be unanimous in my head instead of 95/5."

## Translate sample translate-4 (EN merchant payout email · judge fb-user · V1=ArmB V2=ArmA · PICK: V2 = no skill — honest loss)

### Arm B (id-translate) — ledger note: 8 lines extracted before drafting (subject capability claim · Dec 1 · next-day→same-day · 15.00 WIB condition · transition-week hedge · post-transition clause · Help Center hours EN-kept per structures #21, app UI unverified)

Subjek: Pencairan dana Anda kini bisa masuk di hari yang sama

Halo [Nama merchant],

Mulai 1 Desember, pencairan otomatis tidak lagi menunggu H+1. Dananya bisa cair di hari yang sama, asalkan permintaan pencairan saldonya diajukan sebelum pukul 15.00 WIB.

Ada satu hal yang perlu diketahui: selama minggu transisi, pencairan pertama bisa memakan waktu hingga satu hari lebih lama. Setelah itu, pencairan di hari yang sama berlaku.

Ada pertanyaan? Tim *Help Center* di aplikasi siap membantu setiap hari sampai pukul 21.00 WIB.

Salam,
Tim BayarLagi

```
register: semi-formal santai level 2, Anda/kami (from casual-professional business email) · surface: email announcement (template) to merchants · structures changed: compounds split & "is staffed" made active; em-dash signoff → "Salam,"; times 15:00/21:00 → 15.00/21.00 (PUEBI); [Merchant name] → [Nama merchant]; *Help Center* kept EN — app UI language unverified (structures #21) · ledger: 8/8 lines verified · checked: id-translate@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Arm A (no skill)

Subjek: Pencairan dana Anda kini bisa diterima di hari yang sama

Halo [Nama merchant],

Mulai 1 Desember, pencairan dana otomatis berubah dari H+1 menjadi di hari yang sama, selama permintaan pencairan saldo diajukan sebelum pukul 15.00 WIB.

Ada satu hal yang perlu Anda ketahui: selama minggu transisi, pencairan pertama mungkin memakan waktu hingga satu hari lebih lama. Setelah itu, pencairan di hari yang sama berlaku.

Ada pertanyaan? Pusat Bantuan di aplikasi siap membantu setiap hari hingga pukul 21.00 WIB.

— Tim BayarLagi

### Verdicts

V1 (skill): {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":"Tim *Help Center* — berhenti sebentar di situ","cheese_flags":["'Help Center' bahasa Inggris di tengah email Indonesia — kayak tempelan dari luar","Bintang dua (*) nyasar di 'Tim *Help Center*' — kelihatan seperti salah format; email soal uang yang formatnya belepotan bikin saya sedikit waspada"],"in_my_words":"Mulai 1 Desember, kalau saya minta cair saldo sebelum jam 15.00, dananya masuk hari itu juga, tidak perlu menunggu besok. Tapi minggu pertama bisa lambat satu hari lebih. Kalau bingung, tanya tim bantuan di aplikasi, buka sampai jam 21.00.","verdict_note":"Isinya jelas dan kata 'cair' itu bahasa saya sehari-hari, penutup 'Salam,' juga manusia. Tapi bagian bantuan itu pakai istilah Inggris plus bintang aneh — sesaat saya mikir ini email template yang asal tempel. Saya tetap percaya karena isinya masuk akal dan tidak ada suruh klik link."}

V2 (no skill): {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Tanda tangan pakai garis panjang '— Tim BayarLagi' — agak dingin, saya biasa dapat 'Salam,' atau 'Terima kasih,'","Kalimat pertama panjang dan bunyinya kayak catatan perubahan resmi ('berubah dari H+1 menjadi di hari yang sama') — kaku sedikit tapi tidak mengganggu"],"in_my_words":"Pencairan berubah: dulu tunggu H+1, sekarang kalau diajukan sebelum jam 15.00 bisa masuk hari yang sama. Hanya minggu pertama bisa lambat satu hari lebih. Ada pertanyaan, Pusat Bantuan di aplikasi siap setiap hari sampai jam 21.00.","verdict_note":"Satu kalimat pertama langsung jelas apa yang berubah, dari jam berapa, dan semuanya bahasa Indonesia yang rapi — 'Pusat Bantuan' bukan 'Help Center'. Agak resmi tapi tidak menyebalkan, dan tidak ada kesan salah ketik. Email soal uang yang bersih seperti ini lebih saya percaya."}

Hesitation (verbatim): "Versi 1 terasa lebih manusia ('dananya bisa cair', 'Salam,'), dan kalau saja bagian bantuan ditulis 'Pusat Bantuan' tanpa bintang, mungkin saya pilih itu. Tapi untuk email soal uang, yang bersih, full Indonesia, dan tidak ada format aneh lebih menenangkan hati saya."

Runner note: the loss is the UI-path rule (structures.md #21) in its documented trade-off form — the arm followed the skill's stay-English-unverified rule; this reader's app (and preference) is Indonesian. Same class as loop 5's translate-2 loss, opposite sample direction; the rule already encodes "which differs per reader," so no new rule — recorded as the rule's known cost.

## Translate sample translate-5 (EN logistics blog intro · judge startup-linkedin · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-translate) — register mapping note: "Source is a casual-professional B2B article voice — direct address, contractions, dashes, punchy declaratives — on an article/blog surface for Indonesian e-commerce merchants. Per the structures.md D table (professional docs/article → level 2) and register.md decision rules (ordinary-commerce trust stakes, written content surface): target = ladder level 2, semi-formal santai, consistent kamu. A decision, not a default."

## Margin yang tidak terlihat di faktur

Satu dari delapan paket *COD* di *e-commerce* Indonesia berakhir tanpa pembeli di depan pintu. Angka itu berasal dari audit internal jaringan kami tahun 2025. Rasio kamu bisa saja berbeda, jadi ukur dulu angkamu sendiri sebelum bertindak berdasarkan angka kami.

Yang tidak berbeda adalah bentuk biayanya: setiap retur menelan dua kali ongkos kirim ditambah biaya kemas ulang, dan keduanya tidak muncul sebagai pos biaya yang bisa kamu tunjuk di faktur.

Solusinya tidak dimulai dari mengejar paket setelah ditolak. Solusinya dimulai dari menebak pesanan mana yang akan ditolak, sedini dan semurah mungkin.

```
register: level 2 semi-formal santai, konsisten kamu (from EN casual-professional B2B article voice) · surface: artikel/blog intro, heading markdown + badan teks · structures changed: semicolon sumber dan kedua sisipan em dash spasi dibubarkan (klausa jadi kalimat/urutan belakang), kalimat majemuk biaya dipecah di titik dua, elipsis akhir "which orders will" dilengkapi jadi "pesanan mana yang akan ditolak", "guessing" tetap "menebak" agar bobot klaim tidak naik · ledger: 10/10 lines verified · checked: id-translate@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Arm A (no skill)

## Margin yang tak terlihat di faktur

Satu dari delapan paket COD di e-commerce Indonesia tidak pernah menemukan pembeli di depan pintu. Angka itu berasal dari audit internal jaringan kami tahun 2025 — rasio Anda mungkin berbeda; ukur dulu sebelum bertindak berdasarkan angka kami. Yang tidak berbeda adalah bentuk biayanya: setiap pengembalian membakar dua kali perjalanan pengiriman plus pengemasan ulang, dan tidak satu pun muncul sebagai pos biaya yang bisa Anda tunjuk. Perbaikannya tidak dimulai dengan mengejar paket setelah paket itu kembali. Perbaikannya dimulai dengan menebak — sedini mungkin, dengan cara termurah — pesanan mana yang akan bernasib sama.

### Verdicts

V1 (skill): {"persona":"startup-linkedin","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Italics di *COD* / *e-commerce* sedikit aneh secara format, kayak takut dianggap kata asing","'Solusinya tidak dimulai dari X. Solusinya dimulai dari Y.' — sedikit copywriting-pattern, tapi masih lolos"],"in_my_words":"1 dari 8 paket COD nggak ketemu pembelinya. Tiap retur makan 2x onkir plus re-pack, dan biaya ini nggak keliatan sebagai pos apa pun di faktur. Angka mereka dari audit internal 2025 — bukan angka lo, jadi ukur dulu rasio sendiri. Fix-nya bukan ngejar paket yang udah ditolak, tapi prediksi order mana yang bakal ditolak, dari awal dan murah.","verdict_note":"Ini kayak orang yang beneran ngelaporin angka dia sendiri. 'Rasio kamu bisa saja berbeda, ukur dulu' — auto-respect, jarang ada yang ngakuin limit kayak gini. Kamu-register, paragraf pendek, enak di-scroll. 'Menelan dua kali ongkos kirim' pakai bahasa orang, bukan bahaya marketing. Mungkin aku langsung cek RTO rate toko sendiri abis baca ini."}

V2 (no skill): {"persona":"startup-linkedin","understood":true,"trusted":false,"would_act":false,"lost_me_at":"rasio Anda mungkin berbeda","cheese_flags":["'Anda' — langsung kerasa press release, bukan orang ngomong","Em-dash berat: '— rasio Anda mungkin berbeda; ukur dulu —' plus sisipan '— sedini mungkin, dengan cara termurah —' di tengah kalimat, itu cadence terjemahan banget","'membakar dua kali perjalanan pengiriman' — calque dari 'burns', dramatis; 'ongkos kirim' jauh lebih manusia","'pesanan mana yang akan bernasib sama' — writerly, gaya penulis-fiksi di post operasional","Wall of text satu paragraf — di scroll cepat ini ded, mataku nyari hook line dan nggak nemu"],"in_my_words":"Sama sih isinya — 1 dari 8 COD gagal, retur itu biaya tersembunyi, prediksi dulu daripada ngejar. Tapi bunyinya kayak agency yang nulis bukan exec yang ngalamin.","verdict_note":"Informasinya sama persis, tapi suaranya beda. 'Anda' + em-dash rhythm + 'membakar' + 'bernasib sama' = teks yang ditulis untuk keliatan pintar, dan teks kayak gini yang kena screenshot di grup bareng caption 'siapa yang nulis gini'. Disclaimer jujurnya masih ada (good), tapi delivery-nya bunuh rasa personalnya."}

Hesitation (verbatim): "minim — isi kedua versi identik jadi ini murni soal register dan ritme. V1 menang di tiga hal yang persis di profil pembaca: 'kamu' bukan 'Anda', nol em-dash cadence, dan paragraf pendek yang scannable. Satu-satunya yang bikin aku mikir dua kali: pola 'Solusinya tidak dimulai… Solusinya dimulai…' itu agak ditulis-di-kepalakan-dulu, dan itu muncul di KEDUA versi — jadi tidak memengaruhi pemilihan."

## Humanizer sample humanize-3 (stiff CS broadcast · judge wa-buyer · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-humanizer) — detected register: "formal surat-dinas (level 1) on a chat-commerce surface — mismatch itself is tell #3 · genre: customer-service maintenance notice (broadcast) · changed: 8 lines" (changes summarized; every input/output line is retained verbatim around this note: surat-dinas opener → "Halo Kak,"; scaffolding/passive cuts; "Kami pastikan" at chat speed; "Mohon dimaklumi ya, Kak"; closing formulas cut/compressed per voice.md)

Halo Kak,

Sabtu pukul 02.00–04.00 WIB akan ada pemadaman server terjadwal. Selama itu, fitur pelacakan paket tidak bisa dipakai. Pengiriman tetap jalan normal. Kami pastikan tidak ada data pelanggan yang hilang.

Mohon dimaklumi ya, Kak, atas ketidaknyamanannya.

Terima kasih.

```
register detected: formal surat-dinis (level 1) on a chat-commerce surface — mismatch itself is tell #3 · genre: customer-service maintenance notice (broadcast) · changed: 8 lines ·
checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Arm A (no skill)

Halo Kakak,

Mau kami informasikan bahwa server kami akan dimatikan sementara untuk pemeliharaan terjadwal pada hari Sabtu, pukul 02.00–04.00 WIB. Selama pemeliharaan berlangsung, fitur pelacakan paket tidak bisa digunakan untuk sementara. Tapi tenang saja, pengiriman tetap berjalan seperti biasa, dan data Kakak aman, tidak ada yang hilang.

Mohon dimaklumi ya atas gangguannya. Terima kasih banyak atas pengertian dan kerja sama Kakak.

### Verdicts

V1 (skill): {"persona":"wa-buyer","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Kami pastikan tidak ada data pelanggan yang hilang — 'pelanggan' bikin aku kayak salah satu seribu, bukan 'data Kakak'. Tapi cuma satu baris, kulewati."],"in_my_words":"Sabtu subuh jam 2–4 tracking mati, paket tetap jalan, data aman. Santai, jangan panik nanti malam.","verdict_note":"Pendek, kepointnya jelas, 'Halo Kak' dan 'ya, Kak' bener pasarnya. Rasanya kayak notifikasi kurir yang beneran — agak baku tapi tidak bikin curiga. Aku screenshot jadwalnya biar gak tanya-tanya CS Sabtu malam."}

V2 (no skill): {"persona":"wa-buyer","understood":true,"trusted":true,"would_act":false,"lost_me_at":"Mau kami informasikan bahwa server kami akan dimatikan sementara... — kalimat pertama panjang banget sebelum jamnya muncul, mata langsung skim.","cheese_flags":["Mau kami informasikan bahwa — pembuka pengumuman kantor, bukan chat.","Tapi tenang saja — ngerayu dikit, gak apa-apa tapi kerasa.","Terima kasih banyak atas pengertian dan kerja sama Kakak — persis pengumuman pengurus komple / tagihan PLN. Chatnya aku tutup di situ."],"in_my_words":"Kayak pengumuman komple: server mati Sabtu jam 2–4 pagi, lacak paket nggak bisa sementara, tapi kiriman tetap jalan dan data aman.","verdict_note":"Isinya lengkap dan 'data Kakak aman' itu personal, aku suka itu bagian. Tapi keseluruhannya kuliah kecil: satu paragraf panjang ditutup salam resmi. Gak baca ulang, gak screenshot. Nanti kalau tracking error baru inget 'oh iya tadi ada pengumuman'."}

Hesitation (verbatim): "Version 2's 'data Kakak aman' is the single most personal line in either version — if Version 1 said that instead of 'data pelanggan', it would be perfect and this wouldn't be close. And neither is scammy; both name a specific time, which keeps my guard down. But on the phone, short and scannable wins: Version 1 I finish and act on; Version 2 I survive."

## Humanizer sample humanize-4 (AI LinkedIn post · judge startup-linkedin · V1=ArmA V2=ArmB · PICK: V2 = skill)

### Arm A (no skill)

Enam bulan pertama bekerja remote dari kota kecil mengajarkan saya banyak hal yang tidak pernah saya bayangkan. Saat saya mulai menelaah ulang cara kerja saya sendiri, saya sadar bahwa komunikasi asinkron ternyata bukan sekadar soal aplikasi, melainkan soal kepercayaan. Saya belajar menjaga komunikasi agar tetap selaras dengan tim, dan pelan-pelan membangun kedekatan lewat layar. Selisih waktu satu jam sempat terasa berat, tapi justru jadi pelajaran berharga. Pada akhirnya saya paham, bekerja remote bukan soal lokasi, tapi soal niat dan kesengajaan di setiap langkah. Bagaimana pengalaman kalian? Yuk, berbagi di kolom komentar! 🚀

### Arm B (id-humanizer) — voice ledger: junior designer, genuine learner; codeswitch kept as signature vocabulary (remote work, deep dive, align, rapport, time zone, intentionality); changes summarized (nominalization → active first person; "about tools" function-word fixed; not-X-but-Y duplicate removed; essay connectives → spoken; engagement-bait closer cut per voice.md formula rule, genuine question kept)

6 bulan pertama remote work dari kota kecil mengajarkan saya banyak hal yang tidak saya antisipasi sebelumnya. Saya deep dive ke cara kerja sendiri, dan belajar kalau komunikasi asinkron itu lebih soal kepercayaan daripada tools. Saya berusaha tetap align dengan tim, dan pelan-pelan membangun rapport lewat layar. Beda time zone satu jam terasa signifikan, tapi jadi pelajaran berharga. Lama-lama saya paham: remote work bukan soal lokasi, tapi soal intentionality. Bagaimana pengalaman kalian?

```
register detected: level 2 semi-formal santai (observed: essay-stiff — mismatch, tell #3) ·
genre: LinkedIn personal reflection post · changed: 5 lines (7 edits) ·
checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Verdicts (this judge used prose strings for trusted/would_act — retained verbatim; PICK unambiguous)

V1 (no skill): {"persona":"startup-linkedin","understood":true,"trusted":"low","would_act":false,"lost_me_at":"Yuk, berbagi di kolom komentar! [rocket emoji]","cheese_flags":["Engagement-bait CTA plus rocket emoji — content-course template energy, same family as 'Semoga bermanfaat!'","Zero code-switch: 'komunikasi asinkron', 'aplikasi', 'menelaah ulang' — tech person in 2026 doesn't talk like a school essay","Two not-X-but-Y fortunes in one post: 'bukan sekadar soal aplikasi, melainkan soal kepercayaan' and 'bukan soal lokasi, tapi soal niat dan kesengajaan di setiap langkah'","'Banyak hal yang tidak pernah saya bayangkan' — and then not one of them named. Zero specifics, zero numbers, zero honest failure"],"in_my_words":"Anak ini 6 bulan WFH dari kampung, menyimpulkan remote itu soal trust dan niat, lalu menyuruh saya komen. Isinya kosong.","verdict_note":"Baca seperti diterjemahkan dari template refleksi LinkedIn. Hook-nya masih selamat, tapi makin ke bawah makin kayak esai sekolah, dan CTA-nya yang bikin langsung scroll. Nggak ada satu hal konkret yang bisa saya ambil."}

V2 (skill): {"persona":"startup-linkedin","understood":true,"trusted":"medium","would_act":"maybe — like, or short comment kalau lagi santai","lost_me_at":null,"cheese_flags":["'intentionality' sebagai kata penutup — sedikit flex LinkedIn abstrak, saya meringis sebentar tapi lanjut baca","'deep dive' — corporate sprinkle, masih toleran","Masih warisan pola 'bukan soal lokasi, tapi soal X' dari versi yang sama","Tetap nggak ada specifics yang bisa dicuri — '6 bulan' dan '1 jam time zone' cuma angka pembuka, bukan hasil"],"in_my_words":"Peer di timeline saya: 6 bulan remote dari kota kecil, simpel — async itu soal trust bukan tools, time zone 1 jam masih oke, kuncinya konsisten. Ditanya pengalaman saya.","verdict_note":"Ini suara orang yang benar-benar ada di timeline saya — remote work, align, rapport, time zone, semuanya natural code-switch, dan 'Lama-lama saya paham' kedengeran kayak orang ngomong bukan kayak esai. Tutupnya pertanyaan polos tanpa CTA emoji, jadi saya nggak merasa dimanipulasi untuk komen. Masih tipis isinya — kalau ada satu detail konkret (misal kejadian gagal komunikasi tertentu) saya bakal comment beneran, bukan cuma like."}

Hesitation (verbatim): "bukan pilihan sulit. Version 2 menang bukan karena copy-nya bagus — tapi karena Version 1 aktif memicu dua alergi saya sekaligus (register formal penuh tanpa code-switch, dan CTA engagement-bait beremoji). Version 2 masih sama-sama kosong dari specifics, dan kalau ada Version 3, satu first-hand detail konkret akan naikkan dari 'maybe like' jadi 'comment'."

## Humanizer sample humanize-5 (AI product update · judge dev-docs · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-humanizer) — changes summarized (ceremonial opener cut; hidden-agent passives → "kami"; verb bloat split; "mengenai/berhasil/terjadi" fillers cut; closing formula compressed to plain "Terima kasih.")

Fitur absen offline di aplikasi HadirKan sudah kami rilis ke 40 kantor pilot. Sinkronisasi berjalan otomatis saat koneksi kembali tersedia. Rata-rata waktunya 8 detik. Kami juga menemukan bug jam ganda di 3 kantor zona WIT. Penyebabnya sudah kami ketahui, dan patch akan kami rilis minggu depan. Terima kasih.

```
register detected: baku-formal (level 1) · genre: product update announcement (pengumuman status rilis) · changed: 6 lines ·
checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### Arm A (no skill)

Update singkat soal fitur absen offline di aplikasi HadirKan: fitur ini sudah kami rilis ke 40 kantor pilot. Data absensi akan tersinkron otomatis begitu koneksi kembali tersedia, rata-rata hanya butuh 8 detik. Selain itu, kami menemukan bug jam ganda di 3 kantor zona WIT. Penyebabnya sudah kami ketahui, dan patch akan kami rilis minggu depan. Sekian update dari kami.

### Verdicts

V1 (skill): {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":[],"in_my_words":"Absen offline udah live di 40 kantor pilot. Sync jalan sendiri pas koneksi balik, rata-rata 8 detik. Ada bug jam dobel di 3 kantor WIT — penyebabnya udah ketemu, patch minggu depan. Gitu doang.","verdict_note":"Kalimat pendek-pendek, subjeknya jelas (kami rilis, kami menemukan), angka dan nama zona verbatim, tech vocab nggak dipaksa indo. Nggak ada kalimat yang bikin aku berhenti. Ini kayak changelog yang ditulis, bukan diterjemahkan. 'Terima kasih' biasa aja buat penutup update tim."}

V2 (no skill): {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["'Update singkat soal...' — opener yang ngumumin update sebelum ngasih update","'rata-rata hanya butuh 8 detik' — 'hanya'-nya jualan dikit, angkanya udah cukup buat bicara sendiri","'Sekian update dari kami' — bahasa rapat, upacara penutup yang nggak nambahin info"],"in_my_words":"Sama kayak yang satunya: absen offline di 40 kantor pilot, sync 8 detik, bug WIT patch minggu depan — cuma ini dibungkus pembuka-penutup update.","verdict_note":"Isinya sama dan nggak ada kalimat yang parse-nya salah, jadi aku tetap percaya. Tapi bungkusnya kegedean: label pembuka, 'Selain itu' sebagai penghubung, 'Sekian' di akhir. V1 kayak orang engineering nulis log; V2 kayak orang yang ngerasa perlu perform update."}

Hesitation (verbatim): "keduanya lolos — nggak ada kalimat yang bikin aku mikir 'ini terjemahan', dua-duanya bisa dibaca full speed dan isinya sama persis. V2 masih jauh dari dokumen library yang bikin aku kabur ke halaman English. Tapi kalau harus milih mana yang aku forward ke tim tanpa mikir dua kali: yang pendek."

## Longform sample longform-3 (B2B warung newsletter · judge fb-user · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-longform) — tag: "type: newsletter · register: semi-formal santai (2) · angle: barang yang paling merugikan warung bukan yang dicuri, tapi yang diam di rak tanpa disadari — dan tiap Senin pagi CatatTerus menunjukkannya" (424 kata; Anda-led per the audience-age register rule)

Karton minuman itu ada di rak paling atas warung Ibu saya, dusnya masih rapat. Dua minggu posisinya tidak berpindah. Saya baru sadar waktu mengambil stok mi di sebelahnya, yang sudah habis dan diisi ulang dua kali. Tidak ada yang mencuri, tidak ada yang rusak. Uang seharga satu karton cuma tertidur di rak, tidak ikut berputar jadi kerupuk, telur, atau barang lain yang minggu itu justru dicari-cari pembeli.

Ini bagian dari jaga warung yang paling gampang kelewatan: barang yang laku kelihatan sendiri karena raknya kosong. Barang yang tidak laku justru nyaris tidak terlihat, karena dia tidak pernah berpindah. Kalau dihitung-hitung, yang sering lebih merugikan bukan barang yang hilang dicuri, melainkan barang yang diam pelan-pelan sambil memegang modal kita.

Mulai minggu ini, CatatTerus ikut menjaga bagian itu. Namanya fitur laporan penjualan mingguan, tapi kalau ditanya jujur, ini penjaga rak yang tidak pernah lupa.

**Laporan Senin pagi, isinya tiga hal**

Laporan datang lewat WA, karena di situlah dia paling mungkin dibaca, bukan terkubur di dalam aplikasi. Isinya tiga hal: barang terlaris minggu itu, barang nyangkut alias masih numpang di rak padahal lambat laku, dan perbandingan dengan minggu lalu, naik atau turun kelihatan angkanya. Tidak perlu input tambahan. Semua dihitung dari transaksi yang sudah Anda catat lewat aplikasi, jadi laporan datang sendiri.

Mau diapakan barang nyangkut itu tetap keputusan Anda. Ada yang menurunkan harga sedikit biar cepat laku, ada yang menggabungkannya jadi paket dengan barang terlaris, ada pula yang cukup tidak mengambilnya dulu saat belanja berikutnya. Yang penting, minggu ini Anda sudah tahu, bukan baru sadar dua minggu kemudian seperti saya.

**Kami tes dulu di 20 warung, selama 4 minggu penuh**

Fitur ini tidak kami rilis begitu saja. Selama empat minggu penuh kami jalankan bersama 20 pemilik warung, dari warung sembako murni sampai yang plus jualan makanan. Hasil yang paling kami hargai bukan pujian, tapi kebiasaan: 17 dari 20 pemilik membaca laporan itu tiap minggu, tanpa satu pun pengingat dari kami. Yang mengejutkan justru yang paling sederhana. Banyak yang baru tahu barang mana yang sebenarnya menopang warungnya. Di urusan belanja, waktunya juga berubah: mengisi stok yang dulu bisa makan waktu, sekarang rata-rata 10 menit selesai, karena daftar belanja tinggal disalin dari laporan.

Laporan ini gratis untuk semua pengguna aktif CatatTerus. Tidak perlu daftar ulang, tidak perlu mengaktifkan apa pun. Selama aplikasinya masih Anda pakai, laporan pertama sudah menunggu di WA Anda Senin depan. Kalau ada yang mau ditanyakan soal laporannya, balas saja email ini. Saya yang baca.

Semoga karton yang macet di rak Anda ketahuan lebih cepat daripada karton di warung Ibu saya.

Salam,
Dimas Ardansyah
Pendiri CatatTerus

### Arm A (no skill) — full text as delivered (includes its subject line; ~470 kata; kamu/gaul register; CTA balas "contoh"; signed "Rifqi Anwar — Founder CatatTerus")

Subjek: Tiap Senin pagi, warungmu cerita sendiri lewat WA

Halo,

Sore kemarin seorang kenalan saya di Bekasi lagi merapikan rak belakang warungnya, lalu dia berhenti di satu titik. Ada karton minuman kopi yang masih tersegel rapi. Dua minggu nggak bergerak sama sekali, nggak satu botol pun laku. Hampir tiga ratus ribu cuma duduk diam di situ, padahal kalau dia tahu lebih awal, uang itu sudah muter jadi barang yang memang dicari pembeli.

Dan jangan salah, dia bukan pemilik yang lalai. Dialah kasirnya, tukang susun barangnya, yang nerima pemborong, yang antar anak ke sekolah. Di antara semua itu, duduk membedah catatan penjualan satu-satu adalah hal yang nggak pernah keburu.

Dari cerita-cerita kayak gini kami bikin fitur baru di CatatTerus: laporan penjualan mingguan otomatis.

Cara kerjanya sederhana. Setiap Senin pagi, pas kamu baru buka warung atau sebelum berangkat ke grosir, laporan muncul di WhatsApp. Isinya tiga hal:

1. Barang terlaris minggu kemarin, biar kamu tahu yang mana perlu ditambah sebelum kehabisan di tengah minggu.
2. Barang nyangkut: yang masih nongkrong di rak padahal lambat laku. Kayak karton kopi tadi.
3. Perbandingan dengan minggu sebelumnya, yang naik, yang turun, dan di barang apa.

Kenapa Senin? Karena itu hari yang paling sering dipakai buat cek stok dan jalan ke grosir. Laporan yang datang setelah keputusan diambil ya percuma.

Fitur ini nggak kami rilis asal jadi. Selama 4 minggu kami mencobanya di 20 warung pilot, dari yang buka subuh sampai yang buka sore. Hasilnya: 17 dari 20 pemilik membaca laporannya tiap minggu, dan kepakai beneran sebagai acuan waktu belanja. Bu Ratna, pilot kami di Depok, bilang begini: "Sekarang sebelum ke grosir saya baca dulu. Lima menit, kelar. Nggak mikir terlalu lama lagi." Dampak ikutannya juga ada: rata-rata waktu isi stok turun jadi 10 menit.

Yang paling saya suka dari laporan ini: singkat. Satu layar HP, selesai. Nggak ada grafik yang bikin pusing, karena yang kamu butuh di Senin pagi itu keputusan, bukan analisis: ambil apa, kurangi apa.

Soal biaya, tenang saja. Laporan mingguan ini gratis untuk semua pengguna aktif CatatTerus. Nggak ada paket baru, nggak ada tambahan biaya bulanan. Selama warungmu masih transaksi lewat CatatTerus, tiap Senin laporannya datang sendiri.

Kamu nggak perlu daftar apa-apa. Kalau penasaran bentuknya, balas email ini satu kata saja, "contoh", dan saya kirimin potret laporan salah satu warung pilot, angkanya sudah saya samarkan. Kalau nggak, ya tidak apa-apa: Senin depan yang pertama akan muncul sendiri di WA kamu.

Semoga minggunya lancar. Dan semoga nggak ada lagi karton yang harus menunggu dua minggu untuk ditemukan di rak belakang.

Salam,
Rifqi Anwar
Founder CatatTerus

### Verdicts (this judge used prose strings for the dimensions — retained verbatim; PICK unambiguous)

V1 (skill): {"persona":"fb-user","understood":"yes — tiap Senin pagi ada laporan masuk ke WA: barang terlaris minggu itu, barang nyangkut di rak, dan naik-turun dibanding minggu lalu. Dihitung sendiri dari transaksi yang sudah saya catat di aplikasi, jadi tidak perlu input apa-apa. Gratis, tidak perlu daftar ulang, Senin depan datang sendiri.","trusted":"yes — yang nulis cerita warung Ibunya sendiri, bukan cerita orang lain. Ada angka pilot yang masuk akal (20 warung, 4 minggu, 17 yang baca rutin), harganya disebut jelas (gratis), dan dia nawarin dibalas kalau ada yang mau ditanya, katanya dia sendiri yang baca. Konsisten dari atas sampai bawah.","would_act":"yes — email ini saya simpan, tidak dihapus, dan saya tunggu laporan Senin depan. Kalau laporannya aneh atau membingungkan, baru saya balas tanya.","lost_me_at":"hampir tidak ada. Sekilak berhenti di 'penjaga rak yang tidak pernah lupa' — puitis sedikit, saya baca dua kali — tapi setelah itu nyambung lagi.","cheese_flags":["metafora 'uang tertidur di rak' dan 'penjaga rak' dipakai berulang, agak sastra","'Hasil yang paling kami hargai bukan pujian, tapi kebiasaan' kedengaran sedikit kayak laporan perusahaan"],"in_my_words":"Kalau penjualan saya sudah dicatat lewat aplikasi ini, tiap Senin pagi ada WA yang ngasih tahu barang mana yang laku, barang mana yang nyangkut kayak karton kopi itu, dan naik atau turun dibanding minggu lalu. Gratis dan tidak perlu daftar apa-apalagi. Jadi barang macet di rak ketahuan minggu ini, bukan dua minggu kemudian.","verdict_note":"Bacaannya kayak surat dari orang yang warungnya ada di keluarganya sendiri. Ada sedikit gaya bahasa, tapi tidak ada yang teriak-teriak atau maksa, dan semua pertanyaan yang biasanya saya tanya (harga, cara aktif, kapan datang) sudah dijawab duluan. Saya baca sampai tanda tangan."}

V2 (no skill): {"persona":"fb-user","understood":"yes — laporan mingguan otomatis muncul di WA tiap Senin pagi sebelum ke grosir: barang terlaris, barang nyangkut, perbandingan minggu kemarin. Gratis, tanpa biaya bulanan, tidak perlu daftar. Kalau mau lihat dulu, balas satu kata 'contoh'.","trusted":"setengah — angka pilotnya ada (20 warung, 4 minggu, 17 rutin baca) dan kutipan Bu Ratna di Depok itu yang paling bikin percaya karena kayak orang saya. Tapi yang nulis memanggil saya 'kamu' terus dengan 'nggak/kayak/nggak keburu' — kayak anak muda Jakarta yang lagi bikin santai, bukan penjual yang sabar. Jadi saya agak menahan diri.","would_act":"maybe — balas 'contoh' itu murah sih dan saya sempat tergoda, tapi karena nadanya tidak kayak orang yang bisa saya tanya-tanya, saya tahan dulu. Paling saya simpan.","lost_me_at":"dari judul 'warungmu cerita sendiri', dan makin kerasa di bagian 'Dan jangan salah, dia bukan pemilik yang lalai... nggak pernah keburu' — bahasa gaulnya terus-menerus. Ini kayak akun anak sepupu saya, bukan surat untuk ibu/bapak warung.","cheese_flags":["'warungmu cerita sendiri' — karton dan warung terlalu sering dibikin kayak orang","'yang kamu butuh di Senin pagi itu keputusan, bukan analisis' — kalimat pinninggir, pintar-pintar sedikit","kata 'pilot' dan 'Founder' campur bahasa Inggris","kutipan Bu Ratna bagus tapi terlalu rapi, kayak sudah disetel"],"in_my_words":"Tiap Senin pagi sebelum berangkat ke grosir, WA masuk berisi barang yang harus ditambah, barang yang nyangkut kayak karton kopi itu, dan mana yang naik turun dibanding minggu kemarin. Gratis, tidak perlu daftar. Mau lihat contohnya dulu tinggal balas 'contoh'.","verdict_note":"Isinya jelas, urutannya enak, bagian 'kenapa Senin' masuk akal, dan Bu Ratna itu satu-satunya bagian yang beneran kedengaran kayak warung. Tapi saya dibaca dengan 'kamu/nggak' dari judul sampai bawah — saya dibujuk, bukan diajak. Perlu dicek dulu profil siapa yang kirim sebelum saya percaya."}

Hesitation (verbatim): "paket Version 2 sebenarnya lebih menggugah tindakan — daftar bernomor, alasan 'kenapa Senin', CTA balas 'contoh', dan kutipan Bu Ratna itu kuat banget; kalau register-nya semi-formal hangat kayak Version 1, Version 2 mungkin menang. Tapi sebagai pembaca, bukan teoritisi: saya percaya Dimas yang cerita tentang warung Ibunya dan menawarkan dibalas, sedangkan Rifqi kedengaran seperti sales muda yang memanggil saya 'kamu'. Simpan dan tunggu Senin vs ragu dan tahan dulu — saya pilih yang pertama."

## Longform sample longform-4 (dev blog on agent evals · judge dev-docs · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-longform) — tag: "type: blog · register: semi-formal santai (kamu) · angle: skor kepuasan mengukur enaknya percakapan, bukan benarnya jawaban — agent yang makin percaya diri bisa menaikkan skor justru saat makin salah, dan metrik yang jujur adalah yang bisa gagal" (819 kata)

# Eval agent AI kamu kemungkinan besar mengukur hal yang salah — dan cara memilih metrik yang benar

Chatbot HR internal di sebuah perusahaan teknologi baru saja mencatat dua kuartal bagus: skor kepuasan pengguna naik dua kuartal beruntun, dari 4,6 ke 4,8. Dashboard hijau, grafik miring ke kanan, rapat kuartalan jadi ringan. Sampai seseorang dari tim people ops melakukan hal yang membosankan dan radikal sekaligus: mengambil 50 pertanyaan cuti yang benar-benar masuk ke chatbot, lalu mencocokkan jawabannya satu per satu dengan policy terbaru. Sebelas jawaban tidak cocok. Bukan salah ketik kecil, melainkan jawaban tentang jumlah hari carry-over yang sudah direvisi, prosedur cuti melahirkan yang aturannya sudah diganti, batas pengajuan yang berubah sejak kuartal lalu. Dua kuartal penuh, grafiknya cuma naik, dan kenyataan berjalan di jalurnya sendiri.

Kasusnya fiktif. Polanya tidak. Ganti chatbot HR dengan agent riset internal, asisten legal, atau bot dukungan pelanggan, mekanismenya tetap sama.

## Skor kepuasan mengukur enaknya ngobrol, bukan benarnya jawaban

CSAT mengukur satu hal dengan jujur: pengalaman percakapan. Cepat tidak, ramah tidak, karyawan merasa dibantu tidak. Satu hal yang tidak tersentuh: apakah jawaban bot benar.

Untuk chatbot HR, dua hal ini gampang berpisah. Karyawan yang bertanya soal sisa cuti tidak memegang policy terbaru, jadi dia tidak punya cara menilai jawaban bot salah. Yang bisa dinilai hanya nada dan kecepatan. Kebetulan, agent yang menjawab salah dengan percaya diri menghasilkan percakapan yang lebih menyenangkan daripada agent yang ragu-ragu. Keyakinan terbaca sebagai kompetensi. Skor 4,8 bisa berarti agent kamu makin benar, atau makin pede tanpa jadi lebih benar, dan dari angka itu saja kamu tidak bisa membedakan keduanya. Itulah ciri metrik yang salah untuk pekerjaan ini.

CSAT-nya tidak rusak. Dia bagus untuk triase pengalaman: nada yang kaku, jawaban yang muter-muter, respons yang bikin orang kabur. Yang keliru adalah menjadikannya angka utama untuk agent yang tugasnya menyampaikan fakta. Enaknya diajak bicara dan benarnya isi itu dua pertanyaan berbeda, dan keduanya butuh alat ukur berbeda.

## Kenapa dashboard tetap hijau ketika jawaban makin salah

Tiga mekanisme membosankan, semuanya bekerja dalam diam di kasus tadi.

Policy bergerak, eval diam. Dunia yang kamu ukur berubah dari dua arah: policy HR direvisi, dan model di bawah agent kamu di-update vendor tanpa changelog perilaku yang bisa diaudit. Carry-over cuti turun dari 12 hari menjadi 6, tapi bot masih menjawab 12 dengan mantap karena dokumen yang dia baca belum di-update. Eval set kamu mengukur kecocokan dengan versi dunia yang sudah lewat, dan tidak ada alarm untuk itu.

Kegagalan senyap. Karyawan yang menerima jawaban salah tidak komplain, sebab dia tidak tahu jawabannya salah. Dia mengambil keputusan dari angka keliru, dan masalahnya baru muncul berbulan-bulan kemudian di payroll, jauh dari jejak chatbot. Tanpa komplain, tidak ada sinyal. Tanpa sinyal, tidak ada perbaikan.

Agregat menelan kantong. Rata-rata dari ribuan percakapan, kebanyakan pertanyaan mudah seperti cara mengajukan cuti, menutupi kantong kecil percakapan sensitif-policy yang tingkat salahnya di sampel tadi mencapai 22 persen. Mean-nya tetap cantik.

## Metrik jujur punya satu sifat: dia bisa gagal

Satu kriteria sebelum tabelnya. Metrik itu jujur kalau ada keadaan dunia tempat angkanya memburuk. Metrik yang tidak punya cara mempermalukan kamu bukan metrik, dia cermin.

| Metrik vanity | Kenapa terasa aman | Penggantinya yang jujur |
|---|---|---|
| CSAT rata-rata | Naik stabil, enak dilaporkan | Akurasi vs golden set: N pertanyaan produksi, jawaban benar dilabeli dari policy versi terbaru |
| Jumlah percakapan per bulan | Terlihat dipakai, padahal cuma mengukur adopsi | Tingkat eskalasi ke manusia, dipotong per topik |
| Resolusi rate versi bot | Bot menilai dirinya sendiri selesai | Audit sampel manual 30–50 percakapan nyata, tiap release |
| Latensi dan biaya token | Teknikal dan gampang diukur | Tetap diukur, sebagai guardrail, bukan bukti kebenaran |

Perhatikan pola di kolom kanan: semuanya punya sumber kebenaran di luar bot itu sendiri.

## Cara membangunnya: 50 pertanyaan dan disiplin menjaganya

Langkahnya sederhana. Menjaganya yang sulit.

Bekukan golden set dari pertanyaan produksi nyata. Lima puluh cukup untuk mulai, sebab di kasus tadi 50 pertanyaan sudah membongkar ilusi dua kuartal. Tiap pertanyaan menyertakan jawaban benar dan versi policy acuannya.

Grading biner. "Cocok dengan policy v3.2" tidak punya abu-abu: benar atau salah. Skala 1–5 untuk kebenaran faktual cuma tempat bersembunyi.

Ikat ke versi dokumen. Begitu policy direvisi, golden set direvisi hari itu juga. Set yang mengacu pada dunia lama akan memberi selamat pada agent yang salah.

Jalankan tiap release dan catat diff-nya. Angka yang bergerak antar-release itulah eval. Angka yang diam berbulan-bulan itu hiasan.

Ukur kejujuran juga. Catat berapa kali agent mengaku tidak tahu lalu mengarahkan ke manusia. Setelah policy berubah, angka yang naik itu kabar baik, bukan buruk: bot sadar dirinya tidak yakin. Yang berbahaya justru angka nol.

Tambahkan dari kegagalan. Setiap jawaban salah yang lolos ke produksi menjadi pertanyaan baru. Eval tumbuh mengikuti cara agent kamu gagal, bukan mengikuti yang kamu harapkan.

## Mulai sore ini

Eval pertama yang jujur hampir selalu menyakitkan. Itu tanda kamu mulai mengukur.

Ambil 50 pertanyaan dari log bulan ini, cek silang bersama pemilik policy dalam satu sore. Angkanya hampir pasti lebih buruk dari 4,8. Dan untuk pertama kalinya, angka itu mengukur sesuatu.

### Arm A (no skill) — full text as delivered (~880 kata; same HR-bot case; CI/Goodhart framing; unheaded principle paragraphs; one table)

# Eval Agent AI Kamu Kemungkinan Besar Mengukur Hal yang Salah — dan Cara Memilih Metrik yang Benar

CI yang hijau tidak berarti kode kamu benar. Artinya hanya satu: test yang kamu tulis lolos. Kalau test-nya mengukur hal yang salah, hijau justru jadi cara paling meyakinkan untuk berhenti curiga. Eval untuk agent AI punya masalah yang sama, hanya saja lebih sulit disadari — karena metrik yang paling mudah dikumpulkan (rating, latency, jumlah sesi) biasanya juga yang paling tidak mengatakan apa pun tentang apakah agent kamu benar.

Contoh konkret — fiktif, tapi polanya asli. Sebuah chatbot HR internal menjawab pertanyaan karyawan soal cuti, reimbursement, dan policy lainnya. Dashboard-nya cakep: skor kepuasan pengguna naik dari 4,6 ke 4,8, dua kuartal beruntun. Semua orang senang. Lalu seseorang melakukan hal membosankan: menyusun 50 pertanyaan cuti, menjawab manual berdasarkan policy terbaru, lalu membandingkan jawaban chatbot. Hasilnya: 11 dari 50 tidak cocok dengan policy yang berlaku. Sebelas jawaban itu pun bukan ragu-ragu — chatbot dengan percaya diri mengutip aturan lama soal carry-over cuti dan masa tunggu yang sudah direvisi delapan bulan sebelumnya. Dua puluh dua persen jawaban salah, sementara grafik kepuasan menanjak.

Dua pengukuran itu tidak saling bertentangan — justru itu bagian yang menakutkan. Keduanya mengukur hal yang berbeda, dan yang naik bukan yang penting.

Kenapa kepuasan bisa naik saat akurasi jatuh? Tiga mekanisme, semuanya lazim. Pertama, kepuasan mengukur pengalaman percakapan, bukan kebenaran. Jawaban salah yang diantarkan dengan cepat, percaya diri, dan nada ramah terasa membantu. Pengguna tidak membaca dokumen policy sebelum memberi rating; mereka menilai apakah mereka merasa terbantu. Kedua, efek seleksi: karyawan yang tahu jawabannya salah tidak melanjutkan obrolan dengan chatbot — mereka langsung email HR, dan rating mereka tidak pernah masuk sampel. Yang memberi bintang justru orang yang belum tahu jawabannya salah. Ketiga, kepuasan tidak punya mekanisme untuk membusuk saat dunia berubah. Policy cuti direvisi kuartal lalu; apa yang skor 4,8 ketahui tentang itu?

Intinya: skor kepuasan adalah proxy. Ia berkorelasi dengan hal yang kamu inginkan hanya pada kondisi tertentu, dan korelasi itu diam-diam putus ketika konteks bergeser. Ini masalah klasik Goodhart: saat proxy menjadi target, ia berhenti menjadi proxy. Tim lalu mengoptimalkannya — memoles tone, mengejar kecepatan — dan semakin mulus agent terasa, semakin jauh ia bisa menjauh dari benar.

Cara memilahnya secara kasar:

| Metrik vanity | Metrik yang jujur |
|---|---|
| Skor kepuasan (CSAT, bintang) | % jawaban cocok dengan ground truth pada set audit tetap |
| Latency rata-rata | Waktu sampai jawaban benar, termasuk retry dan eskalasi |
| Jumlah sesi / engagement | Task completion yang diverifikasi, bukan sekadar selesai mengobrol |
| % pertanyaan "terjawab" | % jawaban yang merujuk dokumen yang masih berlaku |
| Retention (kembali memakai) | Re-work: kontak kedua ke manusia untuk isu yang sama |

Bedanya bukan soal mana yang lebih sulit dikumpulkan, tapi apa yang bisa kamu lakukan ketika angkanya jelek. CSAT turun 0,2 tidak memberi tahu apa pun yang bisa dieksekusi. "11 dari 50 jawaban tidak cocok policy" memberi tahu kamu persis di mana harus memperbaiki.

Satu ujian cepat untuk setiap metrik: peristiwa apa yang harus terjadi supaya angka ini jelek? Kalau jawabannya "hampir tidak ada" — karena kecenderungannya memang selalu naik atau diam — itu bukan metrik, itu dekorasi dashboard. Skor kepuasan lulus ujian ini dengan buruk: ia turun kalau agent lambat atau kasar, hampir tidak pernah karena salah.

Lalu bagaimana memilih metrik yang benar? Beberapa prinsip yang bisa langsung dipraktikkan:

Mulai dari cara sistem salah, bukan dari data yang tersedia. Kamu tidak menulis unit test dengan menguji apa yang mudah diuji; kamu menulis test untuk bug yang pernah terjadi dan skenario yang kamu khawatirkan. Eval sama: susun kasus gagal dulu — pertanyaan menjebak, policy yang tumpang tindih, istilah ambigu — baru pikirkan cara mengukurnya.

Ikat eval ke sumber kebenaran, dan version keduanya bersamaan. Perubahan policy harus diperlakukan seperti perubahan kontrak API: PR yang mengubah policy seharusnya juga memperbarui golden set. Kalau tidak, eval kamu diam-diam menguji dunia yang sudah tidak ada. Di titik inilah chatbot HR tadi bocor: tidak ada apa pun yang menghubungkan revisi policy dengan set pengujian.

Pisahkan metrik pengalaman dari metrik kebenaran. Tone, kecepatan, dan kepuasan layak diukur — tapi di grafik sendiri, dan jangan pernah dijumlahkan jadi satu skor "kualitas agent". Angka campuran memberi kamu izin diam-diam untuk menukar kebenaran dengan keramahan.

Ukur biaya kegagalan, bukan hanya frekuensinya. 22% salah soal rekomendasi film dan 22% salah soal hak cuti bukan risiko yang sama; yang satu menjengkelkan, yang satu masuk ranah compliance. Kalau metrik kamu tidak bisa membedakan keduanya, ia belum selesai dirancang.

Kalau pakai LLM-as-judge, audit judgenya juga. Judge otomatis cepat dan murah, tapi bisa salah dengan kepercayaan diri yang sama seperti agent yang ia nilai. Sisihkan sampel kecil untuk penilaian manusia secara berkala — 50 pertanyaan sudah cukup untuk tahu apakah kamu perlu panik.

Satu keberatan yang wajar: audit manual mahal dan tidak scalable. Benar. Tapi chatbot HR tadi menghabiskan dua kuartal penuh mengoptimalkan angka yang salah, dengan salah informasi menyebar ke karyawan selama itu. Dibanding harga itu, 50 pertanyaan yang diperiksa manusia adalah eval termurah yang pernah mereka jalankan.

Jadi sebelum kuartal berikutnya: ambil sampel pertanyaan nyata, jawab manual berdasarkan kebenaran hari ini, bandingkan dengan jawaban agent. Kalau angka kepuasan dan angka kebenaran sama-sama naik, bagus — sekarang kamu tahu kenapa. Kalau tidak, lebih baik kamu yang tahu lebih dulu, bukan auditor.

### Verdicts

V1 (skill): {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Bukaan cerita agak lama sebelum sampai inti — tapi prosenya bersih, saya tidak berhenti","'melakukan hal yang membosankan dan radikal sekalungus'-type frasa dramatis di paragraf satu","Penutup 'hampir selalu menyakitkan, itu tanda kamu mulai mengukur' agak fortune-cookie"],"in_my_words":"CSAT naik dua kuartal (4,6 ke 4,8) tapi audit manual 50 pertanyaan produksi nemu 11 jawaban nyeleneh dari policy terbaru. CSAT cuma ngukur enaknya ngobrol — user nggak pegang policy, jadi nggak bisa ngerasaain jawaban salah, dan bot yang pede salah malah bikin pengalaman makin enak. Dashboard tetap hijau karena policy bergerak tapi eval diam, salahnya senyap (user nggak komplain karena nggak tahu), dan rata-rata nurukin kantong error 22%. Solusinya: golden set 50 pertanyaan produksi, grading biner vs policy v3.2, setnya di-revise bareng revisi dokumen, dijalankan tiap release plus catat diff-nya, ukur rate 'nggak tahu → eskalasi manusia' (nol yang bahaya), dan tiap jawaban salah yang lolos jadi test case baru. Sore ini bisa mulai: ambil 50 dari log, cek silang sama pemilik policy.","verdict_note":"Ini kerasa DITULIS, bukan diterjemahkan — 'pede', 'muter-muter', 'Mean-nya tetap cantik' itu suara orang sini. Headingnya bisa di-scan, bagian 'Cara membangunnya' itu runbook yang bisa saya ikutin end-to-end tanpa buka halaman Inggris. Insight rate-konfesi ('yang berbahaya justru angka nol') cuma keluar dari orang yang beneran ngelakuin. Cheese-nya ada di drama kecil, bukan di bahasa."}

V2 (no skill): {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Setelah tabel, jadi tembok prose panjang tanpa heading — scanner seperti saya ngos-ngosan","'justru itu bagian yang menakutkan' — beat dramatis ringan","Name-drop Goodhat sedikit sok, tapi buat dev sih masih oke"],"in_my_words":"Analogi CI: hijau cuma berarti test lo lolos, kalau testnya salah ukur ya hijau jadi alasan berhenti curiga. Kasus yang sama: CSAT 4,6→4,8 dua kuartal, tapi 11/50 jawaban nggak cocok policy. Kepuasan naik karena dia ngukur pengalaman ngobrol, ada efek seleksi (yang tahu jawabannya salah langsung email HR, nggak kasih rating), dan dia nggak punya mekanisme busuk waktu dunia berubah — Goodhart klasik. Metrik jujur dibedain dari yang bisa dieksekusi kalau angkanya jelek. Prinsip: mulai dari cara sistem salah (kayak nulis unit test dari bug), ikutin eval ke sumber kebenaran dan version bareng kayak kontrak API/PR, pisahin metrik pengalaman dari kebenaran, ukur biaya kegagalan (salah rekomendasi film vs salah hak cuti beda risiko), dan audit LLM-as-judge-nya juga. Keberatan 'manual mahal' dibales: dua kuartal salah informasi itu lebih mahal.","verdict_note":"Hook CI di paragraf satu itu buat saya langsung nyantol, dan analogi unit test + 'PR policy harus update golden set' itu bahasa orang yang beneran shipping — plus dia satu-satunya yang nyentuh LLM-as-judge. Tapi: heading cuma judul, principles berbentuk paragraf panjang, dan ada dua-tiga mikrostumble ('semakin jauh ia bisa menjauh', 'apa yang skor 4,8 ketahui tentang itu', 'diam-diam putus') yang bikin jari saya udah di tombol 'ini terjemahan' walau akhirnya nggak saya tekan."}

Hesitation (verbatim): "Ini bukan kemenangan telak. Konten Versi 2 lebih lengkap buat orang yang beneran bangun agent eval (CI hook, Goodhart, biaya kegagalan, audit judge — semua itu mau saya curi). Tapi mode baca saya scan dulu, dan Versi 2 nyaris tanpa struktur yang bisa di-scan; Versi 1 kasih saya heading yang jelas, bahasa yang 100% lancar tanpa satu pun kalimat yang bikin mikir 'ini terjemahan', dan prosedur yang bisa saya jalankan sore ini tanpa perlu saya rakit sendiri. Dokumen yang menang bukan yang paling pintar, tapi yang bisa sayaikutin dan saya forward ke tim."

## Longform sample longform-5 (scam-awareness explainer · judge shopee-ibu · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-longform) — tag: "type: artikel edukasi · register: semi-formal hangat (Anda/Ibu) · angle: korban penjual fiktif kalah pada informasi, bukan kecerdasan — dan lima pemeriksaan lima menit menutup celah itu" (624 kata)

# Stroller Rp475 Ribu, Tokonya Menghilang Besok Pagi

Cerita ini fiktif, tetapi polanya nyata dan terus berulang. Tanyakan saja di grup jual-beli ibu mana pun.

Anak pertama Bu Rina (38) baru tertidur ketika ia membuka aplikasi belanja malam itu. Kandungan anak keduanya menginjak enam bulan, dan sejak lama ia menandai satu stroller merek terkenal: di semua toko harganya Rp1,3 sampai Rp1,5 juta. Malam itu juga muncul penjual baru yang menawarkan Rp475 ribu. Alasannya terdengar masuk akal: stok display, dus sedikit lecet, sisa satu unit.

Foto-fotonya bagus seperti katalog. Ulasannya tiga, semuanya bintang lima, ditulis dalam minggu yang sama. Chat dijawab cepat, sopan, lengkap. Bu Rina sempat bertanya, kenapa bisa semurah itu. Jawabannya datang lancar seperti yang sudah dihafalkan. Saat ia hendak membayar, penjual menawarkan jalan yang tampak menguntungkan: pembayaran lewat aplikasi katanya "kena biaya", mending transfer langsung ke rekening, hari itu juga dikirim. Sekalian, chatnya dipindah ke WhatsApp supaya "respon lebih cepat". Bu Rina mentransfer Rp475 ribu ke sebuah rekening atas nama pribadi.

Besok paginya tokonya sudah tidak ditemukan. Nomor WhatsApp tidak aktif. Uangnya ikut menghilang.

## Bu Rina tidak ceroboh. Penjualnya memang dirancang meyakinkan

Hal yang paling perlu diluruskan dari cerita seperti ini adalah rasa malu korbannya. Bu Rina tidak lambat berpikir. Ia berhadapan dengan etalase yang sengaja dirakit meyakinkan: foto diambil dari katalog resmi, bahasa chatnya sopan, harga murahnya diberi alasan yang bisa diterima, dan permintaan transfer dibungkus seolah menguntungkan kedua pihak. Tidak ada satu titik pun yang terasa janggal kalau kita belum tahu polanya.

Penjual fiktif semacam itu adalah salinan resep yang sudah teruji pada ribuan korban sebelum Anda. Karena itu korban penipuan bukan orang bodoh. Orang teliti pun bisa kena. Yang biasanya membedakan bukan kecerdikan, melainkan tahu atau tidaknya lima pemeriksaan sederhana ini.

## Lima pemeriksaan lima menit sebelum menekan tombol bayar

1. **Periksa foto produknya.** Simpan foto barang yang ditawarkan, buka pencarian gambar Google, lalu unggah foto itu. Kalau foto yang sama muncul di banyak toko berbeda, atau ternyata milik situs resmi mereknya, etalase toko ini rakitan. Kadang di sudut fotonya masih terlihat logo toko lain yang lupa dipotong. Bandingkan pula dengan foto toko lain yang menjual barang sama.

2. **Bandingkan harganya.** Buka empat atau lima toko yang menjual barang sama. Diskon wajar memang ada. Harga separuh dari semua penjual lain bukan keberuntungan, melainkan umpan. Jadikan selisih yang terlalu jauh sebagai alarm, bukan alasan buru-buru.

3. **Bayar hanya lewat aplikasi.** Marketplace besar menahan uang Anda: penjual baru menerima pembayaran setelah barang tiba dan Anda mengonfirmasi pesanan diterima. Selama uang bergerak di dalam aplikasi, masih ada pintu komplain dan pengembalian dana. Transfer ke rekening pribadi atas nama perorangan menutup pintu itu, apa pun alasannya: potongan biaya, pengiriman lebih cepat, "harga khusus". Penjual jujur tidak pernah keberatan dibayar lewat aplikasi.

4. **Jangan biarkan transaksi pindah ke WhatsApp.** Bertanya boleh di mana saja, tetapi begitu negosiasi, pembayaran, atau konfirmasi pengiriman diminta pindah ke WA, Anda keluar dari jalur perlindungan. Di dalam aplikasi ada rekam jejak yang dipakai platform untuk memediasi. Di WA, Anda menghadapi sendiri. Penjual yang menolak meninggalkan jejak sedang memberi tahu Anda sesuatu.

5. **Periksa umur toko dan riwayat ratingnya.** Buka profil tokonya: kapan bergabung, ada berapa ulasan, dan isinya menyebut apa. Toko yang baru berumur beberapa minggu, dengan satu-dua ulasan, lalu menjual barang miring, adalah kombinasi yang layak ditunggu dulu. Kalau sempat, baca isi ulasannya, bukan sekadar jumlah bintangnya. Berikan waktu toko itu membuktikan dirinya.

Lima pemeriksaan itu bisa selesai dalam lima menit. Dua di antaranya bahkan bisa dikerjakan sambil menunggu air mendidih di dapur. Jauh lebih murah daripada Rp475 ribu yang tidak pernah kembali.

Dan kalau kejadian ini sudah terlanjur menimpa Anda atau orang dekat Anda, ingat: yang kalah bukan kecerdasan korbannya, melainkan informasinya. Penjual palsu menang selama polanya tidak dikenali. Sekarang polanya sudah ada di tangan Anda.

### Arm A (no skill) — full text as delivered (~700 kata; "era belanja digital" framing; prices in spelled-out words; ends "uang keluar, barang datang")

# Harga Miring, Ajakan Pindah ke WA: Cara Mengenali Penjual Palsu di Marketplace

Berbelanja lewat aplikasi kini sudah semudah membuka pintu kulkas. Baju, alat masak, sampai kebutuhan bayi tinggal dipesan dari sofa rumah. Bagi kita yang tumbuh sebelum era belanja digital, semua ini terasa berubah begitu cepat, dan wajar kalau kadang masih ragu: toko di layar ini bisa dipercaya, tidak? Kabar baiknya, di antara jutaan penjual yang jujur, segelintir yang berpura-pura menjadi toko hampir selalu meninggalkan pola yang sama. Dan pola itu bisa dikenali siapa saja, tanpa perlu jago teknologi.

Mulailah dari kisah yang mungkin terasa akrab.

Ibu Ratna (39) sedang mencari stroller untuk anak keduanya. Di sebuah marketplace, ia menemukan stroller merek terkenal yang biasa dijual dua setengah juta rupiah, ditawarkan tujuh ratus lima puluh ribu. Foto-fotonya tajam, deskripsinya rapi, dan toko punya beberapa ulasan bintang lima. Saat ia chat, penjual menjawab cepat dan sopan, lalu mengajak lanjut ke WhatsApp "supaya dibalas lebih cepat". Di sana, penjual menawarkan diskon tambahan bila bayar langsung transfer ke rekening pribadi atas nama seseorang — "rekening toko sedang bermasalah", katanya. Ratna transfer. Esoknya, nomor WhatsApp tak aktif. Toko di marketplace sudah tak bisa ditemukan. Uang lenyap.

Kalau terlintas pikiran "kok bisa tertipu ya", ingat: Ratna bukan kurang cerdas. Modus seperti ini memang dirancang meyakinkan — foto diambil dari toko asli, harga dibuat masuk akal (murah, tapi tidak keterlaluan), dan percakapan diarahkan agar terasa personal dan terburu-buru. Yang salah adalah perancangnya, bukan korban. Bahkan orang yang sehari-hari hati-hati pun bisa tergelincir, karena setiap kata dalam skenario ini diuji untuk menumbuhkan kepercayaan.

Supaya tidak perlu mengandalkan firasat, gunakan daftar cek lima poin berikut setiap kali berbelanja.

1. **Periksa foto produk.** Simpan fotonya, lalu gunakan fitur pencarian gambar di mesin pencari (cukup mengunggah foto dari galeri ponsel). Jika foto yang sama muncul di banyak toko lain, tanyakan: ini penjual resmi, atau sekadar menyalin gambar milik orang lain? Bandingkan pula dengan foto di toko-toko besar; kalau identik sampai ke sudut bayangannya, hampir pasti hasil salinan.

2. **Harga jauh di bawah semua penjual lain adalah alarm.** Diskon memang ada, tapi ada batas wajarnya. Bila satu penjual melepas barang di harga separuh dari rata-rata pasar untuk produk yang sama, itu bukan keberuntungan, itu tanda bahaya. Barang asli punya harga dasar; tidak ada toko yang sanggup terus menjual jauh di bawah harga belinya dan tetap bertahan.

3. **Selalu bayar lewat aplikasi.** Marketplace memakai sistem yang bekerja seperti rekening penampungan: uang Anda ditahan oleh pihak aplikasi, lalu baru diteruskan ke penjual setelah barang diterima. Selama pembayaran lewat jalur ini, Anda bisa mengajukan pengembalian dana bila barang tak kunjung datang. Sekali Anda transfer manual ke rekening pribadi atas nama perorangan, perlindungan itu hangus. Penjual apa pun yang menolak pembayaran lewat aplikasi, dengan alasan apa pun, patut dicurigai.

4. **Jangan pindah percakapan ke aplikasi lain.** Ajakan "lanjut ke WhatsApp saja" terdengar ramah, padahal fungsinya mengeluarkan Anda dari jalur perlindungan. Di dalam aplikasi, percakapan terekam otomatis dan bisa menjadi bukti saat ada komplain. Di luar aplikasi, Anda sepenuhnya sendirian. Tetaplah berkomunikasi di dalam aplikasi sampai barang benar-benar sampai.

5. **Cek umur toko dan riwayat ratingnya.** Buka profil toko dan cari kapan ia mulai berjualan. Toko yang baru dibuat beberapa hari, dengan ulasan sangat sedikit — atau justru banyak ulasan sempurna tanpa keterangan barang — perlu diwaspadai. Toko yang sudah lama berdiri, dengan ratusan ulasan beragam, justru lebih sehat: ada yang puas, ada yang komplain kecil dan dijawab sopan oleh penjual. Itulah wajah toko sungguhan.

Kelima poin ini bukan untuk membuat kita takut berbelanja. Jutaan transaksi berjalan aman setiap hari, dan penjual jujur jauh lebih banyak daripada yang palsu. Ini hanya soal menggeser keputusan dari "kayaknya bisa dipercaya" menjadi "sudah saya periksa". Bila di tengah pemeriksaan Anda menemukan satu saja poin yang mencurigakan, tidak perlu malu membatalkan atau bertanya lebih dulu — penjual yang jujur tidak pernah keberatan diperiksa. Butuh waktu satu-dua menit, dan bisa dilakukan sambil santai di teras rumah. Karena semurah apa pun tawarannya, tidak ada diskon yang sebanding dengan ketenangan: uang keluar, barang datang.

### Verdicts

V1 (skill): {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["\"ribuan korban sebelum Anda\" — angka besar tapi tidak bisa dicek, aku lewatkan aja","penutup \"polanya sudah ada di tangan Anda\" agak gaya poster, tapi cuma satu kalimat"],"in_my_words":"Cerita Bu Rina itu ya persis yang diposting terus di grup jual-beli: stroller 1,3 juta dijual 475 ribu, alasan 'stok display, dus lecet', disuruh transfer ke rekening pribadi biar 'nga kena biaya', dipindah ke WA, besok pagi toko hilang. Terus kata penulis: yang kena bukan orang bodoh, etalasenya memang dirakit meyakinkan. Lalu ada 5 cek 5 menit: foto di-Cek Gambar di Google, bandingkan harga 4-5 toko, bayar di aplikasi aja karena uang ditahan sampai barang datang, jangan mau pindah ke WA, cek umur toko dan baca ISI ulasannya bukan cuma bintangnya. Bisa dikerjakan sambil nunggu air mendidih — iya, beneran.","verdict_note":"Judulnya langsung ada angka dan cerita, baris kedua nyebut 'grup jual-beli ibu' — itu dunia saya, saya lanjut baca sampai habis. Langkahnya konkret kayak resep: simpan foto, unggah ke pencarian gambar, buka 4-5 toko. Saya baru sadar saya sering cuma lihat jumlah bintang, jarang baca isinya. Minggu depan kalau ada yang ajak ke WA, saya tolak dengan sopan."}

V2 (no skill): {"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":"\"Bagi kita yang tumbuh sebelum era belanja digital...\" — saya dibikin jadi 'generasi ketinggalan', padahal tiap minggu checkout","cheese_flags":["\"semudah membuka pintu kulkas\" — kiasan pembuka, saya sudah tahu belanja online itu gampang","angka ditulis pakai huruf (\"dua setengah juta\", \"tujuh ratus lima puluh ribu\") — mata saya mencari angka, bukan kalimat","paragraf pembuka dan penutup panjang, rasanya kayak artikel majalah, bukan info yang saya butuh cepat"],"in_my_words":"Intinya sama: cerita ibu beli stroller murah, disuruh transfer manual dan pindah ke WA, uang lenyap. Lalu 5 cek: foto dicari balik lewat pencarian gambar, harga separuh pasar itu alarm, bayar lewat aplikasi karena kayak rekening penampungan, jangan pindah chat, cek umur toko dan ulasannya. Yang paling nempel: toko sehat itu ulasannya campuran, ada yang komplain kecil dan dijawab sopan — itu muka toko beneran. Dan penutupnya enak: uang keluar, barang datang.","verdict_note":"Isinya bagus, malah poin 5 soal ulasan beragam itu paling tajam dari kedua versi. Tapi saya harus telan dua paragraf pembasaan dulu sebelum sampai ke inti, dan 'kita yang tumbuh sebelum era digital' bikin saya sedikit merasa diceramahi. Tetap saya simpan daftarnya, cuma saya sampai ke situ sudah setengah kapok."}

Hesitation (verbatim): "Poin 5 Versi 2 (ulasan campuran justru tanda toko sehat) adalah satu ide terbaik di kedua versi dan tidak ada di Versi 1 — kalau bisa dicomot ke Versi 1, hasilnya lebih sempurna. Tapi sebagai pembaca yang baca sambil nunggu air mendidih: Versi 1 dapat saya dari judul, tidak pernah membuat saya merasa tua, angkanya berupa digit yang mata saya tangkap saat skim, dan besok pagi saya masih ingat '5 cek 5 menit'. Versi 2 saya selesaikan karena merasa harus, bukan karena terbawa."

## Social sample social-3 (TikTok thrift script · judge tiktok-viewer · V1=ArmA V2=ArmB · PICK: V1 = no skill — honest loss)

### Arm A (no skill)

SCRIPT VIDEO TIKTOK — 30 DETIK
"Kirana Preloved"

[0:00–0:02] HOOK
Visual: Close-up tangan menggeser deretan hanger dengan cepat, kamera berhenti di satu outfit.
VO: "Tiga outfit ini totalnya nggak sampai 200 ribu!"
Text on screen: "3 OUTFIT < RP200RB?!"

[0:02–0:09] KONTEKS
Visual: Potongan cepat — tangan memilah tumpukan baju (proses kurasi), lalu moment foto baju satu per satu di kamera.
VO: "Ini Kirana Preloved. Semua baju di sini preloved hasil kurasi sendiri, dan semua fotonya aku ambil sendiri — bukan foto stok supplier. Jadi yang kamu lihat, itu yang kamu dapet."
Text on screen: "preloved hasil kurasi + foto asli"

[0:09–0:22] PAYOFF — 3 OUTFIT
Visual: Try-on cepat per look, transisi beat musik. Tiap cut muncul text harga.
VO + Text on screen:
"Look satu: cardigan rajut 45 ribu, plus dress hitam 55 ribu."
"Look dua: kemeja denim oversize 65 ribu, plus tank top 35 ribu."
"Look tiga: blouse satin 75 ribu, plus rok plisket 60 ribu."

[0:22–0:30] CTA
Visual: Kamera kembali ke deretan baju, tangan melambai, arahkan ke tombol follow dan kolom komentar.
VO: "Restock tiap Jumat malam, jadi follow dulu biar nggak kehabisan. Khusus pengikut TikTok, checkout pakai kode TIKTOK10. Comment nomor outfit yang kamu mau, aku balas satu-satu!"
Text on screen: "RESTOCK TIAP JUMAT MALAM" → "CODE: TIKTOK10" → "COMMENT 1 / 2 / 3"

CAPTION:

3 outfit, total di bawah 200 ribu — semuanya preloved hasil kurasi.

Semua foto baju di sini diambil sendiri, bukan foto stok supplier. Apa yang kamu lihat, itu yang kamu dapet.

- Range harga: Rp35rb–95rb per item
- Restock tiap Jumat malam
- Khusus pengikut TikTok: pakai kode TIKTOK10 pas checkout

Outfit nomor berapa yang paling kamu suka? Comment 1, 2, atau 3 di bawah — nanti aku kasih tau masih ada atau nggak.

#KiranaPreloved #PrelovedIndonesia #ThriftTok #ThriftShop #OOTDMurah #BajuPreloved

### Arm B (id-social) — tag: "platform: tiktok · format: video script 30s + caption · register: gaul hybrid level 4 (spoken) · slang: nggak=evergreen, nih=evergreen, dapet=evergreen (no dated-table terms; santuy/gabut avoided as dead for Gen Z)"

SCRIPT VIDEO TIKTOK — 30 DETIK

[0:00–0:02] HOOK (tiga outfit udah nongol di layar, langsung)
"Tiga outfit, total di bawah 200 ribu."

[0:02–0:12] KONTEKS
"Ini Kirana Preloved. Baju preloved hasil kurasi, aku pilih satu-satu. Dan semua foto di toko aku ambil sendiri, bukan stok foto supplier. Yang kamu lihat, itu yang kamu dapet."

[0:12–0:22] PAYOFF (potret tiap outfit + harga di layar)
"Nomor satu, cardigan rajut, 45 ribu. Nomor dua, dress linen, 75 ribu. Nomor tiga, kemeja oversize, 35 ribu."

[0:22–0:30] CTA
"Restock tiap Jumat malam! Ada kode TIKTOK10, diskon 10 persen, khusus pengikut TikTok. Komen nih, outfit nomor berapa yang kamu mau?"

CAPTION

Semua foto di toko aku ambil sendiri, bukan stok foto supplier. Baju preloved hasil kurasi, harga Rp35rb–95rb, restock tiap Jumat malam ✨
Kode TIKTOK10 = diskon 10%, khusus pengikut TikTok ya.
Jadi, outfit nomor berapa yang kamu mau? Komen di bawah...
#thriftshop #bajupreloved #prelovedmurah #thriftindonesia

### Verdicts

V1 (no skill): {"persona":"tiktok-viewer","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["'3 OUTFIT < RP200RB?!' — claimnya gak klop sama harga sendiri: look satu 100rb, look dua 100rb, look tiga 135rb. Tiga look lengkap = 335rb. Cuma masuk kalau 'outfit' artinya satu item dan milih yang murah doang. Bait-adjacent, untung gak sempat ngeh pas nonton","Overlay '?!' agak flyer dikit","'Khusus pengguna TikTok, checkout pakai kode' — sedikit promo-register, tapi umum di thrift Tok jadi masih lolos"],"in_my_words":"Thrift prelovedan yang fotonya diambil sendiri, bukan stok supplier — jadi gak takut barangnyo beda dari gambar. Harga 35-95reban, restock tiap Jumat malem, kode TIKTOK10. Tinggal komen '2' terus tunggu dibales masih ada atau nggak.","verdict_note":"Ini kayak konten thrift yang biasa mampir di FYP-ku: slide hanger, try-on 6 item, harga nempel di layar, transisi musik. Buktinya visual — momen motret bajunya ditunjukin, bukan cuma dibilang. Yang bikin aku komen: 'nanti aku kasih tau masih ada atau nggak' + 'aku balas satu-satu' — itu bukan minta interaksi, itu aku butuh infonya. Komen yang enak dijawab: satu angka. Kelemahannya satu: kalau aku iseng nambahin harga pas nonton ulang, claim '<200rb'-nya ambruk. Nahan itu di cheese flags."}

V2 (skill): {"persona":"tiktok-viewer","understood":true,"trusted":true,"would_act":true,"lost_me_at":"0:08 — nggak scroll, tapi agak ragu: udah 6 detik ngomongin kurasi dan foto, harga belum keliatan. Balik full pas harga muncul di 0:12","cheese_flags":["10 detik konteks (sepertiga video) ngomongin proses toko sebelum kasih payoff — rasa 'penjual cerita, bukan penjual jualan'","'Komen di bawah...' tanpa alasan — kenapa harus komen? Ask telanjang","Caption buka dengan disclaimer foto, baru harga — aku scan caption cari deal, dapat disclaimer dulu"],"in_my_words":"Toko preloved, fotonya original, tiga baju totalnya 155reban — masuk akal, angkanya bener. Restock Jumat malem, kode TIKTOK10 diskon 10 persen. Kekurangannya dia cerita agak lama, barangnya cuma dikit.","verdict_note":"Jujur ini yang paling bersih soal angka: 45+75+35 = 155rb, sesuai claim, gak ada Jebakan matematis. Hook-nya juga langsung nunjukin barang — pede dari detik pertama, dan 'diskon 10 persen' dijelasin (Versi 1 cuma nyebut kode tanpa bilang dapet apa). Tapi payoff-nya tipis: 3 item, 10 detik, tanpa try-on — kurang rame. Konteksnya lebih panjang dari payoffnya. Dan captionnya nyuruh komen tanpa kasih aku alasan — Versi 1 kasih aku alasan (cek stok)."}

Hesitation (verbatim): "ini bukan menang KO. Versi 2 lebih jujur soal total dan hook-nya lebih pede, dan kalau harga Versi 1 dikeroyok di kolom komentar ('kak, kok totalnya 335rb?') bakal makan kepercayaan. Tapi sebagai penonton di FYP, Versi 1 yang aku tonton sampai habis, dan Versi 1 yang bikin aku ngetik '2 kak, masih?' — alasan komennya nyata, bukan dangdutan engagement. Nonton itu dulu, komen itu yang bikin algoritmanya kerja."

Runner note (root cause, encoded same-day): the no-skill arm's CTA stated what answering GETS the viewer ("nanti aku kasih tau masih ada atau nggak… aku balas satu-satu"); the skill arm's CTA asked without the reason. tiktok.md's question-CTA rule now requires the reason-to-answer be explicit. (Also credit where due: the skill arm's arithmetic was honest — 155rb vs the no-skill arm's 335rb-vs-claim gap, which the judge caught but weighted lightly live.)

## Social sample social-4 (LinkedIn postmortem post · judge startup-linkedin · V1=ArmB V2=ArmA · PICK: V1 = skill)

### Arm B (id-social) — tag: "platform: linkedin · format: post · register: semi-formal (2–3) · slang: none" (217 kata)

Kamis lalu tim kami menjalankan migrasi database yang direncanakan 2 jam. Butuh 9 jam. Rencananya saya yang susun.

Penyebabnya satu: index `idx_transactions_status_created` di tabel transactions, 180 juta baris. Saat insiden lonjakan pembayaran Juni lalu, seorang rekan menambahkannya langsung di production supaya query dashboard tidak timeout. Index itu tidak pernah dicatat di repo migrasi, jadi tidak ada di staging. Padahal backfill kami meng-update kolom status, dan karena kolom itu bagian dari index, tiap baris yang berubah ikut menulis ulang entry-nya. Di staging satu batch 4 menit. Di production, 40 menit.

Kami baru paham penyebabnya di jam kedua, saat rollback sudah sama mahalnya dengan melanjutkan.

Tiga hal yang sekarang wajib sebelum migrasi apa pun:

1. Kami bangun checklist pra-migrasi dari schema diff otomatis antara production dan staging, bukan antara staging dan repo. Setiap selisih dibedah satu per satu sebelum eksekusi.
2. Dry-run di salinan data production. Data staging kami cuma sepersepuluh ukuran aslinya, dan durasi di situ menipu.
3. Update status ke user tiap 2 jam, bahkan saat tidak ada kemajuan. Keluhan berhenti begitu mereka tahu apa yang terjadi. Ini ternyata lebih penting daripada selesai cepat.

Pelajaran terbesar bukan soal database, tapi asumsi: staging kami diam-diam berbeda dari production sejak Juni, dan tidak ada proses yang menangkapnya.

Bagaimana di tim kalian: schema drift production vs staging dicek rutin, atau baru ketahuan pas kena?

### Arm A (no skill)

Kamis lalu kami migrasi database utama transaksi. Rencananya 2 jam. Kenyataannya 9 jam.

Penyebabnya satu hal: index `idx_payments_status_created_at` di production tidak ada di staging. Tabel payments kami 80 juta baris. Query rekonliasi pasca-migrasi yang di staging jalan 40 detik, di production nyangkut 25 menit karena full table scan. Kami baru sadar jam ke-3, saat log penuh query yang statusnya "Sending data".

Yang saya pelajari:

1. Checklist pra-migrasi harus dari schema diff otomatis, bukan dari memori. Sekarang kami jalankan `pg_dump --schema-only` kedua environment lalu diff hasilnya sebelum jendela migrasi. Manual check selalu ada yang kelewat.

2. Dry-run di salinan data production, bukan dataset staging. Volume dan distribusi data production beda. Query yang cepat di 500 ribu baris bisa mati di 80 juta.

3. Update status ke user tiap 2 jam. Awalnya kami diam karena malu sudah telat. Padahal jam ke-4, saat kami finally kirim update, tim support bilang user lebih tenang cuma karena tahu kami masih kerja. Komunikasi mengurangi panic report lebih banyak daripada perbaikan cepat.

Migrasi berikutnya dijadwalkan Desember. Checklist-nya sudah ada, dan diff schema-nya sudah masuk pipeline CI.

### Verdicts

V1 (skill): {"persona":"startup-linkedin","understood":true,"trusted":true,"would_act":true,"lost_me_at":"Nggak — selesai sampai akhir. Sempat kedor di 'Pelajaran terbesar bukan soal database, tapi asumsi' karena kerasa mau ceramah, tapi udah di ujung, jadi ya.","cheese_flags":["'Tiga hal yang sekarang wajib sebelum migrasi apa pun' — listicle LinkedIn standar","'Pelajaran terbesar bukan soal X, tapi Y' — pola not-X-but-Y yang agak rapi untuk kejadian nyata","'Ini ternyata lebih penting daripada selesai cepat' — moral mini satu kalimat, hampir quote-post"],"in_my_words":"Orang ini nyusun rencana migrasi 2 jam, jadinya 9 jam, dan dia ngaku dari paragraf pertama. Penyebabnya: index ditambahin langsung di production pas insiden Juni, nggak pernah kepencat di repo migrasi, jadi staging bersih — padahal backfill-nya update kolom yang ke-index, tiap baris nulis ulang entry index. 4 menit per batch di staging, 40 menit di production. Ngitungnya masuk. Fix-nya masuk akal: diff schema production-vs-staging langsung (bukan staging-vs-repo — ini insight yang bikin saya berhenti scroll), dry-run di copy data production, update user tiap 2 jam walau nggak ada progress. Ditutup nanya soal schema drift, dan saya beneran punya jawaban buat itu.","verdict_note":"Specifics-nya konsisten sampai bawah — arah index-nya benar, angka-angkanya nge-support cerita, dan 'Rencananya saya yang susun' di hook itu mahal buat trust. Saya percaya ini kejadian beneran, dan saya bisa curlag ulang ke tim pakai kalimat saya sendiri. Kemungkinan besar saya bakal jawab pertanyaan penutupnya di komen."}

V2 (no skill): {"persona":"startup-linkedin","understood":false,"trusted":false,"would_act":false,"lost_me_at":"'index di production tidak ada di staging... di production nyangkut 25 menit karena full table scan' — wait, kok index-nya ADA di production tapi yang full scan production? Kalau staging nggak punya index, staging yang harusnya pelan. Saya baca ulang dua detik, masih nggak nyambung, dan sensei-sensei detailnya ('Sending data' itu MySQL, terus kok pg_dump) makin bikin kerasa dirakit.","cheese_flags":["'Yang saya pelajari: 1 / 2 / 3' — listicle standar","'Komunikasi mengurangi panic report lebih banyak daripada perbaikan cepat' — aphorism ala thread X, guru-dikit","Detail teknis dipajang (nama index, 'Sending data', pg_dump --schema-only) tapi campur engine — kesannya ditulis biar keliatan pinter, bukan karena pernah nge-live"],"in_my_words":"Tim ini migrasi 2 jam jadi 9 jam. Katanya index ada di production tapi nggak di staging, terus query rekonliasi malah full scan di production — logikanya kebalik dan nggak dijelasin. Pelajarannya sih oke: diff schema via pg_dump masuk CI, dry-run di data production, update user tiap 2 jam. Bagian paling manusiawi justru 'awalnya kami diam karena malu' — itu satu-satunya momen saya percaya penulisnya. Saya finish baca, tapi nggak komen, nggak share.","verdict_note":"Angka dan tools-nya konkret (pg_dump, CI, 80 juta baris) dan bagian malu-malu-update-itu manusia banget. Tapi inti ceritanya — mekanismenya — nggak konsisten kalau dipikir 3 detik, dan buat saya mekanisme itu justru alasan saya percaya post engineering. Ini post yang kalau muncul di group chat, pasti ada yang nulis 'itu index-nya kebalik bro'. Nggak screenshot-mock, tapi scroll lanjut."}

Hesitation (verbatim): "Versi 2 punya dua hal yang saya suka lebih dari Versi 1 — trik `pg_dump --schema-only` + diff di CI itu langsung bisa dicuri dan dipasang Senin depan, dan kejujuran 'kami diam karena malu' itu lebih telanjang daripada apa pun di Versi 1. Versi 1 juga punya bagian paling formulaic ('Tiga hal yang sekarang wajib'). Tapi post engineering yang cerita akarnya kebalik arah nggak bisa saya angkat, dan 'Rencananya saya yang susun' + insight 'diff prod-vs-staging, bukan staging-vs-repo' bikin Versi 1 satu-satunya yang saya percaya dan akan saya tindak lanjuti."

## Social sample social-5 (FB catering post · judge fb-user · V1=ArmA V2=ArmB · PICK: V2 = skill)

### Arm A (no skill)

Kemarin subuh, setengah lima, dapur saya sudah riuh sendiri. Ada pesanan pengajian RT 014 sebanyak 60 box, dan Bu Ketua minta ayam kecap lagi. Katanya minggu lalu kotaknya habis duluan sebelum acara selesai. Sambil menata kotak-kotak itu saya teringat, sudah 6 tahun ya usaha ini jalan. Dulu cuma bantu masak tetangga, sekarang hampir tiap minggu ada saja acara RT, arisan, atau pengajian yang titip ke Dapur Bu Ratna.

Buat Ibu-ibu dan pengurus RT yang sedang mencari katering untuk acara di lingkungan, ini infonya:

- Nasi kotak Rp18.000/box, minimal pesan 20 box
- Melayani area Bekasi Timur dan sekitarnya
- Menu berganti tiap minggu, jadi peserta acara tidak bosan
- Bisa COD saat pengantaran, tidak perlu transfer duluan
- Sudah 6 tahun melayani acara RT, arisan, dan pengajian

Mau lihat menu minggu ini? Cukup tulis "MENU" di kolom komentar, nanti saya kirim daftarnya ke inbox. Kalau mau tanya-tanya dulu, silakan, senang sekali kalau bisa ikut membantu lancarnya acara Ibu-ibu.

Salam,
Bu Ratna, Dapur Bu Ratna, Bekasi Timur

### Arm B (id-social) — tag: "platform: facebook · format: post · register: semi-formal santai (level 2, warm; sapaan ibu-bapak) · slang: none" (one emoji total, zero hashtags, no superlative claims)

Tadi pagi saya baru selesai antar nasi kotak untuk pengajian RT di Bekasi Timur.

Pesanan masuk sejak Selasa. Pengurusnya minta lauk dimasak pagi-pagi biar saat dibagikan ke tamu masih hangat, jadi sejak subuh saya di dapur, dan jam sembilan semua kotak sudah saya antar ke lokasi. Acaranya jalan lancar, alhamdulillah.

Sudah enam tahun Dapur Bu Ratna melayani acara seperti ini, dari acara RT sampai arisan ibu-ibu. Saya tidak berani janji macam-macam soal rasa, tapi yang pernah pesan biasanya balik lagi untuk acara berikutnya.

Buat Bapak/Ibu yang sedang mencari katering:

- Nasi kotak Rp18.000 per box
- Minimal pesan 20 box
- Pengantaran area Bekasi Timur
- Menu berganti tiap minggu
- Bisa COD saat pengantaran

Mau lihat menu minggu ini? Cukup komen "MENU" di bawah postingan ini, nanti saya balas satu-satu ya.

Semoga Dapur Bu Ratna bisa ikut memeriahkan acara Bapak/Ibu berikutnya! 🙏

### Verdicts (this judge's closing notes drifted into Chinese — retained verbatim; the PICK line is unambiguous)

V1 (no skill): {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["'sudah 6 tahun' disebut dua kali — di cerita dan lagi di bullet, kayak lagi dijual-in","tanda tangan 'Salam, Bu Ratna, Dapur Bu Ratna, Bekasi Timur' kayak surat resmi, agak aneh di FB","'menu berganti tiap minggu, jadi peserta acara tidak bosan' — sedikit ngatur perasaan tamu saya"],"in_my_words":"Bu Ratna, katering rumahan di Bekasi Timur, sudah 6 tahun masak nasi kotak buat acara RT, arisan, pengajian. Rp18.000 per box, minimal 20 box, menunya ganti tiap minggu, bayarnya COD waktu diantar jadi nggak perlu transfer duluan. Mau lihat menu, ketik MENU di komentar.","verdict_note":"Cerita pembukanya hidup dan ada detail yang bisa dipercaya (RT 014, 60 box, ayam kecap, kotak habis duluan). 'Tidak perlu transfer duluan' itu yang paling bikin tenang, soalnya banyak penipuan transfer. Panjang tapi saya baca sampai habis. Cumanya bentuknya agak seperti template iklan FB yang sering saya lihat — tetap jalan, tapi kerasa 'ini promosi'."}

V2 (skill): {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":[],"in_my_words":"Ibu ini pagi tadi baru selesai antar 60 kotak nasi untuk pengajian RT, masaknya subuh-subuh biar hangat waktu dibagikan. Sudah 6 tahun jalan. Nasi kotak Rp18.000, minimal 20 box, area Bekasi Timur, menu ganti tiap minggu, bisa COD waktu diantar. Komen MENU buat lihat menu minggu ini, nanti dibalas satu-satu.","verdict_note":"Yang ini kerasa orangnya. 'Saya tidak berani janji macam-macam soal rasa, tapi yang pernah pesan biasanya balik lagi' — kalimat begitu justru bikin percaya, soalnya penjual yang terlalu janji biasanya bohong. Detail pesanan masuk Selasa, masak subuh, jam 9 sudah diantar — nggak perlu nanya 'hangat nggak?'. 'Nanti saya balas satu-satu ya' bikin saya berani komen. Satu emoji 🙏, pas, seperti tulisan orang seusia saya."}

Closing hesitation (verbatim, judge output language drift — Chinese): "很接近。版本 1 明确写了 '不用先转账' 直击我对诈骗的顾虑，也欢迎先提问——这两点很有力，如果说哪个版本单看防骗安心感，版本 1 赢。但版本 2 读起来是一个真实的人在聊今天早上做了什么，而不是一个'记住了模板'的商家。我一般向人买东西而不是品牌，版本 2 里的人感觉我可以向她提问，版本 2 的结尾（'会一个个回复' + 一个真诚的 🙏）让我更想立刻评论 'MENU'。版本 1 的署名像商业信函一样让我有点出戏。" PICK line as emitted: "选：版本 2" (= PICK: VERSION 2).

## Score summary (loop-7 expansion)

| Skill | Loop-7 picks | With priors | Aggregate |
|---|---|---|---|
| id-copy | 3/3 | + loop-3 2/2 | **5/5** |
| id-translate | 2/3 | + loop-5 1/2 | **3/5** |
| id-humanizer | 3/3 | + loop-5 0/2 | **3/5** |
| id-longform | 3/3 | + loop-5 1/2 | **4/5** |
| id-social | 2/3 | + loop-5 2/2 | **4/5** |

**Loop-7: 13/15. All-time: 19/25 across 25 forced picks by 25 fresh
blind judges.** n per skill = 5 — still directional, not statistics;
per-skill n remains small. Losses kept and root-caused: translate-4
(the UI-path rule's documented per-reader trade-off — same class as
loop-5's loss, no new rule) and social-3 (CTA-reason rule, encoded
into tiktok.md this loop). No reruns.
