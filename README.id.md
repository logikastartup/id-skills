# id-skills

[Baca versi bahasa Inggris](README.md)

Kumpulan skill agent untuk pasar Indonesia: copy yang terasa seperti
ditulis manusia, dinilai langsung oleh pembaca yang memang bakal
melihatnya.

LLM global kalau menulis bahasa Indonesia aksennya gampang dikenali,
sebut saja *bahasa Indonesia ala AI*: bahasa baku yang kaku seperti
buku pelajaran, metafora yang diterjemahkan mentah-mentah dari bahasa
Inggris, kalimat yang lebay, dan buta register (Anda dipakai padahal
pembaca seharusnya disapa Kak). Dua skill di repo ini menanganinya
dari dua sisi:

- **`id-copy`** — menulis dan memperbaiki copy pemasaran bahasa
  Indonesia. Skill-nya mewajibkan kamu memilih register dan
  menyatakannya secara eksplisit sebelum mulai menulis. Draf lalu
  diperiksa dengan daftar tell yang terdokumentasi, mengikuti aturan
  code-switch (kata mana yang tetap bahasa Inggris — dicek ke KBBI atau
  diberi penanda sumbernya), plus norma tiap platform.
- **`id-reader`** — agent persona LLM berperan sebagai pembaca
  Indonesia tertentu (pemburu diskon marketplace, pembaca LinkedIn kalangan startup,
  pembeli di grup WhatsApp), membaca copy-nya, lalu mengeluarkan verdict
  terstruktur. Pembaca menilai dari rasanya, bukan dari daftar tell —
  dua skill ini sengaja tidak memakai checklist yang sama (satu
  penulis membangun keduanya, apa yang dicakup dan apa yang tidak
  dijelaskan di catatan jujur soal A/B).

Skill ekspansi (2026-10-31 — empat di antaranya dengan A/B buta lima
sampel lintas loop 5+7, catatan hasil lengkapnya di `eval/verdicts/`):

- **`id-translate`** — EN→ID yang terasa ditulis orisinal dari nol: buku
  paritas (klaim, angka, dan keraguan tidak boleh melenceng) plus bank
  transformasi pembunuh kalque dan struktur bahasa Inggris yang ikut
  kebawa.
- **`id-longform`** — artikel dan newsletter: angle dinyatakan,
  tiap bagian satu gerakan, plus daftar larangan pola perancah AI
  yang terdokumentasi.
- **`id-humanizer`** — bersihkan teks Indonesia apa pun dari lapisan
  mesin tanpa menghapus penulisnya, tiap perubahan dicatat. Register
  dideteksi, bukan dipilih.
- **`id-social`** — script TikTok, post LinkedIn dan Facebook: satu
  komponen per platform, slang selalu bertanggal, register per
  platform.
- **`id-bench`** — A/B buta persona untuk varian teks apa pun:
  disiplin evaluasi repo ini, dijadikan produk.

## Kenapa layak dipercaya

- **Sumbernya ikut terbawa** — entri KBBI yang dicek langsung,
  kampanye brand yang nyata, kumpulan template yang terdokumentasi,
  status slang beserta tanggalnya. Yang tidak bersumber ditandai apa
  adanya (`pattern-level` = pola hasil observasi, `[inf]` = inferensi),
  tidak pernah diam-diam.
- **`eval/` ikut dikirim** — sampel "bahasa Indonesia ala AI", sebagian
  dari lapangan, sebagian dibuat ulang dengan prompt yang bisa
  direproduksi. Sampel-sampel itu ditulis ulang memakai `id-copy`, lalu
  dibaca ulang oleh persona sebelum dan sesudahnya — termasuk satu
  kegagalan jujur yang sengaja dipertahankan.
