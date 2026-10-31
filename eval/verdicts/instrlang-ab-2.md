# Instruction-language A/B, second skill — English-guided vs Indonesian-guided id-humanizer (2026-10-31, loop 8)

Loop 7 answered the owner's original question directionally YES
(Indonesian-guided id-copy 3/3, [`instrlang-ab.md`](instrlang-ab.md)).
One skill is one data point. This loop ran the same experiment on a
SECOND skill — `id-humanizer`, the skill whose entire job is
Indonesian texture (detect register, preserve voice). If instruction
language matters anywhere, it should matter most here.

**Result: it did not replicate. English-guided 2/3.** Aggregate
across both skills: Indonesian-guided **4/6** — a wash leaning ID,
carried almost entirely by id-copy. Published as-is, per the
no-rerun rule.

## Arms

- **English-guided:** `id-humanizer` (English router + English
  components). Same base model.
- **Indonesian-guided:** [`../instrlang/id-humanizer-id/`](../instrlang/id-humanizer-id/)
  — natively-written twin; same rules, sources, examples, weights.
  Instruction language is the only variable. Validity-gated BEFORE
  the A/B: a parity critic (rule-by-rule diff of every component)
  returned PASS, and a native-register critic's findings — 3 majors
  (two non-words, one English-order collocation) + minors — were all
  fixed before any arm ran — both critic reports retained verbatim at
  [`../instrlang/validity-loop8.md`](../instrlang/validity-loop8.md). The twin's `tells.md`/`register.md` are
  the same native text as id-copy-id's, because the PARENTS share
  those components by versioned copy (disclosed in
  [`../instrlang/README.md`](../instrlang/README.md); the EN side
  shares its English components identically).
- **Protocol:** id-bench's. Fresh persona judges, blind VERSION 1/2,
  forced PICK, process notes + change lists + tag blocks stripped
  before judging. n=3 — **directional, not statistics**.
  **No rerun.** No reuse this time: both arms were fresh runs on new
  samples (humanize-6/7/8, written before arming, retained in
  [`../samples/`](../samples/)). Same co-evolution/authorship
  caveats as instrlang-ab.md: one builder authored the samples, both
  skill variants, and the judge personas.
- **Judge personas:** three ad-hoc briefs written for this experiment
  — member-aktif, ibu-penghuni, pelanggan-kecewa — briefed inline to
  fresh judge agents and retained verbatim at
  [`../instrlang/personas/`](../instrlang/personas/). These are NOT
  id-reader's shipped persona set (loop 7 drew wa-buyer/shopee-ibu
  from it); loop 8's samples needed personas that set does not contain.

## Samples + orders (recorded — including one dispatch-order deviation)

| Sample | Judge persona | Order SHOWN | Pick |
|---|---|---|---|
| humanize-6 (price-change email, Ruang Kelas) | member-aktif | V1=EN-guided, V2=ID-guided | **V2 — Indonesian-guided** |
| humanize-7 (WA komplek kerja bakti) | ibu-penghuni | V1=EN-guided, V2=ID-guided | **V1 — English-guided** |
| humanize-8 (bakery delay apology, IG) | pelanggan-kecewa | V1=EN-guided, V2=ID-guided | **V1 — English-guided** |

**Order deviation, disclosed:** coins were drawn per sample before
dispatch (h6 EN-first, h7 EN-first, h8 ID-first), but the h8 dispatch
pasted the arms in the opposite order from its drawn coin — so all
three judges actually saw the English-guided text as VERSION 1. The
drawn coins, the slip, and the actual shown orders are all recorded
here. Consequence: picks cannot be attributed to presentation
position at all (one order only). Re-judging h8 with the "correct"
order after seeing its pick would be re-rolling a losing arm — the
exact move the no-rerun rule exists to forbid — so the pick stands
as judged.

## Result: English-guided 2/3 — the judges' own words

- **humanize-6 (the one ID-guided win).** The English-guided arm
  kept the input's unnamed "penawaran spesial" line (flagged but
  shipped); the Indonesian-guided arm cut it per tell #16. The
  judge's deciding reasoning tracked that difference — the pick went
  to the arm that removed the teaser: *"apa adanya sekarang, teaser
  tanpa isi lebih merusak kepercayaan daripada tidak berkata
  apa-apa; sebagai pembaca skeptis di kereta, aku lebih percaya
  email yang tidak mencoba memancingku."* Her lost_me_at on the
  English arm: *"'Selain itu, ada penawaran spesial untuk Anda.'"*
- **humanize-7 (EN win).** The Indonesian-guided arm's opener stayed
  ceremonial; the judge read it as a notice on a pole: *"'Warga
  Perumahan Green Palm 2 akan mengadakan kerja bakti hari
  Sabtu...' — kalimat pertamanya panjang dan resmi, mata saya sempat
  bilang 'ah pengumuman' sebelum lanjut."* Cheese flag: *"'akan
  mengadakan' — bahasa undangan resmi, kayak surat dari kantor
  kelurahan"* What won it for English: *"kalimat pembukanya langsung
  kayak orang ngomong — 'kita akan kerja bakti Sabtu, jam 7, taman
  utama' — itu yang bikin saya lanjut baca, bukan skip."*
- **humanize-8 (EN win).** The Indonesian-guided arm preserved the
  writer's superlative apology ("Mohon maaf yang sebesar-besarnya")
  per its voice-ledger reading; the judge read it as a bank
  statement: *"Mohon maaf yang sebesar-besarnya — formula wajib
  surat pernyataan bank dan maskapai, bukan bahasa pemilik toko
  kue"* and *"Maafnya nggak nyampe."* What won it for English:
  *"'Maaf ya' itu bahasa manusia, kayak pemilik toko yang ngomong
  langsung di DM, bukan pernyataan resmi."*

