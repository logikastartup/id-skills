---
name: id-humanizer-id
description: Kembaran id-humanizer yang ditulis langsung dalam bahasa Indonesia — menulis ulang teks Indonesia yang kaku dan berasa mesin supaya terbaca ditulis orang yang sama (laporan, esai, post, email). Membunuh tell "bahasa Indonesia ala AI" tanpa mengubah makna DAN tanpa menghapus suara penulisnya; setiap perubahan disebut satu per satu di daftar perubahan. Pakai saat teks Indonesia sudah ada dan terasa buatan mesin. Bukan untuk membuat konten baru (id-copy) atau menerjemahkan (id-translate). Artefak eksperimen bahasa instruksi (eval/instrlang/), bukan skill rilis.
---

# id-humanizer-id — buang aksen mesin, pertahankan penulisnya

**Hanya router.** Komponen hidup di `references/`; aturannya sama
persis dengan `id-humanizer`; bedanya hanya satu: seluruh teks
instruksi ini ditulis langsung dalam bahasa Indonesia (rancangan
eksperimennya ada di [`../README.md`](../README.md)).

## Pembeda yang membuat skill ini beda

`id-copy` **menulis baru** (register dipilih, draf disusun).
`id-translate` **menerjemahkan** (ada teks sumber dalam bahasa lain).
Di sini teksnya sudah ada dalam bahasa Indonesia dan sudah punya
register — jadi alur ini **mendeteksi** register dan mempertahankan
suara penulis, bukan memilih lalu menulis draf.

## Alur (selalu berurutan)

1. **DETEKSI** — kenali register teks ini sekarang (bukti: kata ganti,
   partikel, kosakata) dan jenis tulisannya. Sebutkan keduanya. Cara
   mendeteksinya: tangga register
   ([`references/register.md`](references/register.md)) memberi level
   yang DIHARAPKAN per media (aturan keputusannya); bukti di teks
   memberi level yang TERLIHAT — kalau keduanya beda, itu sendiri
   tell #3.
2. **CATAT SUARA** — inventarisasi yang harus selamat, sesuai
   [`references/voice.md`](references/voice.md): kebiasaan penulisnya
   (ritme kalimat, kata khas, humor, format) DAN leger maknanya
   (fakta, angka, nama, klaim — tidak boleh disentuh).
3. **PERIKSA TELL** — jalankan [`references/tells.md`](references/tells.md)
   terhadap seluruh teks. Setiap temuan **diperbaiki, bukan dihapus
   diam-diam** — barisnya ditulis ulang dengan isinya utuh
   (boilerplate tanpa informasi boleh dipangkas sesuai aturan formula
   penutup di voice.md).
4. **CEK ULANG SUARA** — baca ulang hasilnya terhadap catatan suara.
   Kalau perbaikan malah menghapus penulisnya, pakai perbaikan yang
   lebih ringan. Kalau sebuah "perbaikan" mengubah makna, itu bukan
   perbaikan — tandai, jangan dikerjakan.
5. **SERAHKAN + TAG** — teks bersih + daftar perubahan (setiap
   perubahan disebut: apa · tell yang mana · kenapa), lalu blok tag:

```
register terdeteksi: <r> · genre: <g> · diubah: <n> baris ·
checked: id-humanizer-id@v1
⚠️ serahkan dulu ke pembaca Indonesia asli sebelum dipublikasikan.
```

## Kejujuran

Skill ini membuang aksen mesin; ia tidak bisa menambahkan kepribadian
yang memang tidak ada di teksnya. Teks tanpa manusia di bawahnya
tetap hampa — itu temuan untuk dilaporkan, bukan cacat untuk
disembunyikan.

## Lingkup (v1)

**Masuk:** teks Indonesia apa pun yang tidak kamu buat dengan
`id-copy` — laporan, esai, pengumuman, post, email, transkrip chat.
**Di luar lingkup:** menulis copy baru (→ `id-copy`); menerjemahkan
(→ `id-translate`); mengubah makna, tone-of-record, atau kata
legal/medis (tandai, jangan tulis ulang); teks non-Indonesia.