- **A/B buta** — model yang sama menulis ulang sampel uji (sampel yang
  tidak disentuh saat skill dibangun), sekali dengan skill, sekali
  tanpa skill. Pembaca persona tidak diberi tahu versi mana hasil
  skill, dan urutan bacaannya diacak. Hasilnya: dua dari dua pembaca
  memilih versi hasil skill
  ([`eval/verdicts/ab-test.md`](eval/verdicts/ab-test.md)). Ingin
  mencoba sendiri? Resepnya ada di [`eval/run.md`](eval/run.md).

Dua skill ini membuat hasil copy makin tajam. Keduanya bukan pengganti
telinga penutur asli — setiap output `id-copy` menyertakan pengingat:
serahkan dulu dibaca penutur asli sebelum dipublikasikan.

## Hasil

Model yang sama di kedua lengan — satu-satunya beda: pakai skill atau
tidak. Hakim persona baru, buta label, urutan diacak, wajib memilih,
tanpa rerun. Skor dulu, baru rasakan teksnya: tiap skill punya berkas
before/after di [`eval/before-after/`](eval/before-after) yang
mengutip keluaran aslinya. (n=5 per skill lintas ronde evaluasi — ini sekadar petunjuk arah,
bukan statistik.)

Para hakimnya adalah agent persona LLM — agent baru, model dasar yang
sama, memerankan personanya — bukan pembaca manusia. Anggap setiap
skor sebagai bukti soal teksnya, bukan riset preferensi manusia.

### id-copy · 5/5

> **Tanpa skill:** "Ada kabar baik buat hari ini: tas wanita premium
> koleksi terbaru lagi diskon spesial! … siapa cepat dia dapat ya,
> Kak!"
>
> **Dengan skill:** "Lagi ada promo tas hari ini... kualitas premium
> tapi harganya bikin kaget (yang enak). Stoknya beneran dikit, makanya
> jangan lama-lama! … Mau langsung order atau lihat katalog dulu?"

Hakim buta (wa-buyer) soal versi pertama: *"the broadcast I delete…
Nobody who ends a message like that has ever sent me a resi. Mute."* Soal
versi kedua: *"a question I can answer in three words…"* Pada evaluasi sampel liar yang lebih awal, empat dari lima berubah
total setelah ditulis ulang, satu kegagalan dipertahankan apa adanya.
→ [`id-copy-before-after.md`](eval/before-after/id-copy-before-after.md)

### id-translate · 3/5

> **Tanpa skill:** "Kunci API Anda ada di menu **Pengaturan →
> Kunci**" — jalur menu di aplikasi berbahasa Inggris ikut
> diterjemahkan. Kata hakim: *"You do not translate UI labels; that is
> the one string I need to click…"*
>
> **Dengan skill:** "*API key* kamu ada di **Settings → Keys**. Cukup
> set sekali:" — jalur menunya tetap bisa diklik, register kamu, buku
> paritas 7/7.

