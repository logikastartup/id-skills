# longform-4 — dev blog on agent evals (input for id-longform eval, loop 7)

**Generated:** 2026-10-31 by the repo builder, from the prompt below.

**generation prompt (reproduce the brief):**

```
Buat brief artikel blog teknologi Indonesia (800-900 kata) untuk
developer: "Eval agent AI kamu kemungkinan besar mengukur hal yang
salah — dan cara memilih metrik yang benar". Sudut bebas asal
spesifik. Sertakan satu contoh fiktif-tapi-konkret (chatbot internal
HR yang skor kepuasan naik tiap kuartal padahal jawaban cuti makin
salah), satu tabel kecil (metrik vanity vs metrik yang jujur), penutup
yang mendarat. Pembaca: developer yang baru pertama membangun eval.
```

- **Piece:** dev blog article, 800–900 kata, audience = developer
  building their first eval suite.
- **Must include:** the fictional HR-chatbot example (satisfaction
  score rising quarterly while leave-policy answers quietly drift
  wrong); one small comparison table (vanity vs honest metrics); a
  closing that lands a point, not a summary.
- **Suggested persona:** dev-docs.

## Brief (both arms write from this)

Thesis to sharpen: evals that measure what's easy (CSAT, thumbs,
token counts) drift away from what matters (is the answer *correct*
for this policy/version/data). The HR bot: kepuasan naik 4,6 → 4,8
dua kuartal beruntun, tapi audit manual 50 pertanyaan cuti menemukan
11 jawaban tidak cocok dengan policy terbaru — pengukuran dan
kenyataan berjalan sendiri-sendiri. Banned: era openers,
"Kesimpulannya" mechanical closer, padding. Register: semi-formal
santai untuk developer.
