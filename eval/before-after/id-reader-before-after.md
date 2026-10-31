# id-reader — before / after

id-reader is the judging half of the repo: a specific Indonesian
reader persona reads the copy once, on their phone, and emits a
structured verdict — `understood / trusted / would_act`, the exact
line that lost them (`lost_me_at`), cheese flags, and what the copy is
actually saying in their words. Readers grade by ear, never against
the tells list — no circular grading with id-copy.

## Before (the copy, as the reader met it)

Wild sample 4 — an AI-FAQ paste about ChatGPT posted where a
marketplace shopper would scroll past it. The persona (shopee-ibu) had
one read, and her verdict localized the failure to line two:

> lost_me_at: "ChatGPT adalah sebuah chatbot yang dikembangkan oleh
> OpenAI, dan memiliki kemampuan yang sangat luas."

Her words: *"dua baris ini suasananya seperti dosen ngajar, bukan
orang ngobrol. Tidak ada angka, tidak ada bukti… cukup menggeser ke
atas lagi."* Verdict: understood ✓, trusted ✗, would_act ✗.

## After (the rewrite, re-read blind by the same persona)

id-copy's rewrite, then a FRESH agent loading only the persona file:

> "ChatGPT itu apa ya? Singkatnya: kita ngetik, dia jawab. Kayak chat
> sama orang paling sabar di dunia. … Yang perlu diingat: jawabannya
> kadang salah, jadi info penting selalu dicek ulang ya, Kak."

Same reader, second read: understood ✓, trusted ✓, would_act ✓ — and
the trust landed on the honesty caveat: *"sama rasanya kayak seller
yang jujur bilang 'warna bisa beda dikit sama foto'… aku baca sampai
habis dan malam ini aku coba tanya menu seminggu."*

## The honest failure (wild-3, kept)

On staged openers the reader taught the skill its limit — rewrites
that manufactured "concrete" scenes still failed: *"Three costumes of
the same manufactured stress scene… a mood scene that describes
everyone describes no one…"* Encoded into tells.md #1: a replacement
hook must be lived or specific to a real speaker. Across the five wild
samples, 4 of 5 flipped every verdict; wild-3 stands as the v1 limit.

## Why this skill matters

Every A/B table in this repo is id-reader output: the picks, the
`lost_me_at` localizations that turned losses into fixable findings,
the hesitation notes. It is the repo's instrument panel — and its
personas are ordinary readers, not copywriting theory.

All verdict JSONs: [`eval/verdicts/results.md`](../verdicts/results.md)
+ per-sample files there · this sample's full record:
[`wild-4-wikipedia-paste.md`](../verdicts/wild-4-wikipedia-paste.md),
failure: [`wild-3-opener-family.md`](../verdicts/wild-3-opener-family.md)
· input: [`wild-4-wikipedia-paste.md`](../samples/wild-4-wikipedia-paste.md)
