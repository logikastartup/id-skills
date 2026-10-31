# id-skills

Agent skills for the Indonesian market — copy that reads like a person
wrote it, judged by readers who'd actually see it.

[README Bahasa Indonesia →](README.id.md)

Global LLMs writing Indonesian produce a recognizable accent — *"AI
Indonesian"*: stiff textbook baku, calqued English metaphors, cheese
overload, and register blindness (Anda where Kak belongs). These skills
attack it from two sides:

- **`id-copy`** — write and fix Indonesian marketing copy. Forces an
  explicit register choice, drafts against a documented tells blacklist,
  applies code-switch rules (which words stay English — verified against
  KBBI or source-marked), per-platform norms.
- **`id-reader`** — LLM persona agents read the copy *as a specific
  Indonesian reader*
  (bargain-hunting marketplace shopper, startup LinkedIn reader,
  WhatsApp-group buyer) and emit a structured verdict. Readers grade by ear from their persona, never
  against the tells list — the two skills share no checklist (one author
  built both; the A/B honesty notes say what that does and doesn't cover).

Expansion skills (2026-10-31 — four with their own five-sample blind
A/Bs across loops 5+7, receipts in `eval/verdicts/`):

- **`id-translate`** — EN→ID translation that reads originally-written:
  a parity ledger (claims, numbers, hedges never drift) plus a
  transformation bank that kills calques and carried English structure.
- **`id-longform`** — Indonesian articles and newsletters: stated angle,
  sections-as-moves, against a documented scaffolding ban-list.
- **`id-humanizer`** — de-slop any Indonesian text while preserving the
  writer's voice. Every change named. Detects register instead of
  choosing it.
- **`id-social`** — TikTok scripts, LinkedIn, Facebook posts: one
  component per platform, slang always dated, register per platform.
- **`id-bench`** — blind persona A/B over any text variants: this repo's
  own evaluation discipline, productized.

## Why believe it

- **Sources ride along** — KBBI entries verified live, real brand
  campaigns, documented template corpora, dated slang statuses.
  Everything unsourced is marked (`pattern-level` = observed pattern,
  `[inf]` = inference), never silent.
- **`eval/` ships with the repo** — wild-caught and
  reproducibly-generated AI-Indonesian samples, rewritten through
  `id-copy`, with before/after reader verdicts by persona (including
  one honest failure, kept).
- **A blind A/B** — the same model rewrote held-out samples with and
  without the skill; persona readers, blind and order-randomized,
  picked the skill-guided version both times
  ([`eval/verdicts/ab-test.md`](eval/verdicts/ab-test.md)). Re-run it
  yourself: the recipe is in [`eval/run.md`](eval/run.md).

These skills sharpen output; they replace no native ear. Every `id-copy`
output carries "hand to a native Indonesian reader before publishing".

## Results

Same model both arms — the only difference is the skill. Fresh persona
judges, blind to labels, orders randomized, forced picks, no reruns.
Scores first, then taste the text: every skill has a before/after
exhibit in [`eval/before-after/`](eval/before-after) quoting the real
outputs. (n=5 per skill across eval rounds — directional, not statistics.)

The judges are LLM persona agents — fresh agents, same base model,
playing the persona — not human readers. Treat every score as evidence
about the text, not human-preference research.

### id-copy · 5/5

> **Without:** "Ada kabar baik buat hari ini: tas wanita premium
> koleksi terbaru lagi diskon spesial! … siapa cepat dia dapat ya,
> Kak!"
>
> **With:** "Lagi ada promo tas hari ini... kualitas premium tapi
> harganya bikin kaget (yang enak). Stoknya beneran dikit, makanya
> jangan lama-lama! … Mau langsung order atau lihat katalog dulu?"

Blind wa-buyer on the first: *"the broadcast I delete… Nobody who
ends a message like that has ever sent me a resi. Mute."* On the second:
*"a question I can answer in three words…"* In the earlier
wild-caught eval, 4 of 5 samples flipped; the one that didn't is
kept, failure and all.
→ [`id-copy-before-after.md`](eval/before-after/id-copy-before-after.md)

### id-translate · 3/5

> **Without:** "Kunci API Anda ada di menu **Pengaturan → Kunci**" —
> the English app's Settings → Keys, translated. Judge: *"You do not
> translate UI labels; that is the one string I need to click…"*
>
> **With:** "*API key* kamu ada di **Settings → Keys**. Cukup set
> sekali:" — clickable again, kamu register, parity ledger 7/7.

The loss was the same rule from the opposite direction: the skill
kept the English path in an Indonesian-localized app. One rule
learned from both sides — UI paths follow the app's actual UI
language (now structures.md #21).
→ [`id-translate-before-after.md`](eval/before-after/id-translate-before-after.md)

### id-longform · 4/5

> **Without:** an Anda-addressed essay with semicolon punchlines.
> Judge: *"I don't forward consultant-voiced think pieces to the team
> channel."*
>
> **With:** "Jumat, jam 10.14. … Rp449.000. Padahal harga promo
> Rp399.000 sudah berlaku sejak Kamis malam." Headings as assertions,
> a "write this today" section. Judge: *"This is the one I paste into
> the team channel."*

The loss is the register lesson: a 48-year-old shop owner read the
skill arm's kamu as junior — *"kalau sales datang ke toko saya pasti
bilang 'Pak'."* Audience age now weighs on register.
→ [`id-longform-before-after.md`](eval/before-after/id-longform-before-after.md)

### id-humanizer · 3/5 — 0/2, fixed, then 3/3

> **Input:** "…Demikian pengumuman ini kami sampaikan… atas perhatian
> dan kerja sama para pengguna, kami ucapkan terima kasih."
>
> **The skill arm kept the formula.** Blind reader: *"saya seperti
> membaca surat dari kantor kelurahan… penutup surat resmi yang
> distempel, bukan yang diucapkan orang."*

Both loop-5 picks went to the no-skill arm. Root cause identical in both:
formulaic closers mis-classified as voice. `voice.md` now rules
**"Formulaic closers are tells, not voice."** The fix postdates the
A/B — re-measuring takes new samples, per the no-rerun rule. Loop 7
brought those samples: **3/3 to the skill arm.** The fix, measured.
→ [`id-humanizer-before-after.md`](eval/before-after/id-humanizer-before-after.md)

### id-social · 4/5

> **Without:** "Anak Jatim, stop scroll dulu." … "Tag temenmu yang
> ngaku tahan pedes…" Judge: *"kayak page Facebook zaman 2021."*
>
> **With:** the crunch as the hook — "Balado level tiga, asli
> Bondowoso" over a chip snapped at the lens — and a CTA answerable in
> one word: "kamu tim level berapa?" Judge: *"itu bahasa TikTok, bukan
> bahasa iklan… saya langsung ketik '3' di komen, nggak perlu mikir."*

Both loop-5 judges quoted the platform rules back. Dated slang was
refused by the staleness rule. The loop-7 TikTok loss taught the
CTA-reason rule (state what answering gets the viewer), encoded
same-day into tiktok.md.
→ [`id-social-before-after.md`](eval/before-after/id-social-before-after.md)

### id-reader · the judging half

The verdict engine behind every result above: a persona reads once, in
character, and names the exact line that lost them. On an AI-FAQ
paste: *"suasananya seperti dosen ngajar… Tidak ada angka, tidak ada
bukti…"* → after the rewrite, same persona: *"malam ini aku coba tanya
menu seminggu."* Wild eval: 4 of 5 samples flipped; the miss is kept.
→ [`id-reader-before-after.md`](eval/before-after/id-reader-before-after.md)

### The instruction-language experiment · asked twice, answered both ways

The question that opened this repo: does writing the skill itself in
Indonesian improve the model's Indonesian? Loop 7 built a native
Indonesian twin of id-copy (same rules, same sources — instruction
language the only variable) and ran it blind against the English
skill: Indonesian-guided 3/3, its drafts read as MORE colloquial at
the same register — *"'Garing' bukan 'renyah'… 'tombol Beli Sekarang'
itu emang tombol yang ada di Shopee — gak nyasar."* Loop 8 built the
twin of a second skill, id-humanizer, and the answer flipped:
English-guided 2/3, with the Indonesian-guided arm trending formal —
one judge read its kept superlative apology as *"Mohon maaf yang
sebesar-besarnya — formula wajib surat pernyataan bank dan maskapai,
bukan bahasa pemilik toko kue"*. Aggregate across both skills: 4/6 —
a real effect on copy, not on humanizer. Migration stays parked; both
records are published as-is, loss included.
→ [`instrlang-ab.md`](eval/verdicts/instrlang-ab.md) ·
[`instrlang-ab-2.md`](eval/verdicts/instrlang-ab-2.md)

### id-bench · the harness

The discipline productized: blind judges, randomized recorded orders,
forced picks, hesitation notes kept, all arms retained verbatim. Its
demo receipts are the repo's own eval rounds — aggregate **19/25**
across loops 3+5+7, every loss localized to a line and either fixed
same-day or recorded as a rule's known cost. One judge's
recorded hesitation: *"Version 1 is the better argument and Version 2 is the
better conversation, and I buy from conversations…"*
→ [`id-bench-before-after.md`](eval/before-after/id-bench-before-after.md)

## Layout

```
id-copy/           the writing skill (thin router + 4 components)
  references/      register · tells · codeswitch · platforms  ← reusable
id-reader/         the verdict skill (protocol + personas/)
id-translate/      EN→ID with a parity ledger + transformation bank
id-longform/       articles + newsletters (angle · moves · ban-list)
id-humanizer/      de-slop any Indonesian text (voice ledger)
id-social/         tiktok · linkedin · facebook — one file per platform
id-bench/          the blind A/B harness (protocol + id-reader personas)
eval/              samples → rewrites → verdicts → before/after exhibits
```

Components are one-concern files, loadable on demand. SKILL.md routers
are bilingual — each flow step states the rule in English with a
one-line Indonesian gloss. Later id-* skills (ads research, more) reuse
the same components by versioned copy.

## Using the skills

Copy a skill folder into your agent's skills directory (Claude Code:
`~/.claude/skills/` or `.agents/skills/`; other agents: wherever skills
live). `id-copy` works standalone; `id-reader` pairs with it for
pre-publish verdicts. Each expansion skill works standalone too;
`id-bench` needs `id-reader`'s personas (copy both folders). Shared
components are versioned copies (`copied-from:` headers) — re-copy to
update, never fork-edit.

## Status

v1 candidate — built and evaluated 2026-10-31 by Bobby Heykal
([timai.id](https://timai.id)) with agent tooling. The native-check
pass over personas, examples, and the repo's Indonesian prose runs as
gauntlet loops, not a one-time blessing (loop 6, 2026-10-31: a
native-lens critic panel over the personas and the loop-5 skill
components, findings fixed — machine critics, not the owner's ear). Something read wrong to
you? That's an issue or a PR; corrections land in the repo. Slang
ages: check `codeswitch.md` dates before trusting any slang-bearing
line.

## License

MIT — copy the skills, ship better Indonesian.
