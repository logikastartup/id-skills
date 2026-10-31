---
name: id-humanizer
description: Rewrite stiff, AI-sounding Indonesian so it reads like the same human wrote it — any genre (reports, essays, posts, email). Kills AI-Indonesian tells while preserving meaning AND the writer's voice; every change is named in a change list. Use when Indonesian text exists and reads machine-made. Not for generating new content (id-copy) or translating (id-translate).
---

# id-humanizer — de-slop Indonesian, keep the writer

**Router only.** Components under `references/`; each flow step carries
a one-line Indonesian gloss (English line = the rule).

## The one distinction that makes this skill

`id-copy` **generates** (you choose a register, it drafts). `id-translate`
**translates** (a source in another language exists). Here, the text
already exists in Indonesian and already has a register — so this flow
**detects** register and preserves voice instead of choosing and
drafting.

## Flow (always in order)

1. **DETECT** — identify the text's current register (evidence:
   pronouns, particles, vocabulary) and its genre. State both.
   Detection method: the register ladder
   ([`references/register.md`](references/register.md)) gives the
   EXPECTED level per surface (its decision rules); your evidence gives
   the OBSERVED level — mismatch between them is itself tell #3.
   *Indonesian:* Kenali register teks ini sekarang (bukti: kata ganti,
   partikel, kosakata) dan jenis tulisannya. Sebutkan keduanya. Register
   yang diharapkan menurut tangga register vs yang terlihat di bukti —
   kalau beda, itu sendiri tell #3.
2. **VOICE LEDGER** — inventory what must survive, per
   [`references/voice.md`](references/voice.md): the writer's habits
   (sentence rhythm, signature words, humor, formatting) AND the
   meaning ledger (facts, numbers, names, claims — inviolate).
   *Indonesian:* Catat yang harus selamat: kebiasaan penulisnya dan
   isi maknanya. Fakta dan angka tidak boleh berubah.
3. **TELLS PASS** — run [`references/tells.md`](references/tells.md)
   over the text. Every hit is **fixed, never deleted silently** — the
   line is rewritten with its content intact (zero-information
   boilerplate may be cut per voice.md's closing-formula rule).
   *Indonesian:* Periksa dengan daftar tell. Setiap temuan diperbaiki
   — bukan dihapus diam-diam.
4. **VOICE CHECK** — re-read the result against the voice ledger. If a
   fix erased the writer, take the lighter fix. If a "fix" would change
   meaning, it is not a fix — flag it instead.
   *Indonesian:* Baca ulang hasilnya. Kalau perbaikan malah menghapus
   gaya penulisnya, pakai perbaikan yang lebih ringan.
5. **DELIVER + TAG** — cleaned text + change list (every change named:
   what · which tell · why), then:

```
register detected: <r> · genre: <g> · changed: <n> lines ·
checked: id-humanizer@v1
⚠️ hand to a native Indonesian reader before publishing.
```

   *Indonesian:* Serahkan hasilnya plus daftar perubahan — apa, tell
   yang mana, kenapa.

## Honesty

This skill removes the machine accent; it cannot add a personality the
text never had. Text with no human underneath stays hollow — that is a
finding to report, not a bug to hide.

*Indonesian:* Skill ini membuang aksen mesin; ia tidak bisa menambahkan
kepribadian yang memang tidak ada di teksnya.

## Scope (v1)

**In:** any Indonesian prose you didn't generate with `id-copy` —
reports, essays, announcements, posts, email, chat transcripts.
**Out of scope:** generating new copy (→ `id-copy`); translating
(→ `id-translate`); changing meaning, tone-of-record, or legal/medical
wording (flag, don't rewrite); non-Indonesian text.
