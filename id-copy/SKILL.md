---
name: id-copy
description: Write natural Indonesian marketing copy — taglines, WhatsApp/IG captions, product copy — free of "AI Indonesian" tells (stiff baku, calqued idioms, cheese overdose, register blindness). Use when writing or fixing Indonesian copy for Indonesian readers. Forces an explicit register choice, drafts against the tells blacklist, applies code-switch rules. Guardrails + judgment + examples — not a native ear; outputs carry a "hand to a native reader" reminder.
---

# id-copy — natural Indonesian marketing copy

**Router only.** Every concern lives in one component file under
`references/` — read what the task needs, nothing more. Each flow step
carries a one-line Indonesian gloss: the English line is the rule; the
gloss serves bilingual readers and keeps Indonesian in context.

## Flow (always in order)

1. **INTAKE** — collect or ask: surface (WhatsApp | IG caption | tagline |
   product copy), goal, audience, CTA. A missing piece → ask, never guess.
   *Indonesian:* Kumpulkan atau tanyakan: media (WhatsApp | caption IG |
   tagline | copy produk), tujuan, audiens, CTA. Ada yang kurang → tanya,
   jangan nebak.
2. **REGISTER** — force an explicit choice from
   [`references/register.md`](references/register.md). **Do not draft until
   a register is chosen and stated.** Averaging registers is how "safe and
   cheesy" happens.
   *Indonesian:* Pilih register secara eksplisit dari register.md dan
   nyatakan pilihannya — jangan menulis sebelum itu. Menulis di
   tengah-tengah dua register adalah cara lahirnya copy yang "aman tapi
   lebay".
3. **DRAFT** — apply the register consequences (pronouns, verb forms,
   greeting/signoff, emoji budget) plus the stay-English word list in
   [`references/codeswitch.md`](references/codeswitch.md). Surface norms
   from [`references/platforms.md`](references/platforms.md).
   *Indonesian:* Terapkan konsekuensi register (kata ganti, bentuk verba,
   sapaan, jatah emoji) plus daftar kata yang tetap bahasa Inggris di
   codeswitch.md; norma per media dari platforms.md.
4. **TELLS CHECK** — check the draft against every entry in
   [`references/tells.md`](references/tells.md). Each hit: **fix the line**
   (never delete it silently).
   *Indonesian:* Periksa draf terhadap semua entri tells.md. Setiap
   temuan: perbaiki barisnya — jangan menghapusnya diam-diam.
5. **POLISH + TAG** — deliver the copy, then a tag block:

```
register: <chosen> · surface: <surface> · checked: id-copy@<version>
⚠️ hand to a native Indonesian reader before publishing.
```

   *Indonesian:* Serahkan copy-nya, lalu blok tag di atas — lengkap dengan
   pengingat native reader-nya.

## Honesty

This skill supplies rules, judgment calls, and sourced examples — it
sharpens output but replaces no native ear. The final call belongs to a
human Indonesian reader — pair it with `id-reader` for a verdict before
publishing.

*Indonesian:* Skill ini memberi aturan, pertimbangan, dan contoh
bersumber — membuat hasil lebih tajam, bukan menggantikan telinga
penutur asli. Putusan akhir ada pada pembaca Indonesia manusia.

## Extending

- New tell → `references/tells.md` (one entry: tell · why it fails · fix ·
  good/bad pair).
- New surface → `references/platforms.md`.
- Slang-bearing content carries `status: evergreen | dated <date>`.
  Refresh dated entries; never trust them blind.

## Scope (v1)

Marketing copy, taglines, WhatsApp/IG captions, product copy. **Out of
scope:** long-form, blog, UX microcopy, regional dialects beyond
Jakarta-centric gaul, English output. Two clarifiers: using regional
ADDRESS conventions (Kak/Bunda/Akang per platforms.md) is not dialect
writing — it's in scope; and the eval deliberately stress-tests surfaces
at the edge of scope (a blog opening, a headline) — those runs demonstrate
the tells hold beyond the comfortable center, they don't widen the
contract.