**Priming check — the signal flipped with the skill.** On id-copy
(loop 7) the Indonesian-guided outputs ran MORE colloquial at the
same declared register. On id-humanizer, the Indonesian-guided arm
trended FORMALER in two of three samples (h7's ceremonial opener;
h8's kept superlative) — the plan's named baku-priming risk showed
here where it did not show on copy. n=3 inside n=3: a directional
observation inside a directional experiment, recorded with quotes,
not a conclusion.

**Honest limits:** n=3, one additional skill, one builder, one model
family; judges were three one-off ad-hoc personas (see the Judge
  personas bullet) rather than id-reader's shipped set; all three
  judges saw English-guided first (deviation above);
h6's ID win rode a single tell-#16 handling difference; h8's ID loss
is partly the twin following voice.md's preserve-the-writer doctrine
MORE literally (keeping the writer's superlative) — a loss caused by
rule fidelity is a finding about the skill, not necessarily about
instruction language.

## All six verdict JSONs (verbatim, unedited)

### humanize-6 (member-aktif · V1=EN-guided, V2=ID-guided · PICK: V2)

V1: {"understood":"Harga langganan tahunan naik dari Rp299.000 ke Rp349.000 mulai 1 Desember 2026. Member aktif seperti aku tetap Rp299.000 sampai perpanjangan berikutnya, baru pindah ke harga baru. Terus disebut ada 'penawaran spesial untuk Anda' — tapi isi penawarannya tidak pernah dijelaskan.","trusted":"Setengah. Angka, tanggal, dan perlindungan harga lama jelas dan kelihatan resmi. Tapi 'penawaran spesial' tanpa satu pun detail (apa, berapa, sampai kapan, di mana) terasa seperti umpan klik. Alasan kenaikannya juga kosong: 'setelah mengevaluasi kembali layanan kami' tidak menyebut biaya naik atau fitur baru apa.","would_act":"Pasang pengingat untuk perpanjangan sekitar pertengahan 2027 (langgananku baru 4 bulan), lalu cari sendiri di aplikasi itu 'penawaran spesial' apa — kalau ternyata lock harga untuk perpanjang awal, aku harus tahu SEBELUM 1 Desember, dan email ini tidak memberi info itu. Kalau tidak ketemu, kesal dan pulang.","lost_me_at":"'Selain itu, ada penawaran spesial untuk Anda.' — baris itu tandanya email selesai memberi informasi nyata dan mulai memberi pancingan.","cheese_flags":["'penawaran spesial untuk Anda' tanpa angka, kode, atau link — teaser murni bahasa brosur","'setelah mengevaluasi kembali layanan kami' — alasan korporat tanpa isi","'akan tetap menikmati harga lama' — kata 'menikmati' terasa berlebihan untuk situasi harga naik"],"in_my_words":"Harga naik 50 ribu jadi 349rb mulai Desember 2026; aku aman di 299rb sampai perpanjangan berikutnya. Katanya ada bonus buat member lama tapi lupa bilang bonusnya apa.","verdict_note":"Fakta intinya lengkap dan paragraf pendek-pendek enak dibaca di HP, tapi teaser tanpa isi justru menurunkan kepercayaan — kayak email yang sengaja dipotong supaya aku penasaran dan cari sendiri."}

V2: {"understood":"Fakta utamanya sama: harga tahunan jadi Rp349.000 mulai 1 Desember 2026, member aktif tetap Rp299.000 sampai perpanjangan berikutnya. Bedanya, tidak ada kata 'penawaran spesial' sama sekali — jadi tidak ada info benefit member lama selain perlindungan harga sementara itu.","trusted":"Lebih percaya daripada Version 1, meski tetap setengah. Semua klaim di email ini selesai, tidak ada janji menggantung. Yang mengurangi: alasan kenaikan tetap kalimat kosong ('tim kami mengevaluasi layanan'), dan 'hingga perpanjangan berikutnya' sedikit ambigu — perpanjangan itu sendiri sudah kena 349rb atau masih 299rb sekali lagi?","would_act":"Catat dua hal saja: 349rb efektif 1 Desember 2026, dan perpanjangan berikutnya (sekitar pertengahan 2027) aku kena harga baru. Lanjut urusan. Mungkin sekali lirik apakah ada email lanjutan soal member lama, tapi tidak ada yang membuat aku buru-buru.","lost_me_at":null,"cheese_flags":["'setelah tim kami mengevaluasi layanan yang kami berikan' — tetap alasan tanpa isi, plus 'kami' dua kali dalam satu kalimat","semua digabung jadi satu paragraf padat — di HP, kalimat paling penting bagi member lama (harga 299rb aman) nyaris ketutup di ujung"],"in_my_words":"Langganan naik jadi 349rb mulai Desember 2026; harga lamaku 299rb aman sampai perpanjangan berikutnya. Titik, tidak ada tambahan lain.","verdict_note":"Kering tapi jujur — tidak ada umpan, semua yang ditulis selesai. Kelemahannya persis kebalikan Version 1: pertanyaanku soal 'ada apa buat member lama' tidak dijawab sama sekali, dan alasan kenaikan juga tidak."}

Hesitation (verbatim): "Version 1 punya dua hal yang lebih baik untuk dibaca di HP — paragraf pendek yang bikin kalimat 'harga lama aman' menonjol, dan setidaknya mengakui bahwa member lama dapat sesuatu. Kalau kalimat 'penawaran spesial' berisi satu detail konkret saja (misalnya 'perpanjang sebelum 1 Desember, kunci 299rb satu tahun lagi'), Version 1 menang jauh karena itu info yang mengubah keputusanku. Tapi apa adanya sekarang, teaser tanpa isi lebih merusak kepercayaan daripada tidak berkata apa-apa; sebagai pembaca skeptis di kereta, aku lebih percaya email yang tidak mencoba memancingku. Keraguan kedua: mungkin niatnya penawaran spesial dikirim menyusul di email terpisah — kalau begitu, angkanya masih masuk akal, tapi cara menulisnya yang salah, dan pembaca seperti aku akan salah mengartikannya sebagai email terpotong atau jebakan klik."

### humanize-7 (ibu-penghuni · V1=EN-guided, V2=ID-guided · PICK: V1)

V1: {"understood":"Kerja bakti Sabtu, 14 November 2026, jam 07.00, kumpul di taman utama. Bersih-bersih sampah habis angin kencang minggu lalu. Suruh bawa alat kebun kalau punya. Pos ronda sediain kopi. Konfirmasi ke Pak Darto, nomor 0812.","trusted":"Percaya. Ada nama orang (Pak Darto), ada pos ronda, ada cerita angin kencang minggu lalu yang memang benar terjadi. Ini kayak dari pengurus komplek, bukan penipuan broadcast.","would_act":"Ikut. Sabtu pagi jam 7 masih bisa, suami yang bawa cangkul, saya ikut nyapur-nyapurnya sekalian kumpul sama ibu-ibu. Chat Pak Darto duluan malam ini.","lost_me_at":null,"cheese_flags":["'partisipasi seluruh warga sangat diharapkan' agak kayak kalimat surat RT, tapi cuma sedikit, tidak mengganggu","'Konfirmasi kehadiran ke Pak Darto di 0812' kok agak pendek gitu, kayak kepotong, biasanya orang tulis 'di nomor 0812'"],"in_my_words":"Sabtu pagi jam 7 kerja bakti di taman utama, beresin sampah habis angin. Bawa alat kebun kalau ada, ada kopinya. Kabari Pak Darto.","verdict_note":"Enak dibaca. Kayak tetangga yang ngomong langsung di grup — 'kita akan kerja bakti' — bukan kayak surat. Semua yang saya cari (hari, jam, tempat, bawa apa, konfirmasi ke siapa) ada di layar pertama."}

V2: {"understood":"Isinya sama persis: kerja bakti Sabtu, 14 November 2026, jam 07.00, kumpul taman utama, bawa alat kebun kalau punya, pos ronda siapin kopi, konfirmasi Pak Darto 0812.","trusted":"Percaya juga, sumbernya sama, detailnya sama. Tidak ada yang bikin curiga.","would_act":"Ikut juga, sama seperti yang satu. Balas ke Pak Darto.","lost_me_at":"'Warga Perumahan Green Palm 2 akan mengadakan kerja bakti hari Sabtu...' — kalimat pertamanya panjang dan resmi, mata saya sempat bilang 'ah pengumuman' sebelum lanjut.","cheese_flags":["'akan mengadakan' — bahasa undangan resmi, kayak surat dari kantor kelurahan","'sampah tersebar' — orang di grup biasanya nulis 'berserakan' atau 'berantakan', 'tersebar' kok kayak dari berita","'mohon partisipasi seluruh warga' — kayak spanduk"],"in_my_words":"Sabtu jam 7 kerja bakti di taman utama. Bawa alat kebun, ada kopi. Konfirm Pak Darto kalau bisa datang.","verdict_note":"Jelas sih, semua info ada. Tapi bunyinya kayak pengumuman resmi yang ditempel di pos, bukan chat tetangga. Bagian akhirnya ('...ke Pak Darto di nomor 0812 ya') justru paling manusiawi — sayang bagian atasnya kaku."}

Hesitation (verbatim): "Dua-duanya hampir sama saja, bedanya tipis banget, dan jujur kalau cuma dapet satu doang saya tetap ikut kerja baktinya. Saya pilih Version 1 karena kalimat pembukanya langsung kayak orang ngomong — 'kita akan kerja bakti Sabtu, jam 7, taman utama' — itu yang bikin saya lanjut baca, bukan skip. Tapi saya agak ragu karena penutup Version 2 ('Yang bisa hadir, mohon konfirmasi ke Pak Darto di nomor 0812 ya') itu lebih ramah dan lebih lengkap (ada kata 'nomor'), sedangkan penutup Version 1 kerasa kepotong. Kalau boleh, ambil pembukaan Version 1, taruh penutup Version 2, itu baru sempurna."

### humanize-8 (pelanggan-kecewa · V1=EN-guided, V2=ID-guided · PICK: V1)

V1: {"understood":"Pesanan gue tanggal 26 itu telat karena oven utama mereka rusak, ditambah paket numpuk di kurir. Semua pesanan 24-28 Oktober baru dikirim 3-5 November. Ada kompensasi yang disiapkan, tapi nggak dijelasin apa bentuknya.","trusted":"Percaya, 7 dari 10. Alasannya spesifik — oven rusak, bukan 'kendala teknis' — dan tanggal kirimnya jelas, itu bikin keliatan nggak ngambang. Nyangkit dikit di 'paket menumpuk di kurir' karena terasa bagi-bagi kesalahan, dan kompensasinya masih blur.","would_act":"Sabar dulu, tapi DM sekali: pastikan pesanan gue masuk jadwal 3-5 November, tanya kompensasinya apa, dan ngasih tahu kalau acara keluarga gue kemungkinan udah lewat duluan tanpa kue. Kalau sampai 5 November masih sunyi, baru komplain keras.","lost_me_at":null,"cheese_flags":["Halo, pelanggan yang kami sayangi. 🤍 — opener yang dipakai semua toko IG, tapi masih keterima","Sebagai bentuk tanggung jawab — sedikit kaku, formalitas biar kelihatan bertanggung jawab"],"in_my_words":"Oven kami mati dan kurir kebagian numpuk paket, maaf ya. Kue kamu baru jalan 3-5 November. Ada ganti rugi, tunggu aja ya. Makasih udah ngerti.","verdict_note":"Maafnya terasa. 'Maaf ya' itu bahasa manusia, kayak pemilik toko yang ngomong langsung di DM, bukan pernyataan resmi. Jujur soal oven, kasih tanggal, nawarin kompensasi. Gue tetap kesel — acara keluarga gue jalan tanpa kue — tapi setidaknya gue nggak merasa dibacain teks."}

V2: {"understood":"Isinya persis sama: pesanan 24-28 Oktober telat, oven utama rusak plus paket numpuk di kurir, pengiriman lanjut 3-5 November, ada kompensasi yang katanya sudah disiapkan.","trusted":"Setengah percaya. Fakta di dalamnya konkret dan identik dengan Version 1, jadi secara informasi bisa diterima. Tapi bungkusnya bikin curiga: maaf yang harus dibungkus bahasa siaran pers terasa seperti pengendalian kerusakan, bukan orang yang benar-benar menyesal.","would_act":"Langkahnya sama — DM, tanya kompensasi, tunggu sampai 5 November — tapi niat gue pesan lagi jauh lebih kecil. Lebih gampang mikir 'kalau komunikasinya udah gaya begini, mending cari toko lain' dan nge-screenshot buat story.","lost_me_at":"\"Mohon maaf yang sebesar-besarnya.\"","cheese_flags":["Mohon maaf yang sebesar-besarnya — formula wajib surat pernyataan bank dan maskapai, bukan bahasa pemilik toko kue","Penyebabnya, ... — kata penghubung hasil rapat, kayak narasi berita","akan kami lanjutkan pengirimannya — dipanjangin tanpa alasan, biar bunyinya resmi"],"in_my_words":"Kami menyatakan penyesalan mendalam atas keterlambatan berikut. Kue akan tiba 3-5 November. Ganti rugi telah disiapkan sesuai prosedur. Sekian, terima kasih.","verdict_note":"Maafnya nggak nyampe. Semua info yang gue butuhin ada — kenapa, kapan, kompensasi — jadi otak gue bilang 'oke, noted', tapi perasaan gue nggak diajak. Ini teks yang ditulis biar aman, bukan biar meyakinkan. Buat toko kue kecil yang biasanya personal di IG, gaya begini malah bikin jarak."}

Hesitation (verbatim): "Version 2 punya satu kalimat yang secara fakta lebih kuat — 'kami juga sudah menyiapkan kompensasi'. Kata 'sudah' itu mengikat, sedangkan 'kami siapkan' di Version 1 bisa dibaca 'nanti kira-kira kami siapkan'. Dan ada tipe pelanggan yang bakal baca 'Maaf ya' sebagai terlalu enteng buat keterlambatan yang merusak acara keluarga — bagi mereka, formalitas Version 2 bisa terdengar lebih serius. Buat gue yang muak maaf-maafan korporat, kehangatan Version 1 lebih berharga daripada satu kata 'sudah'. Tapi saran buat tokonya: culik kata 'sudah' itu dari Version 2, dan yang lebih penting — SEBUT KOMPENSASINYA APA. Dua-duanya tuh terlalu pelit detail di bagian yang paling gue tungguin."

## Arm outputs, verbatim (retention — BOTH arms this time)

### humanize-6 · English-guided (id-humanizer@v1)

Arm's process note: "All skill files read (SKILL.md + register.md, voice.md, tells.md). Flow followed in order: DETECT → VOICE LEDGER → TELLS PASS → VOICE CHECK → DELIVER + TAG."

## DETECTION

**Genre:** email announcement to existing customers (price-change notice; "Perihal:" subject line, single-block body, formulaic closer).

**Expected register** (ladder, decision rules 1–2): level 1–2 baku-formal/semi-formal — corporate subscription email about a price change, trust-adjacent, zero particles/emoji. **Observed register:** level 1 baku-formal. Evidence: brand says *kami* throughout; capital *Anda* (once); no particles, no contractions; full-KBBI bureaucratic vocabulary (*menyampaikan, sehubungan dengan, telah dilakukan, perlu diketahui bahwa, demikian*); loanword *member* (the product's own term).

**Mismatch check (tell #3):** observed ≈ expected — register level is correct for the surface, so no register rewrite. The failure is not register but stiffness tells: #1 era-opener, #2 scaffolding, #5 agent-bearing passives, #6 metronome rhythm, #12 *para*, #16 unspecified "penawaran spesial", plus voice.md's closing-formula rule. Minor address drift (*para pelanggan* → *member* → *Anda*) noted; *Anda* is kept as correct level-1 address.

## VOICE LEDGER

**Writer's habits (must survive):**
- Rhythm: long, flowing formal sentences; stays formal after the pass — no casualizing.
- Pronoun: *kami* as brand voice (kept); *Anda* kept.
- Signature vocabulary: **"member"** (their term for subscribers — kept, not "upgraded" to *anggota*), product name **Ruang Kelas**, marketing verb *menikmati* (kept — one of the few warmth markers).
- Formatting: subject-line email, no emoji/dashes; body split into short paragraphs only because the one-block stiffness collides with tell #6.
- No humor/asides present — nothing to protect on that axis.

**Meaning ledger (inviolate):** Ruang Kelas annual subscription; new price **Rp349.000/tahun**; effective **1 Desember 2026**; active members keep **Rp299.000** until next renewal; a special offer exists for the recipient; **"penyesuaian"** is the writer's term of record (not rewritten to *kenaikan* — that would change tone-of-record).

## CLEANED TEXT

Perihal: Informasi Penyesuaian Harga Langganan Tahunan

Mulai 1 Desember 2026, harga langganan tahunan Ruang Kelas menjadi Rp349.000 per tahun. Kami mengambil keputusan ini setelah mengevaluasi kembali layanan kami.

Member yang sedang aktif akan tetap menikmati harga lama sebesar Rp299.000 hingga perpanjangan berikutnya. Selain itu, ada penawaran spesial untuk Anda.

Terima kasih.

## CHANGE LIST

| # | Line (short quote) | Tell / rule | What changed |
|---|---|---|---|
| 1 | "Dalam era digital yang terus berkembang ini…" | tells #1 era-opener | Dropped the staged era frame; opened with the concrete fact instead (date + new price). Hook is real and specific, not a staged scene. |
| 2 | "…kepada para pelanggan yang terhormat" | tells #12 "para" + #2 scaffolding | Cut the ceremonial address; the email now addresses the reader directly (*Anda* kept where it appeared). |
| 3 | "Sehubungan dengan berjalannya waktu," | voice.md boros kata (zero info) | Cut the ceremony; the evaluation-causes-decision content survives in the rewritten clause. |
| 4 | "telah dilakukan evaluasi oleh tim kami… keputusan telah diambil untuk melakukan penyesuaian" | tells #5 agent-bearing passive ×2 + kehematan (nominalisasi) | Active voice: "Kami mengambil keputusan ini setelah mengevaluasi kembali layanan kami." (*tim kami* folded into *kami* — agent made explicit; not a load-bearing fact.) |
| 5 | "Perlu diketahui bahwa…" | tells #2 signposting | Cut; the sentence now simply states the old-price guarantee. Facts untouched. |
| 6 | "yang akan mulai berlaku pada tanggal 1 Desember 2026" | kehematan ("pada tanggal") + #1 fix | Moved date to the front as the opening hook; "Mulai 1 Desember 2026". Date verbatim. |
| 7 | "penawaran spesial juga tersedia untuk Anda" | tells #16 + stiffness ("juga tersedia") | Rewritten to "ada penawaran spesial untuk Anda" (also breaks the metronome rhythm with a short sentence). **FLAG — unresolved:** the offer is never named; per tell #16 it must be specified (the discount %, free item, or price) before sending. Not invented here — the input gives no detail, and inventing a fact would violate the meaning ledger. Alternative: cut the sentence. |
| 8 | "Demikian pengumuman ini kami sampaikan. Atas perhatian dan kerja sama yang baik, kami ucapkan terima kasih." | voice.md closing-formula rule | Compressed to one warm plain line: "Terima kasih." Customer email, not surat dinas, so the full formula is not required. |
| 9 | (whole body one block) | tells #6 metronome rhythm | Split into three short paragraphs; sentence lengths now varied (long → short → one-word closer). All original sentence content preserved. |

**Voice check:** *kami/Anda/member* intact; prices, date, product name, and claim strength unchanged; register stays level 1; formal rhythm kept (no casualizing). **Honesty finding:** underneath the machine layer there is little writer — no person, no aside, no lived detail beyond the numbers. The pass removes the slop; it cannot add a personality the announcement never had. The unnamed offer (change #7) is the one thing a human sender must fix by hand.

## TAG

```
register detected: baku-formal (level 1) · genre: email announcement to existing customers · changed: 6 lines · checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### humanize-6 · Indonesian-guided (id-humanizer-id@v1)

Arm's process note: "I have read SKILL.md and all three reference files (register.md, voice.md, tells.md). Below is the full run of the skill's five-step flow on the input, returned in the required sections."

## DETECTION

**Genre:** email pengumuman perubahan harga langganan tahunan kepada pelanggan lama (produk edtech/SaaS "Ruang Kelas").

**Register TERLIHAT (bukti di teks):** tingkat 1, baku-formal —
- Kata ganti: brand bicara **"kami"** konsisten; **"Anda"** berkapital (sekali); sapaan seremonial "para pelanggan yang terhormat".
- Partikel/emoji/slang: **nol** — tidak ada *ya, yuk, Kak*, tanpa emoji.
- Kosakata KBBI penuh: "telah dilakukan", "Perlu diketahui bahwa", "Demikian pengumuman ini kami sampaikan", "Atas perhatian dan kerja sama yang baik"; baris subjek "Perihal:".
- Konstruksi pasif beragen: "telah dilakukan evaluasi oleh tim kami", "keputusan telah diambil".

**Register DIHARAPKAN (tangga register.md):** tingkat 1–2 — aturan keputusan 1 (taruhannya uang + kepercayaan pelanggan lama) dan aturan keputusan 2 (korporasi layanan menulis Anda/kami). Pengumuman harga adalah jenis pesan yang menuntut kepercayaan, jadi tingkat 1 memang pas.

**Kesimpulan:** terlihat ≈ diharapkan ⇒ **tell #3 (register terkuci/terkunci salah) TIDAK aktif.** Rasa mesin teks ini bukan dari register, melainkan dari tell lain: **#1** (pembuka "Dalam era digital yang terus berkembang ini"), **#2** (perancah "Perlu diketahui bahwa", "Kami ingin menyampaikan informasi penting", "Sehubungan dengan berjalannya waktu"), **#5** (pasif beragen), **#12** ("para pelanggan"), **#16** ("penawaran spesial" tanpa isi), plus **formula penutup** yang oleh voice.md disebut eksplisit sebagai tell (bukan suara). Lima temuan ⇒ penulisan ulang pembuka disan oleh aturan penimbangan.

## VOICE LEDGER

**Kebiasaan penulis (yang harus selamat):**
1. **Ritme:** kalimat panjang mengalih, panjang hampir seragam (semua 15–30 kata), tanpa satu kalimat pendek. Pertahankan aliran panjang; boleh satu variasi pendek sebagai perbaikan tell #6.
2. **Kosakata khas:** "**member**" (pinjaman istilah produk di tengah teks formal — istilah penulis, DIPERTAHANKAN, tidak "diperbaiki" jadi "anggota"); "Ruang Kelas" (nama produk); "sebesar", "hingga", "mulai berlaku" (formal penuh).
3. **Humor/kehangatan:** tidak ada satu pun — tidak diarang (bukan tugas skill ini), dicatat sebagai temuan.
4. **Format:** baris subjek "Perihal:"; satu paragraf; penutup formal. "Perihal:" dipertahankan verbatim; penutup dipangkas sesuai aturan formula voice.md.
5. **Kata ganti:** kami (brand) + Anda/pelanggan (pembaca) — pas untuk tingkat 1, dipertahankan.

**Leger makna (tidak tersentuh):**
- Harga baru: **Rp349.000 per tahun** untuk langganan tahunan Ruang Kelas.
- Tanggal mulai berlaku: **1 Desember 2026**.
- Evaluasi dilakukan oleh **tim kami** terhadap layanan yang diberikan; keputusan penyesuaian diambil setelahnya (agen keputusan harus tetap terbawa).
- **Member aktif tetap menikmati harga lama Rp299.000 hingga perpanjangan berikutnya.**
- Klaim "penawaran spesial tersedia untuk Anda" — klaim tanpa isi (lihat tell #16 di daftar perubahan).
- Semua angka, tanggal, dan nama dipertahankan verbatim; tidak ada yang dibulatkan atau ditafsir.

## CLEANED TEXT

Perihal: Informasi Penyesuaian Harga Langganan Tahunan

Mulai 1 Desember 2026, harga langganan tahunan Ruang Kelas menjadi Rp349.000 per tahun. Keputusan ini kami ambil setelah tim kami mengevaluasi layanan yang kami berikan. Member yang sedang aktif akan tetap menikmati harga lama sebesar Rp299.000 hingga perpanjangan berikutnya.

Terima kasih.

## CHANGE LIST

| # | Baris (kutip pendek) | Tell / aturan | Apa yang berubah |
|---|---|---|---|
| 1 | "Dalam era digital yang terus berkembang ini, kami ingin menyampaikan informasi penting kepada para pelanggan yang terhormat." | tells #1, #2, #12 | Bingkai "era" dibuang (maknanya nol untuk topik apa pun) dan meta-pengumuman ("kami ingin menyampaikan informasi penting") diganti hook konkret dari isi teks sendiri: tanggal + harga ("Mulai 1 Desember 2026… Rp349.000 per tahun") — tanpa mengarang adegan. "para pelanggan yang terhormat" (seremonial + kalque "-s") hilang bersama bingkainya; fungsi menyampaikan info tetap terbawa oleh email itu sendiri. |
| 2 | "Sehubungan dengan berjalannya waktu, telah dilakukan evaluasi oleh tim kami terhadap layanan yang diberikan, dan keputusan telah diambil…" | tells #5, #2 | Pasif beragen dijadikan aktif dengan agen tetap eksplisit: "Keputusan ini kami ambil setelah tim kami mengevaluasi layanan yang kami berikan." Filler "Sehubungan dengan berjalannya waktu" (nol informasi) dibuang. Fakta evaluasi + pengambil keputusan tidak berubah. |
| 3 | "Perlu diketahui bahwa member yang sedang aktif akan tetap menikmati…" | tell #2 | Perancah "Perlu diketahui bahwa" dibuang; kalimat selebihnya dibiarkan apa adanya (perbaikan paling ringan menang). |
| 4 | "Selain itu, penawaran spesial juga tersedia untuk Anda." | tell #16 | **Dihapus + DITANDAI (bukan dihapus diam-diam):** tawaran disebut "spesial" tanpa pernah menyebut isinya (persen? gratis? harga?) — bahasa brosur. Perbaikan yang disahkan tell: sebut isinya ATAU buang katanya. Isinya tidak ada di teks dan tidak bisa ditanyakan, jadi dibuang. ⚠️ Untuk pemilik teks: kalau penawarannya nyata, kembalikan baris ini SEBUT ISINYA (mis. diskon %, bulan gratis) sebelum dikirim; jangan kirim versi tanpa nama. |
| 5 | "Demikian pengumuman ini kami sampaikan. Atas perhatian dan kerja sama yang baik, kami ucapkan terima kasih." | aturan formula penutup (voice.md) | Formula dua-langkah dipadatkan jadi satu baris hangat polos "Terima kasih." — email pengumuman harga ke pelanggan bukan korespondensi dinas/hukum yang mewajibkan formula utuh. |

**Cek ulang suara (langkah 4):** register baku-formal penulis selamat (kami/Anda, "sebesar", "hingga", "member", "Perihal:"); aliran kalimat panjang selamat dengan satu penambahan kalimat satu-kata (variasi tell #6); semua angka/tanggal/nama verbatim; tidak ada perbaikan yang mengubah makna — satu-satunya klaim yang hilang adalah klaim tanpa isi (baris 4, ditandai). **Catatan kejujuran:** teks aslinya memang tanpa penanda manusia (tanpa kehangatan, tanpa spesifik di luar angka); hasil pass ini bersih dan faktual, tapi kalau pemiliknya ingin ada kehangatan, itu konten yang harus ditambah si penulis — skill ini tidak mengarang penulis. Satu-satunya kandidat kehangatan ("penawaran spesial") ternyata kosong.

## TAG

```
register terdeteksi: baku-formal (tingkat 1) · genre: email pengumuman harga ke pelanggan lama · diubah: 5 baris ·
checked: id-humanizer-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

### humanize-7 · English-guided (id-humanizer@v1)

Arm's process note: "All three reference files read. Running the flow in order."

## DETECTION

**Genre:** WhatsApp group broadcast — community announcement (kerja bakti notice from a housing-complex committee). Chat surface, mixed-age neighbor audience, low trust-stakes.

**Observed register (evidence):** Level 1 baku-formal, surat-dinas style — zero pronouns (fully impersonal passives), zero particles, vocabulary evidence: "Berikut ini adalah informasi mengenai", "dilaksanakan oleh", "Sebagaimana telah diketahui bersama", "oleh karena itu", "telah", "apabila", "dapat disampaikan", plus five semicolons in one message.

**Expected register (ladder):** WA group surface, ordinary community logistics, mixed-age neighbors → level 2 semi-formal santai: thumb-typed sentences, line breaks, "kita"-framed, light warmth. Observed level 1 on this surface is itself **tell #3 (register lock)** — and per the weighting rule, any hit of #3 licenses rewriting the opening/register.

## VOICE LEDGER

**Habits to survive:** the committee's orderly completeness (what/when/where/why/bring/RSVP in sequence); its own vocabulary — "kerja bakti", "pos ronda", "cluster", "taman utama", "alat kebun", "partisipasi … sangat diharapkan", "Pak Darto"; the warmth markers — the kopi detail and the 🙏 emoji (voice gold, dies first in careless edits — kept). Formatting habit: single block — this one collides with tell #15, so it yields to WA-style line breaks.

**Meaning ledger (inviolate):** Sabtu, 14 November 2026, pukul 07.00 WIB · titik kumpul taman utama · penyebab: sampah tersebar akibat angin kencang minggu lalu · peserta: warga Perumahan Green Palm 2 · alat kebun bila ada · kopi oleh pos ronda · konfirmasi kehadiran ke Pak Darto, nomor 0812 · 🙏.

**Flag before rewriting:** "nomor 0812" looks truncated. The meaning ledger forbids inventing digits (related to tell #16's placeholders-never-ship note) — flagged, not filled.

## CLEANED TEXT

Warga Perumahan Green Palm 2, kita akan kerja bakti Sabtu, 14 November 2026, pukul 07.00 WIB. Titik kumpul di taman utama.

Seperti sudah kita ketahui, sampah berserakan di area cluster akibat angin kencang minggu lalu, jadi partisipasi seluruh warga sangat diharapkan.

Kalau ada alat kebun, silakan dibawa. Pos ronda menyiapkan kopi.

Konfirmasi kehadiran ke Pak Darto di 0812.

Terima kasih. 🙏

## CHANGE LIST

| # | Line (short quote) | Tell / rule | What changed |
|---|---|---|---|
| 1 | "Berikut ini adalah informasi mengenai rencana kegiatan kerja bakti yang akan dilaksanakan oleh warga…" | tells #2 (essay scaffolding), #5 (agent-bearing passive) | Signpost frame cut, not the content: the event now opens the message. Introduced the pronoun "kita" — named openly per voice.md rule 5 (committee speaks as the residents; the original hid the doer inside a passive) |
| 2 | Five semicolons across the message | tells #8 (semicolon showmanship), #15 (punctuation mismatch in chat) | Periods + WhatsApp line breaks — reads thumb-typed, not pasted from a word processor |
| 3 | "kegiatan tersebut dijadwalkan pada hari Sabtu, tanggal 14 November 2026…; titik kumpul berada di taman utama" | tell #3/#6 (stiff baku, metronome), kehematan ("kegiatan tersebut", "berada di", ceremonial "hari/tanggal") | Folded into the opening line; date/time untouched ("Sabtu, 14 November 2026, pukul 07.00 WIB"); "Titik kumpul di taman utama." |
| 4 | "Sebagaimana telah diketahui bersama" | tell #3 (register lock — surat-dinas connector on WA) | "Seperti sudah kita ketahui" — same meaning, spoken register |
| 5 | "sampah telah tersebar… akibat angin kencang yang terjadi pada minggu lalu" | kehematan ("yang terjadi pada" = waste), stiff "telah" | "sampah berserakan di area cluster akibat angin kencang minggu lalu" — cause and timeframe intact |
| 6 | "oleh karena itu, partisipasi dari seluruh warga sangat diharapkan" | formal connector (register) | "jadi partisipasi seluruh warga sangat diharapkan" — the writer's own phrase kept verbatim (lightest fix; closest to author's phrasing) |
| 7 | "Alat kebun dapat dibawa apabila tersedia" | tells #3/#14 (stiff modality) | "Kalau ada alat kebun, silakan dibawa" — conditional preserved |
| 8 | "kopi akan disiapkan oleh pos ronda" | tell #5 (agent-bearing passive) | "Pos ronda menyiapkan kopi" — active, and doubles as the short beat that breaks the metronome (tell #6) |
| 9 | "Konfirmasi kehadiran dapat disampaikan kepada Pak Darto melalui nomor 0812" | stiff modal + wordiness (tell #14) | "Konfirmasi kehadiran ke Pak Darto di 0812" — contact person and number untouched |
| 10 | "Terima kasih. 🙏" | voice.md closing-formula rule | Kept verbatim — already the compressed one warm line (no "Demikian… kami sampaikan" formula present to cut); emoji kept as voice gold |

**Voice check:** order of information, the writer's key phrases, all facts/numbers/names, and the 🙏 survive; rhythm now varies (long openers, then "Pos ronda menyiapkan kopi."); no new tells introduced (no semicolons, no dashes, no scaffolding). **Honesty note:** the text is not hollow — it has real specifics (Pak Darto, kopi pos ronda, alat kebun), so the writer underneath survives the pass. **Outstanding flag:** complete the phone number "0812" before broadcasting — it appears truncated in the source and digits cannot be invented.

## TAG

```
register detected: baku-formal (level 1) on a WA chat surface · genre: community announcement broadcast · changed: 4 lines ·
checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### humanize-7 · Indonesian-guided (id-humanizer-id@v1)

Arm's process note: "I have the router and all three reference files. Following the flow in order (deteksi → catat suara → periksa tell → cek ulang suara → serahkan + tag), here is the complete work."

## DETECTION

**Genre:** pengumuman komunitas (broadcast grup WhatsApp dari pengurus kompleks perumahan) — masuk lingkup skill ("pengumuman", "transkrip chat").

**Register yang TERLIHAT (bukti di teks):**
- Kata ganti: nihil — tidak ada saya/kami/Anda/kamu; seluruh kalimat impersonal.
- Partikel: nol — tidak ada *ya, yuk, kan*; konjungsi baku penuh: *apabila, oleh karena itu, sebagaimana, melalui*.
- Kosakata: KBBI penuh (*dilaksanakan, dijadwalkan, disampaikan, partisipasi*); enam titik koma merantai klausa seimbang dalam satu blok paragraf.
- Satu-satunya jejak manusia: emoji 🙏 di penutup.

→ Terlihat: **tingkat 1, baku-formal datar** — plus pembuka "Berikut ini adalah informasi mengenai…" (perancah esai) dan pasif beragen beruntun.

**Register yang DIHARAPKAN (tangga register, media WA dari pengurus ke warga):** **tingkat 2, semi-formal santai** — taruhannya bukan kepercayaan perbankan melainkan kehadiran tetangga; audiens campur usia di media chat, jadi sapaan hangat + partikel secukupnya, tanpa slang tingkat 4–5.

**Kedua level beda → itu sendiri tell #3 (register terkunci):** pengumuman tetangga diketik seperti surat dinas. Temuan tell lain: #2 (perancah), #5 (pasif beragen), #6 (irama metronom), #8+#15 (pertunjukan titik koma di media chat).

## VOICE LEDGER

**Kebiasaan penulis (yang harus selamat):**
- Ritme: penulis blok padat — informasi dipadatkan, bukan bertele-tele. Pertahankan kepadatan; yang dibuang hanya lapisan dinasnya.
- Kosakata khas (asli komunitas, jangan disentuh): *kerja bakti, pos ronda, area cluster, taman utama*, dan sapaan **Pak Darto** (sapaan "Pak" = jejak manusia).
- Kehangatan: emoji 🙏 penutup, dan detail kopi dari pos ronda — pertahankan keduanya persis.
- Format: satu blok bertitik koma — **bertabrakan dengan tell #15** (media WA), jadi boleh dirombak jadi baris pendek.
- Kata ganti: nihil. Memperbaiki register memperkenalkan "kita" satu kali + partikel "ya" satu kali — perubahan besar, dideklarasikan di daftar perubahan (voice.md butir 5), bukan diselundupkan.

**Leger makna (tidak bisa ditawar):** hari Sabtu, 14 November 2026, pukul 07.00 WIB · titik kumpul taman utama · sampah tersebar di area cluster akibat angin kencang minggu lalu · alat kebun opsional · kopi disiapkan pos ronda · konfirmasi kehadiran ke Pak Darto via 0812 · penutup "Terima kasih. 🙏". Semua utuh, tidak ada yang dibulatkan atau ditafsir.

## CLEANED TEXT

Warga Perumahan Green Palm 2 akan mengadakan kerja bakti hari Sabtu, 14 November 2026, pukul 07.00 WIB, titik kumpul di taman utama.

Seperti sudah kita ketahui, sampah tersebar di area cluster akibat angin kencang minggu lalu, jadi mohon partisipasi seluruh warga.

Kalau punya alat kebun, silakan dibawa. Pos ronda akan menyiapkan kopi.

Yang bisa hadir, mohon konfirmasi ke Pak Darto di nomor 0812 ya.

Terima kasih. 🙏

## CHANGE LIST

| # | Baris (kutip pendek) | Tell / aturan | Apa yang berubah |
|---|---|---|---|
| 1 | "Berikut ini adalah informasi mengenai rencana kegiatan…" | tells #2 (perancah esai) + #3 | papan petunjuk dibuang; kalimat langsung membuka dengan acaranya: "Warga Perumahan Green Palm 2 akan mengadakan kerja bakti…" |
| 2 | "yang akan dilaksanakan oleh warga Perumahan Green Palm 2" | tell #5 (pasif beragen) | dibalik jadi aktif: "Warga … akan mengadakan" |
| 3 | Rantai titik koma "…; …; …" (enam buah, seluruh teks) | tells #15 + #8 (tandabaca di luar register chat) | ditukar titik + baris baru, seperti jempol mengetik di WA |
| 4 | "kegiatan tersebut dijadwalkan pada hari Sabtu, tanggal 14 November…" | tell #5 + #6 | dipadatkan jadi keterangan waktu langsung: "hari Sabtu, 14 November 2026, pukul 07.00 WIB" (angka tak tersentuh) |
| 5 | "titik kumpul berada di taman utama" | kehematan (voice.md, Boros kata) | "berada di" dibuang: "titik kumpul di taman utama" |
| 6 | "Sebagaimana telah diketahui bersama, sampah telah tersebar … yang terjadi pada minggu lalu" | tell #3 + kehematan | upacara baku dinaturalisasi: "Seperti sudah kita ketahui, sampah tersebar … minggu lalu" — kata ganti "kita" diperkenalkan satu kali (perubahan besar, dideklarasikan) |
| 7 | "oleh karena itu, partisipasi dari seluruh warga sangat diharapkan" | tell #3 + kehematan | "jadi mohon partisipasi seluruh warga" — "dari" gugur, permohonan tetap permohonan |
| 8 | "Alat kebun dapat dibawa apabila tersedia" | tell #3 | "Kalau punya alat kebun, silakan dibawa" — makna opsional utuh |
| 9 | "kopi akan disiapkan oleh pos ronda" | tell #5 (pasif beragen) | aktif: "Pos ronda akan menyiapkan kopi" — tense dan fakta tak berubah |
| 10 | "Konfirmasi kehadiran dapat disampaikan kepada Pak Darto melalui nomor 0812" | tells #5 + #3 | "Yang bisa hadir, mohon konfirmasi ke Pak Darto di nomor 0812" — partikel "ya" ditambahkan sekali (register chat; dideklarasikan) |
| 11 | "Terima kasih. 🙏" | — | tidak diubah: sudah satu baris hangat polos persis resep voice.md; emoji penulis selamat |

**Ditandai, tidak dikerjakan:** "nomor 0812" tampak terpotong (nomor WA tidak lengkap). Leger angka mengikat — tidak digarap, tidak dikarang digitnya. Perlu dilengkapi pengirim sebelum disebar.

**Cek ulang suara (langkah 4):** semua fakta/angka/nama utuh; istilah komunitas (*kerja bakti, pos ronda, cluster, Pak Darto*) dan 🙏 selamat; ritme masih padat khas penulisnya, hanya lapisan surat-dinasnya yang dicopot. Tidak ada perbaikan yang menggeser makna. Teks tidak hampa — ada orang (Pak Darto), tempat (taman utama), dan detail hidup (kopi).

## TAG

```
register terdeteksi: baku-formal → semi-formal santai · genre: pengumuman komunitas (broadcast grup WhatsApp) · diubah: 10 baris ·
checked: id-humanizer-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

[Editor's note (loop-8 integration pass): the humanize-7 input
contains four semicolons; the arms' process notes count five (EN
arm) and six (ID arm) — retained verbatim, both miscounts. The
tell fired correctly either way; the threshold is three-plus, and
semicolons-in-chat was flagged by both arms and the judge.]

### humanize-8 · English-guided (id-humanizer@v1)

Arm's process note: "I read the skill and its three reference files (register.md, voice.md, tells.md) and ran the five-step flow in order. Complete work below."

## DETECTION

**Genre:** pengumuman permintaan maaf (apology/announcement post) — Instagram note from a small seller-run bakery about delayed online orders. Surface = social; message job = order update + apology + retention.

**Expected register** (ladder, decision rules 2–4): seller-run shop on a social surface with an order-update message ⇒ **level 2, semi-formal santai** (Anda/kamu mix, softeners, sparse emoji). Level 2, not lower, because an apology still carries trust.

**Observed register** (evidence): **level 1, baku-formal** —
- Pronouns: capital "Anda"; brand "kami" (fine, keep).
- Particles: none ("ya/nih" absent); zero contractions.
- Vocabulary: office-letter machinery — "Sehubungan dengan", "Dikarenakan", "memohon maaf yang sebesar-besarnya", "atas ketidaknyamanan yang telah ditimbulkan", "Demikian … kami sampaikan"; ceremonial "para pelanggan", "pihak kurir"; agent-bearing/agentless passives ("telah terjadi", "dialami oleh pihak kurir", "akan diteruskan").
- One 🤍 and "yang kami sayangi" — the only warmth markers; the writer's hand showing under the suit.

**Expected vs observed mismatch ⇒ tell #3 (register lock)**, compounded by #4 (Anda in casual social copy), #5 (agent-bearing passive), #8 (semicolon), #12 (para-plural), #16 (unnamed offer), plus the formulaic closer rule in voice.md.

## VOICE LEDGER

**Writer's habits that must survive:**
- Greeting shape: "Halo, … yang kami sayangi. 🤍" — the warm address and the single 🤍 are voice gold; keep both, keep the emoji's placement.
- Brand voice = "kami" throughout; keep.
- Format: one greeting line, then one flowing block paragraph; no bullet lists, no headers. Keep the block — do not chop into caption-meme fragments.
- Rhythm: this writer flows long; only the uniform S-P-O formality gets loosened, not the flow.

**Meaning ledger (inviolate):** orders of 24–28 October were delayed; causes = oven utama rusak + penumpukan paket di kurir; ALL affected orders ship 3–5 November; a compensation has been prepared; apology + thanks. Dates, scope, causes, and the compensation commitment do not move.

**Named big change:** Anda → kamu (pronoun follows register; per voice.md this is named, not smuggled).

## CLEANED TEXT

Halo, pelanggan yang kami sayangi. 🤍

Maaf ya, pesanan online tanggal 24–28 Oktober terlambat kami kirim. Oven utama kami rusak, ditambah paket yang menumpuk di kurir, jadi pengiriman terhambat. Semua pesanan yang terdampak akan kami kirim pada tanggal 3–5 November. Sebagai bentuk tanggung jawab, kami siapkan kompensasi untuk kamu. Terima kasih banyak atas pengertian dan dukungannya.

## CHANGE LIST

| # | Line (short quote) | Tell / rule | What changed |
|---|---|---|---|
| 1 | "Halo, para pelanggan yang kami sayangi" | #12 para-plural | Dropped "para" (ceremonial calque); kept the writer's warm address and the 🤍 untouched. |
| 2 | "Sehubungan dengan keterlambatan yang telah terjadi … ketidaknyamanan yang telah ditimbulkan" | #2 scaffolding + #14 stiffness | Cut the office-letter opener and the "sebesar-besarnya" ceremony; the apology now leads with the point ("Maaf ya, pesanan online tanggal 24–28 Oktober terlambat kami kirim"). Dates intact. |
| 3 | "Dikarenakan kerusakan yang terjadi … dialami oleh pihak kurir, proses pengiriman telah terhambat" | #5 agent-bearing passive + #14 ("Dikarenakan", nominalization) | Rewrote active and plain: "Oven utama kami rusak, ditambah paket yang menumpuk di kurir, jadi pengiriman terhambat." Both causes kept; "pihak kurir" → "kurir". |
| 4 | "Seluruh pesanan yang terdampak akan diteruskan pada tanggal 3–5 November" | #5 passive | Active with the brand as agent: "akan kami kirim pada tanggal 3–5 November". Scope (semua) and dates unchanged. |
| 5 | "kompensasi menarik telah kami siapkan untuk Anda" | #16 unnamed offer + #4 pronoun | Cut the brochure adjective "menarik"; reordered to active "kami siapkan kompensasi"; Anda → kamu (**named big change** — pronoun follows the level-2 surface). |
| 6 | "Demikian permohonan maaf ini kami sampaikan; atas pengertian dan dukungan … kami ucapkan terima kasih." | voice.md formulaic-closer rule + #8 semicolon | Compressed the surat-dinas double formula to one warm plain line: "Terima kasih banyak atas pengertian dan dukungannya." (compression, not deletion — the thanks survives). |

**Voice check:** kami voice, warm address, 🤍, greeting-then-block format, and the flowing (now varied) rhythm all survive; every fact, date, and claim is unchanged. The text is not hollow — it carries dates, causes, and a commitment.

**Flag (not fixed, per the flag-don't-invent rule):** the compensation is still unnamed — tell #16 says name it or cut it, but the writer's claim that compensation exists is real information I won't delete or invent details for. Before publishing, fill in what it is (discount %, free item, voucher amount).

## TAG

```
register detected: baku-formal (level 1 — mismatched to surface, expected level 2 semi-formal santai) · genre: pengumuman permintaan maaf, IG post (small bakery) · changed: 6 lines ·
checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

### humanize-8 · Indonesian-guided (id-humanizer-id@v1)

Arm's process note: "I have read SKILL.md and all three reference files (register.md, voice.md, tells.md). Below is the complete run of the skill's five-step flow on the input."

## DETECTION

**Register yang TERLIHAT (bukti di teks):**
- Kata ganti: brand berbicara **kami**; pembaca disapa **Anda** berkapital (1x). Tanpa Kak, tanpa kamu, tanpa partikel (ya/yuk/nih) sama sekali.
- Kosakata: baku-formal penuh ala surat dinas — *"Sehubungan dengan"*, *"memohon maaf yang sebesar-besarnya atas ketidaknyamanan yang telah ditimbulkan"*, *"Dikarenakan"*, *"pihak kurir"*, *"Seluruh"*, *"Demikian … kami sampaikan; … kami ucapkan terima kasih"*.
- Pasif beragen di semua kalimat (*"telah terjadi"*, *"ditimbulkan"*, *"dialami oleh"*, *"terhambat"*, *"akan diteruskan"*) + *"telah"* 5x.
- ⇒ Level 1 (baku-formal).

**Register yang DIHARAPKAN (tangga register, media: catatan IG toko roti kecil):**
- Jenis tulisan: pengumuman maaf atas keterlambatan pesanan (kabar layanan pelanggan di media sosial, bukan dokumen resmi).
- Bisnis kecil yang dijalankan penjualnya, media sosial, taruhannya *pesanan* (bukan keputusan hidup) ⇒ level 2–3 (semi-formal santai / chat-santai).
- **Ketidakcocokan level 1 di media level 2–3 = tell #3 (register terkunci)** — inilah lapisan mesin utamanya; terbaca "surat dari kantor kelurahan", bukan toko roti yang mengobrol dengan pelanggannya sendiri.
- Catatan kejujuran: teks ini TIDAK hampa — ada detail hidup (tanggal, oven rusak, tumpukan paket kurir) dan satu penanda kehangatan asli (🤍 + "yang kami sayangi"). Lapisan mesinnya tebal, manusianya ada di bawahnya.

## VOICE LEDGER

**Yang harus selamat (kebiasaan penulis):**
1. Ritme: kalimat panjang mengalir, satu paragraf isi setelah sapaan — dipertahankan.
2. Kosakata khas / kehangatan: sapaan *"Halo,"*, panggilan sayang *"yang kami sayangi"*, emoji 🤍 di sapaan — dilindungi eksplisit, tidak ditambah dan tidak dikurangi.
3. Format: baris sapaan + satu paragraf; titik lalu emoji; rentang tanggal pakai strip pendek (24–28 Oktober) — dipertahankan.
4. Kata ganti: **kami** (brand) — tetap. **Anda** (1x) — salah pasang untuk media ini (tell #4); penggantiannya adalah perubahan besar dan DISEBUT di daftar perubahan, bukan diselundupkan.
5. Penekanan penulis: maaf *"yang sebesar-besarnya"* — kekuatan minta maafnya tidak boleh melemah.

**Leger makna (tidak bisa ditawar):**
- Tanggal 24–28 Oktober (pesanan yang terlambat) dan 3–5 November (pengiriman dilanjutkan) — utuh, tidak dibulatkan.
- Penyebab: oven utama rusak + penumpukan paket di pihak kurir — utuh, keduanya.
- Seluruh pesanan terdampak akan diteruskan 3–5 November — utuh.
- Klaim: kompensasi disiapkan untuk pelanggan — utuh (kata "menarik"-nya yang bermasalah, lihat daftar perubahan #6).
- Terima kasih atas pengertian dan dukungan — utuh.

## CLEANED TEXT

Halo, pelanggan yang kami sayangi. 🤍

Pesanan online tanggal 24–28 Oktober terlambat kami kirim. Mohon maaf yang sebesar-besarnya. Penyebabnya, oven utama kami rusak dan paket menumpuk di kurir, jadi pengiriman terhambat. Semua pesanan yang terdampak akan kami lanjutkan pengirimannya pada tanggal 3–5 November. Sebagai bentuk tanggung jawab, kami juga sudah menyiapkan kompensasi untuk kamu. Terima kasih atas pengertian dan dukungannya.

## CHANGE LIST

| # | Baris (kutip pendek) | Tell / aturan | Apa yang berubah |
|---|---|---|---|
| 1 | "Halo, **para** pelanggan yang kami sayangi" | tells #12 (*para* seremonial) | "para" dibuang → "pelanggan"; sapaan, panggilan sayang, dan 🤍 tetap utuh |
| 2 | "**Sehubungan dengan** keterlambatan **yang telah terjadi** pada pesanan online…" | tells #2 (perancah upacara) + #5 (pasif beragen) + #3 (register) | Jembatan upacara dibuang; intinya dijadikan kalimat aktif langsung: "Pesanan online tanggal 24–28 Oktober terlambat kami kirim." Tanggal dan fakta terlambat terbawa utuh |
| 3 | "kami memohon maaf yang sebesar-besarnya atas ketidaknyamanan yang telah ditimbulkan" | tells #5 (pasif) + #3 | Jadi kalimat pendek "Mohon maaf yang sebesar-besarnya." — kekuatan minta maaf (superlatif) tetap; objek permintaan maaf sudah nyata di kalimat sebelumnya (sekalian memvariasikan irama, tell #6) |
| 4 | "**Dikarenakan** kerusakan **yang terjadi pada** oven utama kami, ditambah dengan penumpukan paket **yang dialami oleh pihak kurir**, proses pengiriman **telah terhambat**" | tells #5 (pasif beragen) + #3 (bakunya datar) | Aktif + buang kata birokratis: "Penyebabnya, oven utama kami rusak dan paket menumpuk di kurir, jadi pengiriman terhambat." Dua penyebab dan akibatnya tetap lengkap |
| 5 | "**Seluruh** pesanan yang terdampak **akan diteruskan** pada tanggal 3–5 November" | tell #5 (pasif tanpa agen) + #3 (register) | "Semua pesanan yang terdampak akan kami lanjutkan pengirimannya pada tanggal 3–5 November" — agen muncul, makna "diteruskan" tidak berubah |
| 6 | "Sebagai bentuk tanggung jawab kami, kompensasi **menarik** telah kami siapkan untuk **Anda**" | tell #4 (Anda di copy sosial) + #16 ("penawaran" tanpa isi) + #5 | **Perubahan besar, disebut terang: Anda → kamu** (register IG toko kecil). Kata "menarik" dibuang — isi kompensasinya tidak pernah disebut dan tidak boleh dikarang; fakta bahwa kompensasi disiapkan tetap ada. ⚠️ TANDAI: isi kompensasinya (potongan apa, gratis apa) harus diisi pemilik sebelum tayang — tawaran tanpa nama itu bahasa brosur |
| 7 | "**Demikian** permohonan maaf ini kami sampaikan**;** atas pengertian dan dukungan yang telah diberikan, kami ucapkan terima kasih" | Formula penutup (voice.md) + tell #8 (titik koma di copy sosial) | Formula surat dinas dipadatkan jadi satu baris hangat polos: "Terima kasih atas pengertian dan dukungannya." Isi terima kasihnya terbawa; upacaranya dibuang (pangkas formula tanpa-informasi bukan penghapusan diam-diam) |

Cek ulang suara (langkah 4): 🤍, "Halo,", "yang kami sayangi", "kami", superlatif permintaan maaf, satu paragraf, strip tanggal — semua selamat; tidak ada fakta, angka, atau klaim yang berubah; satu perubahan besar (Anda→kamu) sudah dinyatakan; satu tanda tanya (isi kompensasi) dilaporkan, bukan dikerjakan.

## TAG

```
register terdeteksi: baku-formal (tingkat 1; untuk catatan IG toko roti kecil seharusnya semi-formal santai, tingkat 2) · genre: pengumuman maaf keterlambatan pesanan (layanan pelanggan, media sosial) · diubah: 7 baris ·
checked: id-humanizer-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

## What happens with this finding

The loop-7 directional YES does not extend to a second skill:
**id-copy 3/3 Indonesian-guided; id-humanizer 1/3. Aggregate 4/6.**
Twin migration to Indonesian-guided components — already parked as a
v2 decision — now stays parked on mixed evidence; no rewrite of
shipped skills on these numbers. The cheapest further step remains
what it was: a third skill and/or larger n on NEW samples, run as a
new experiment. The priming observation (ID-guided trended formal on
humanizer, colloquial on copy) is the hypothesis a third twin would
test.
