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
- **`id-reader`** — read the copy *as a specific Indonesian reader*
  (bargain-hunting marketplace shopper, startup LinkedIn reader,
  WhatsApp-group buyer) and emit a structured verdict. Readers grade by ear from their persona, never
  against the tells list — the two skills share no checklist (one author
  built both; the A/B honesty notes say what that does and doesn't cover).

Expansion skills (2026-10-31 — four with their own two-sample blind
A/Bs, receipts in `eval/verdicts/`; `id-bench`'s receipt is the demo
mapping there):

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

Examples and rules carry their source — KBBI entries verified live, real
brand campaigns, documented template corpora, dated slang statuses — and
everything unsourced is marked as such (`pattern-level`, `[inf]`).
The repo ships with **`eval/`** — wild-caught and reproducibly-generated
AI-Indonesian samples, rewritten through `id-copy`, with before/after
reader verdicts by persona (including one honest failure, kept) — and a
**blind A/B**: the same model rewrote held-out samples with and without
the skill; persona readers, blind and order-randomized, picked the
skill-guided version both times ([`eval/verdicts/ab-test.md`](eval/verdicts/ab-test.md)).
Re-run it yourself; the recipe is in [`eval/run.md`](eval/run.md).

These skills sharpen output; they replace no native ear. Every `id-copy`
output carries "hand to a native Indonesian reader before publishing".

## Results

Same model, with vs without the skill — blind persona readers:

| Sample | Without skill | With skill | Blind pick |
|---|---|---|---|
| WA promo (gen-1) | trusted ✗ · would_act ✗ | ✓ · ✓ | skill version |
| IG caption (gen-2) | trusted ✗ · would_act ✗ | ✓ · ✓ | skill version |

Wild rewrites: 4 of 5 samples flipped every verdict; one honest failure
kept (wild-3). Full outputs, uncropped:
[`eval/verdicts/ab-arms.md`](eval/verdicts/ab-arms.md) ·
[`eval/verdicts/results.md`](eval/verdicts/results.md). n=2, blind,
order-randomized — directional, not statistics.

Expansion skills (2026-10-31, loop 5): **4/8 skill-arm picks** across
four two-sample A/Bs — id-social 2/2, id-translate 1/2, id-longform
1/2, id-humanizer 0/2 (kept; both its losses produced the skill's
closing-formula fix the same day). Same protocol, same honesty rules:
[`eval/verdicts/translate-ab.md`](eval/verdicts/translate-ab.md) ·
[`humanize-ab.md`](eval/verdicts/humanize-ab.md) ·
[`longform-ab.md`](eval/verdicts/longform-ab.md) ·
[`social-ab.md`](eval/verdicts/social-ab.md).

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
eval/              samples → rewrites → verdicts; re-runnable
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
([timai.id](https://timai.id)) with agent tooling; the owner's native
correction pass over personas, examples, and the repo's Indonesian prose
(README.id.md included — machine-written) is part of finalizing v1 (the
personas carry their banner until then). Slang ages: check
`codeswitch.md` dates before trusting any slang-bearing line.

## License

MIT — copy the skills, ship better Indonesian.
