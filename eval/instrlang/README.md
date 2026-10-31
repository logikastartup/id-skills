# instrlang — eksperimen bahasa instruksi (loop 7)

Pertanyaan pemilik repo (2026-10-31, pertanyaan yang membuka arc ini):
"apakah menulis skill-nya dalam bahasa Indonesia membantu LLM
memperbaiki bahasa Indonesianya?"

## Rancangan

- **Lengan 1 (English-guided):** `id-copy` apa adanya — router
  berbahasa Inggris (gloss Indonesia satu baris per langkah) +
  komponen berbahasa Inggris.
- **Lengan 2 (Indonesian-guided):** `id-copy-id/` di folder ini —
  kembaran yang ditulis **langsung dari nol dalam bahasa Indonesia** (bukan
  terjemahan): aturan, sumber, contoh, dan bobot sama persis;
  satu-satunya variabel adalah bahasa teks instruksinya.
- **Instrumen:** protokol A/B buta `id-bench` — hakim persona baru,
  label VERSION 1/2, urutan diacak dan dicatat, PICK wajib, tanpa
  rerun. Sampel: `copy-3`, `copy-4`, `copy-5` (n=3 — arah, bukan
  statistik).
- **Risiko yang sudah dinamai sebelumnya** (plans/id-skills.md
  "Instruction language"): instruksi baku-formal mungkin **menular**
  ke output baku-formal — arah yang salah saat register targetnya
  tingkat 3–4. Karena itu register instruksi kembarannya dipilih
  lugas-profesional (padanan fungsional dari prosa Inggris versi
  aslinya), bukan seremonial; dan verdict hakim mencatat register
  yang terbaca, bukan cuma pilihannya.

## Kontrol keabsahan

1. Kembaran dibangun **sebelum** A/B dan lulus panel kritikus
   telinga penutur asli (loop 7) — kalau tidak, temuannya cuma
   "terjemahan buruk kalah".
2. Kedua lengan sama-sama memakai skill (tanpa lengan "tanpa skill")
   — bahasa instruksi adalah satu-satunya perbedaan.
3. Hakim buta terhadap bahasa instruksi; keduanya hanya melihat
   output jadi (catatan proses dan blok tag dilucuti sebelum
   dinilai).
4. Hasil lengan English-guided untuk sampel yang sama dipakai ulang
   dari ekspansi loop-7 (output `id-copy` atas copy-3/4/5) — bukan
   dijalankan dua kali.

## Ke mana hasilnya

`eval/verdicts/instrlang-ab.md` — dan dipublikasikan apa adanya,
menang kalah. Kalau Indonesian-guided menang, kandidat migrasi
komponen dibahas sebagai keputusan v2 (bukan diam-diam diubah).
