# id-skills

[Baca versi bahasa Inggris](README.md)

Kumpulan skill agent untuk pasar Indonesia: copy yang terasa ditulis
manusia, dinilai langsung oleh pembaca yang memang bakal melihatnya.

LLM global kalau menulis bahasa Indonesia aksennya gampang dikenali,
sebut saja *bahasa Indonesia ala AI*: bahasa baku yang kaku seperti
buku pelajaran, metafora yang diterjemahkan mentah-mentah dari bahasa
Inggris, kalimat yang lebay, dan buta register (Anda dipakai padahal
pembaca seharusnya disapa Kak). Dua skill di repo ini menanganinya
dari dua sisi:

- **`id-copy`** — menulis dan memperbaiki copy pemasaran bahasa
  Indonesia. Skill-nya mewajibkan kamu memilih register dan
  menyatakannya secara eksplisit sebelum mulai menulis. Draf lalu
  diperiksa terhadap daftar tell yang terdokumentasi, mengikuti aturan
  code-switch (kata mana yang tetap bahasa Inggris — dicek ke KBBI atau
  diberi penanda sumbernya), plus norma tiap platform.
- **`id-reader`** — berperan sebagai pembaca Indonesia tertentu
  (pemburu diskon marketplace, pembaca LinkedIn kalangan startup,
  pembeli di grup WhatsApp), membaca copy-nya, lalu mengeluarkan verdict
  terstruktur. Pembaca menilai dari rasanya, bukan dari daftar tell —
  dua skill ini sengaja tidak memakai checklist yang sama (satu
  penulis membangun keduanya, apa yang dicakup dan tidaknya dijelaskan
  di catatan jujur soal A/B).

Skill ekspansi (2026-10-31 — empat di antaranya dengan A/B buta dua
sampel, strukturnya di `eval/verdicts/`. Receipt `id-bench` adalah
pemetaan demo di folder yang sama):

- **`id-translate`** — EN→ID yang terasa ditulis asli dari nol: buku
  paritas (klaim, angka, dan keraguan tidak boleh melenceng) plus bank
  transformasi pembunuh kalque dan struktur bahasa Inggris yang ikut
  kebawa.
- **`id-longform`** — artikel dan newsletter: angle dinyatakan,
  bagian-per-gerakan, lawan daftar larangan perancah AI yang
  terdokumentasi.
- **`id-humanizer`** — bersihkan teks Indonesia apa pun dari lapisan
  mesin tanpa menghapus penulisnya, tiap perubahan dicatat. Register
  dideteksi, bukan dipilih.
- **`id-social`** — script TikTok, post LinkedIn dan Facebook: satu
  komponen per platform, slang selalu bertanggal, register per
  platform.
- **`id-bench`** — A/B buta persona untuk varian teks apa pun:
  disiplin evaluasi repo ini, dijadikan produk.

## Kenapa layak dipercaya

Setiap contoh dan aturan menyertakan sumbernya — entri KBBI yang dicek
langsung, kampanye brand yang nyata, kumpulan template yang
terdokumentasi, status slang beserta tanggalnya. Yang memang tidak ada sumbernya
ditandai apa adanya (`pattern-level`, `[inf]`).

Repo ini juga menyertakan **`eval/`**: sampel "bahasa Indonesia ala
AI", sebagian dikumpulkan dari lapangan, sebagian dibuat ulang dengan
prompt yang bisa direproduksi. Sampel-sampel itu ditulis ulang
memakai `id-copy`. Persona lalu membaca versi awal dan versi barunya,
memberi verdict untuk keduanya — termasuk satu kegagalan jujur yang
sengaja dipertahankan. Ada pula uji A/B buta: model yang sama menulis
ulang sampel uji (sampel yang tidak disentuh saat skill dibangun),
sekali dengan skill, sekali tanpa skill. Pembaca persona tidak
diberi tahu versi mana hasil skill, dan urutan bacaannya diacak.
Hasilnya: dua dari dua pembaca memilih versi hasil skill
([`eval/verdicts/ab-test.md`](eval/verdicts/ab-test.md)). Ingin
mencoba sendiri? Resepnya ada di [`eval/run.md`](eval/run.md).

Dua skill ini membuat hasil copy makin tajam. Keduanya bukan pengganti
telinga penutur asli — setiap output `id-copy` menyertakan pengingat:
serahkan dulu dibaca penutur asli sebelum dipublikasikan.

## Hasil

Model yang sama, dengan vs tanpa skill — pembaca persona buta:

| Sampel | Tanpa skill | Dengan skill | Pilihan pembaca buta |
|---|---|---|---|
| Promosi WA (gen-1) | trusted ✗ · would_act ✗ | ✓ · ✓ | versi skill |
| Caption IG (gen-2) | trusted ✗ · would_act ✗ | ✓ · ✓ | versi skill |

Sampel liar: 4 dari 5 flip semua verdict setelah ditulis ulang, satu
kegagalan jujur dipertahankan (wild-3). Output lengkap tanpa potongan di
[`eval/verdicts/ab-arms.md`](eval/verdicts/ab-arms.md) ·
[`eval/verdicts/results.md`](eval/verdicts/results.md). n=2, buta,
urutan diacak — ini arah, bukan statistik.

Skill ekspansi (2026-10-31, loop 5): **4 dari 8** pilihan pembaca jatuh
ke versi skill, dari empat A/B dua sampel — id-social 2/2, id-translate
1/2, id-longform 1/2, id-humanizer 0/2 (dipertahankan — dua
kekalahannya justru menghasilkan perbaikan aturan penutup formula di
hari yang sama). Protokol dan aturan kejujurannya sama:
[`eval/verdicts/translate-ab.md`](eval/verdicts/translate-ab.md) ·
[`humanize-ab.md`](eval/verdicts/humanize-ab.md) ·
[`longform-ab.md`](eval/verdicts/longform-ab.md) ·
[`social-ab.md`](eval/verdicts/social-ab.md).

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
eval/              sampel → rewrite → verdict, bisa diulang sendiri
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
([timai.id](https://timai.id)) dengan bantuan agent. Sebelum v1
difinalkan, pemilik repo (penutur asli) masih akan mengoreksi
persona, contoh, dan seluruh teks bahasa Indonesia di repo ini —
termasuk README yang sedang kamu baca (itu tulisan mesin). Karena itu
file persona masih menampilkan banner. Slang cepat basi: cek tanggal
di `codeswitch.md` sebelum memakai baris yang mengandung slang.

## Lisensi

MIT — salin skill-nya, tulis bahasa Indonesia yang lebih enak dibaca.
