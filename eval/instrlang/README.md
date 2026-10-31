# instrlang — eksperimen bahasa instruksi (loop 7 + loop 8)

Pertanyaan pemilik repo (2026-10-31, pertanyaan yang membuka arc ini):
"apakah menulis skill-nya dalam bahasa Indonesia membantu LLM
memperbaiki bahasa Indonesianya?"

## Rancangan

- **Lengan 1 (English-guided):** skill apa adanya — router
  berbahasa Inggris (gloss Indonesia satu baris per langkah) +
  komponen berbahasa Inggris.
- **Lengan 2 (Indonesian-guided):** kembaran di folder ini yang
  ditulis **langsung dari nol dalam bahasa Indonesia** (bukan
  terjemahan): aturan, sumber, contoh, dan bobot sama persis;
  satu-satunya variabel adalah bahasa teks instruksinya.
- **Kembaran:**
  1. `id-copy-id/` (loop 7) — pasangan `id-copy`; sampel
     `copy-3/4/5`.
  2. `id-humanizer-id/` (loop 8) — pasangan `id-humanizer`, skill
     yang seluruh tugasnya soal tekstur bahasa Indonesia (deteksi
     register, bukan pilihan); sampel `humanize-6/7/8`. Kalau bahasa
     instruksi berpengaruh, tempat paling mungkin kelihatan
     perbedaannya adalah di sini.
- **Instrumen:** protokol A/B buta `id-bench` — hakim persona baru,
  label VERSION 1/2, urutan diacak dan dicatat, PICK wajib, tanpa
  rerun. n=3 per skill — arah, bukan statistik.
- **Risiko yang sudah dinamai sebelumnya** (plans/id-skills.md
  "Instruction language"): instruksi baku-formal mungkin **menular**
  ke output baku-formal — arah yang salah saat register targetnya
  tingkat 3–4. Karena itu register instruksi kembarannya dipilih
  lugas-profesional (padanan fungsional dari prosa Inggris versi
  aslinya), bukan seremonial; dan verdict hakim mencatat register
  yang terbaca, bukan cuma pilihannya.

## Kontrol keabsahan

1. Kembaran dibangun **sebelum** A/B dan lulus panel kritikus
   (paritas aturan + telinga penutur asli) — kalau tidak, temuannya
   cuma "terjemahan buruk kalah". Loop 7: id-copy-id; loop 8:
   id-humanizer-id.
2. Kedua lengan sama-sama memakai skill (tanpa lengan "tanpa skill")
   — bahasa instruksi adalah satu-satunya perbedaan.
3. Hakim buta terhadap bahasa instruksi; keduanya hanya melihat
   output jadi (catatan proses dan blok tag dilucuti sebelum
   dinilai).
4. **Pemakaian ulang, loop 7 saja:** hasil lengan English-guided
   copy-3/4/5 dipakai ulang dari ekspansi loop-7 — bukan dijalankan
   dua kali. **Loop 8 tidak memakai ulang hasil lengan mana pun:** kedua lengan
   humanize-6/7/8 dijalankan segar untuk eksperimen ini.
5. **Komponen bersama, loop 8:** `tells.md` dan `register.md` versi
   Indonesianya identik dengan milik `id-copy-id` kecuali header provenansinya
   (masing-masing menunjuk induknya sendiri) — karena induknya
   sendiri berbagi komponen yang sama lewat salinan versi
   (`copied-from: id-copy@v1`). Ini bukan variabel tambahan: sisi
   English-guided berbagi komponen Inggris yang sama persis pula.
   Yang ditulis segar untuk kembaran ini hanya `SKILL.md` dan
   `voice.md` (komponen spesifik humanizer).

## Ke mana hasilnya

- Loop 7: `eval/verdicts/instrlang-ab.md`
- Loop 8: `eval/verdicts/instrlang-ab-2.md`

Dua-duanya dipublikasikan apa adanya, menang kalah. Kalau
Indonesian-guided menang, kandidat migrasi komponen dibahas sebagai
keputusan v2 (bukan diam-diam diubah).
