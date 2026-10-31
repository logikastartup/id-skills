---
name: id-bench
description: Run a blind reader A/B over two or more Indonesian text variants — fresh persona verdicts, randomized order, forced pick, everything retained. Use to test copy variants before publishing, or to benchmark any Indonesian-writing skill against its no-skill baseline. Small n is disclosed as directional, never dressed as statistics.
---

# id-bench — blind A/B over Indonesian text

This is the repo's own evaluation discipline, productized (it grew out
of `eval/run.md` and produced `eval/verdicts/ab-test.md`). **Router
only**; the protocol lives in one file, personas come from `id-reader`.

## Flow (always in order)

1. **SETUP** — inputs: 2+ variants of ONE piece (same intent), the
   persona set (from [`../id-reader/personas/`](../id-reader/personas/)
   — copy `id-reader` alongside if you take only this folder), and the
   question the bench must answer (e.g. "which reads more natural?").
   Assign blind labels; randomize presentation order; write down the
   order you used.
   *Indonesian:* Siapkan dua varian atau lebih dari tulisan yang sama,
   pilih persona pembacanya, acak urutannya, catat urutan yang dipakai.
2. **JUDGE** — one fresh judge per SAMPLE: loads ONLY its persona file +
   that sample's variants (labeled VERSION 1/2/…). No tells list, no
   bench internals, no sight of other judges' output. It emits the
   `id-reader` verdict JSON for EACH variant, then a forced PICK.
   *Indonesian:* Setiap varian dibaca agen baru yang hanya melihat
   persona dan varian itu. Tidak boleh lihat daftar tell atau varian
   lain.
3. **REPORT** — table (variant × understood/trusted/would_act + picks)
   + retained JSONs + the mandatory honesty line when n is small:
   "directional, not statistics".
   *Indonesian:* Tampilkan tabelnya, simpan semua JSON, dan tulis
   baris jujurnya: ini sekadar petunjuk arah, bukan statistik.
4. **ARCHIVE** — every variant verbatim (process notes stripped so
   arms are compared on text alone) + every verdict. See
   [`references/protocol.md`](references/protocol.md).
   *Indonesian:* Simpan semua varian dan semua verdict apa adanya.

## Non-negotiables

- **No rerun until green.** A losing arm is a finding about the text
  (or the skill under test), recorded — not a do-over.
- **One builder = disclosed.** If one author wrote variants AND
  personas, the report says so (co-evolution caveat, below).
- **n is named.** Every report states sample count; below ~10 picks it
  says "directional" in the same breath as the result.

## Scope (v1)

**In:** Indonesian text variants (any genre the persona set covers);
skill-vs-baseline arms. **Out of scope:** English or multilingual
battings; non-text artifacts; claiming statistical significance;
ranking MORE than ~4 variants in one pass (reader fatigue corrupts
picks).
