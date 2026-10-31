---
name: id-translate
description: Translate English prose into Indonesian that reads originally-written — docs, READMEs, articles, announcements, business email. Kills translationese (calques, English word order, passive chains, punctuation carry-over) and enforces a parity ledger so no claim, number, hedge, or link drifts. Use when translating English into Indonesian for Indonesian readers. Rewrite with parity — not sentence-mapping; outputs carry a hand-to-native reminder.
---

# id-translate — EN→ID that doesn't read translated

**Router only.** Every concern lives in one component file under
`references/` — read what the task needs, nothing more. Each flow step
carries a one-line Indonesian gloss: the English line is the rule; the
gloss serves bilingual readers and keeps Indonesian in context.

## Flow (always in order)

1. **INTAKE** — source text, surface, audience. **Detect** the source
   register; **state** the target-register mapping from
   [`references/register.md`](references/register.md) — a decision,
   never a silent default.
   *Indonesian:* Baca teks sumbernya, tentukan mediannya dan pembacanya.
   Kenali register teks sumber, lalu nyatakan register tujuannya —
   keputusan, bukan asal ikut.
2. **LEDGER** — *before* drafting, extract the parity ledger from
   [`references/ledger.md`](references/ledger.md): every claim with its
   strength, numbers, links, hedges, quantifiers, disclosures.
   *Indonesian:* Sebelum menulis, catat dulu buku paritasnya: semua
   klaim beserta kekuatannya, angka, tautan, keraguan, kata "semua",
   pengungkapan. Tidak boleh ada yang hilang atau berubah kuat nanti.
3. **REWRITE** — draft as original Indonesian informed by the ledger,
   applying [`references/structures.md`](references/structures.md).
   Never sentence-mapped. Stay-English words per
   [`references/codeswitch.md`](references/codeswitch.md).
   *Indonesian:* Tulis seperti menulis dari nol dalam bahasa Indonesia —
   bukan memindahkan kalimat satu per satu. Ikuti bank transformasi di
   structures.md dan daftar kata yang tetap Inggris.
4. **TELLS + PARITY** — run
   [`references/tells.md`](references/tells.md) over the draft; then
   re-walk the ledger against the draft. Divergences are fixed in
   *either* direction (a weak Indonesian line can expose a false
   English claim — that happened to this repo's own README).
   *Indonesian:* Periksa draf dengan daftar tell, lalu bandingkan lagi
   dengan buku paritas. Kalau ada yang melenceng, perbaiki — dua arah.
5. **DELIVER + TAG** — the translation, then a tag block:

```
register: <target> (from <source register>) · surface: <surface> ·
structures changed: <one-line note of what was restructured> ·
ledger: <n>/<n> lines verified · checked: id-translate@v1
⚠️ hand to a native Indonesian reader before publishing.
```

   *Indonesian:* Serahkan hasilnya plus blok tag — register, media,
   catatan struktur yang diubah, dan pengingat native reader-nya.

## Honesty

This skill turns translation into rewriting under a ledger — it kills
the accent, not the need for a native ear. Meaning drift it can catch;
taste it cannot.

*Indonesian:* Skill ini mengubah penerjemahan jadi penulisan ulang dengan
buku paritas — membuang aksennya, bukan kebutuhan akan telinga penutur
asli.

## Scope (v1)

**In:** EN→ID informative prose — docs, READMEs, articles,
announcements, business email. **Out of scope:** ID→EN; literary, legal,
subtitle translation; marketing transcreation (that's `id-copy`'s
intake); machine-translation metric claims (receipts here are reader
verdicts, not scores).