Kekalahannya aturan yang sama dari arah sebaliknya: skill
mempertahankan jalur Inggris di aplikasi yang tampilannya bahasa
Indonesia. Satu pelajaran dari dua sisi — jalur UI mengikuti bahasa
tampilan aplikasi milik pembacanya (kini structures.md #21).
→ [`id-translate-before-after.md`](eval/before-after/id-translate-before-after.md)

### id-longform · 4/5

> **Tanpa skill:** esai — sapaan "Anda" dari awal sampai akhir,
> titik koma dramatis di mana-mana. Kata hakim: *"I don't forward
> consultant-voiced think pieces to the team channel."*
>
> **Dengan skill:** "Jumat, jam 10.14. … Rp449.000. Padahal harga
> promo Rp399.000 sudah berlaku sejak Kamis malam." Judul bagian
> berupa pernyataan, ada bagian "Yang bisa kamu tulis hari ini". Kata
> hakim: *"This is the one I paste into the team channel."*

Kekalahannya pelajaran register: pembaca toko berusia 48 tahun membaca
"kamu" di versi skill sebagai sapaan anak muda — *"kalau sales datang
ke toko saya pasti bilang 'Pak'."* Usia audiens kini ikut menentukan
pilihan register.
→ [`id-longform-before-after.md`](eval/before-after/id-longform-before-after.md)

### id-humanizer · 3/5 — 0/2, diperbaiki, lalu 3/3

> **Masukan:** "…Demikian pengumuman ini kami sampaikan… atas
> perhatian dan kerja sama para pengguna, kami ucapkan terima kasih."
>
> **Lengan skill mempertahankan formulanya.** Kata pembaca buta: *"saya
> seperti membaca surat dari kantor kelurahan… penutup surat resmi
> yang distempel, bukan yang diucapkan orang."*

Kedua sampel loop 5 dimenangkan lengan tanpa skill. Akarnya sama: penutup
formula salah dikira sebagai voice penulis, padahal tell. Kini
`voice.md` memutus **"Formulaic closers are tells, not voice."**
Perbaikan ini lahir setelah A/B-nya selesai — mengukur ulang butuh
sampel baru, sesuai aturan tanpa-rerun. Loop 7 membawa sampel
barunya: **3/3 untuk lengan skill.** Perbaikinya, terukur.
→ [`id-humanizer-before-after.md`](eval/before-after/id-humanizer-before-after.md)

### id-social · 4/5

> **Tanpa skill:** "Anak Jatim, stop scroll dulu." … "Tag temenmu yang
> ngaku tahan pedes…" Kata hakim: *"kayak page Facebook zaman 2021."*
>
> **Dengan skill:** kriuknya jadi pembuka — "Balado level tiga, asli
> Bondowoso" di atas keripik yang dipatahkan tepat di depan lensa —
> dan CTA yang bisa dijawab satu kata: "kamu tim level berapa?" Kata
> hakim: *"itu bahasa TikTok, bukan bahasa iklan… saya langsung ketik
> '3' di komen, nggak perlu mikir."*

Kedua hakim loop 5 mengutip balik aturan platformnya. Slang
bertanggal ditolak oleh aturan staleness. Kekalahan TikTok di loop 7
menghasilkan aturan alasan CTA (sebutkan apa yang didapat pembaca
dari menjawab), masuk ke tiktok.md di hari yang sama.
→ [`id-social-before-after.md`](eval/before-after/id-social-before-after.md)

### id-reader · pihak yang menilai

Mesin verdict di balik semua hasil di atas: seorang persona membaca
satu kali sesuai perannya lalu menunjuk baris persis yang membuatnya
berhenti. Pada tempelan FAQ AI: *"suasananya seperti dosen ngajar…
Tidak ada angka, tidak ada bukti…"* → setelah ditulis ulang, persona
yang sama: *"malam ini aku coba tanya menu seminggu."* Evaluasi sampel
liar: 4 dari 5 berubah total, satu kegagalan dipertahankan.
→ [`id-reader-before-after.md`](eval/before-after/id-reader-before-after.md)

### Eksperimen bahasa instruksi · ditanya dua kali, jawabannya berbeda

Pertanyaan yang membuka repo ini: kalau skill-nya ditulis dalam
bahasa Indonesia, apakah bahasa Indonesianya ikut membaik? Loop 7
membangun kembaran id-copy yang ditulis langsung dalam bahasa
Indonesia (aturan dan sumber sama — bahasa instruksi menjadi
satu-satunya variabelnya) lalu menguji buta melawan skill berbahasa
Inggris: versi Indonesia 3/3, drafnya terbaca lebih santai
(kolokial) di register yang sama —
*"'Garing' bukan 'renyah'… 'tombol Beli Sekarang' itu emang tombol
yang ada di Shopee — gak nyasar."* Loop 8 membangun kembaran skill
kedua, id-humanizer, dan jawabannya berbalik: versi Inggris 2/3,
dengan lengan versi Indonesia cenderung lebih formal — seorang
hakim membaca maaf superlatif yang dipertahankan lengan itu
sebagai *"Mohon maaf yang sebesar-besarnya — formula wajib surat
pernyataan bank dan maskapai, bukan bahasa pemilik toko kue"*.
Gabungan dua skill: 4/6 — efeknya nyata di copy, tidak di
humanizer. Migrasi komponen tetap diparkir. Dua rekamannya terbit
apa adanya, kalah termasuk.
→ [`instrlang-ab.md`](eval/verdicts/instrlang-ab.md) ·
[`instrlang-ab-2.md`](eval/verdicts/instrlang-ab-2.md)

### id-bench · alat ujinya

Disiplinnya dijadikan produk: hakim buta, urutan diacak dan dicatat,
wajib memilih, catatan keraguan dipertahankan, semua lengan disimpan
apa adanya. Bukti demonya adalah ronde evaluasi repo ini sendiri — agregat
**19/25** lintas loop 3+5+7, tiap kekalahan dilacak sampai ke baris
penyebabnya lalu diperbaiki di hari yang sama atau dicatat sebagai
konsekuensi aturan yang memang sudah diketahui. Satu keraguan hakim
yang terekam: *"Version
1 is the better argument and Version 2 is the better conversation,
and I buy from conversations…"*
→ [`id-bench-before-after.md`](eval/before-after/id-bench-before-after.md)

## Struktur

```
id-copy/           skill untuk menulis (router tipis + 4 komponen)
  references/      register · tells · codeswitch · platforms  ← dipakai ulang
id-reader/         skill untuk verdict (protokol + personas/)
id-translate/      EN→ID dengan buku paritas + bank transformasi
id-longform/       artikel + newsletter (angle · gerakan · daftar larangan)
id-humanizer/      bersihkan teks Indonesia apa pun (buku gaya penulis)
id-social/         tiktok · linkedin · facebook, satu file per platform
id-bench/          alat uji A/B buta (protokol + persona id-reader)
eval/              sampel → rewrite → verdict → before/after
```

Setiap komponen menangani satu topik dalam satu file, dimuat hanya
saat dibutuhkan. Router SKILL.md ditulis dalam dua bahasa: setiap
langkah
berisi aturan dalam bahasa Inggris plus satu baris padanan bahasa
Indonesia. Skill id-* berikutnya (misalnya riset iklan) cukup
menyalin komponen yang sama lengkap dengan penanda versinya.

## Cara pakai

Salin folder skill ke direktori skill agent-mu (Claude Code:
`~/.claude/skills/` atau `.agents/skills/`; agent lain: di mana pun
skill diletakkan). `id-copy` bisa jalan sendiri. Untuk meminta verdict
sebelum publikasi, pasangkan `id-reader` dengannya. Tiap skill ekspansi
juga bisa jalan sendiri. `id-bench` butuh persona milik `id-reader`
(salin kedua foldernya). Komponen bersama disalin utuh dengan penanda
versinya (header `copied-from:`) — perbarui dengan menyalin ulang,
jangan menyunting salinannya sampai bercabang.

## Status

Kandidat v1 — dibangun dan dievaluasi 2026-10-31 oleh Bobby Heykal
([timai.id](https://timai.id)) dengan bantuan agent. Pemeriksaan ala
penutur asli untuk persona, contoh, dan seluruh teks Indonesia di repo
ini berjalan lewat siklus gauntlet, bukan satu kali restu (loop 6,
2026-10-31: panel kritikus berperan sebagai telinga penutur asli,
memeriksa semua persona dan komponen skill loop-5, temuannya langsung
diperbaiki — tetap
telinga mesin, bukan telinga pemilik repo). Ada yang terasa janggal
buat kamu? Buat issue atau PR, koreksinya masuk langsung ke repo. Slang
cepat basi: cek tanggal di `codeswitch.md` sebelum memakai baris yang
mengandung slang.

## Lisensi

MIT — salin skill-nya, tulis bahasa Indonesia yang lebih enak dibaca.
