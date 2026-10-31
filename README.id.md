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

## Struktur

```
id-copy/           skill untuk menulis (router tipis + 4 komponen)
  references/      register · tells · codeswitch · platforms  ← dipakai ulang
id-reader/         skill untuk verdict (protokol + personas/)
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
sebelum publikasi, pasangkan `id-reader` dengannya.

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
