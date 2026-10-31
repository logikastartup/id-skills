---
name: id-copy-id
description: Kembaran id-copy yang ditulis langsung dalam bahasa Indonesia — menulis copy pemasaran bahasa Indonesia yang natural (tagline, caption WhatsApp/IG, copy produk), bebas tell "bahasa Indonesia ala AI" (baku kaku, kalque idiom, lebay, buta register). Mewajibkan pilihan register eksplisit, menyusun draf yang diuji terhadap daftar hitam tell, menerapkan aturan code-switch. Skill ini menyediakan aturan, pertimbangan, dan contoh bersumber — bukan pengganti telinga penutur asli; hasil selalu membawa pengingat serahkan ke pembaca asli. Artefak eksperimen bahasa instruksi (eval/instrlang/), bukan skill rilis.
---

# id-copy-id — copy pemasaran bahasa Indonesia yang natural

**Hanya router.** Setiap aspek hidup di satu file komponen di bawah
`references/` — baca yang dibutuhkan tugasnya, tidak lebih. Aturannya
sama persis dengan `id-copy`; bedanya hanya satu: seluruh teks
instruksi ini ditulis langsung dalam bahasa Indonesia (rancangan
eksperimennya ada di [`../README.md`](../README.md)).

## Alur (selalu berurutan)

1. **KUMPULKAN** — media (WhatsApp | caption IG | tagline | copy
   produk), tujuan, audiens, CTA. Ada yang kurang → tanya, jangan
   nebak.
2. **PILIH REGISTER** — pilihan eksplisit dari
   [`references/register.md`](references/register.md). **Jangan
   menulis satu kalimat pun sebelum register dipilih dan
   dinyatakan.** Berdiri di tengah-tengah dua register adalah cara
   lahirnya copy yang "aman tapi lebay".
3. **TULIS DRAF** — terapkan konsekuensi register (kata ganti, bentuk
   verba, sapaan, jatah emoji) plus daftar kata yang tetap Inggris di
   [`references/codeswitch.md`](references/codeswitch.md); norma tiap
   media dari [`references/platforms.md`](references/platforms.md).
4. **CEK TELL** — periksa draf terhadap semua entri
   [`references/tells.md`](references/tells.md). Setiap temuan:
   **perbaiki barisnya** — jangan menghapusnya diam-diam.
5. **SEMPURNAKAN + TAG** — serahkan copy-nya, lalu blok tag:

```
register: <pilihan> · media: <media> · checked: id-copy-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

## Kejujuran

Skill ini menyediakan aturan, pertimbangan, dan contoh bersumber —
hasilnya lebih tajam, tapi tetap bukan pengganti telinga penutur
asli. Putusan akhir ada pada pembaca Indonesia manusia: pasangkan
dengan `id-reader` untuk meminta verdict sebelum publikasi.

## Perluasan

- Tell baru → `references/tells.md` (satu entri: pola · kenapa gagal
  · perbaikan · pasangan bagus/buruk).
- Media baru → `references/platforms.md`.
- Baris yang memuat slang selalu membawa status bertanggal
  (`masih hidup | basi <tanggal>`). Segarkan status basi; jangan
  pernah percaya slang tanpa cek tanggal.

## Lingkup (v1)

Copy pemasaran, tagline, caption WhatsApp/IG, copy produk. **Di luar
lingkup:** tulisan panjang, blog, microcopy UX, dialek daerah di luar
gaul sentris-Jakarta, output bahasa Inggris. Dua klarifikasi: memakai
konvensi sapaan daerah (Kak/Bunda/Akang menurut platforms.md) bukan
berarti menulis dialek — itu tetap di dalam lingkup; dan eval memang
menguji media di tepi lingkup (pembukaan blog, headline) — run itu
membuktikan tell-nya berlaku melampaui zona nyaman, bukan
memperlebar kontraknya.
