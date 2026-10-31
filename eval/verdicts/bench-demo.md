# id-bench — demo run (2026-10-31, loop 5)

The bench's own receipt is this: **all four loop-5 A/Bs in this folder
were run under id-bench's protocol** (which is eval/run.md's protocol,
extracted). This file records how they map onto the protocol's four
steps, so the bench is demonstrated on real work rather than a toy.

## SETUP (per the four A/Bs)

- Variants: 2 per sample (Arm A = no-skill, Arm B = with-skill), same
  brief/input per pair → content confound controlled.
- Persona set: existing + new personas (dev-docs, tiktok-viewer,
  fb-user).
- Question: "which version would the reader act on?"

## JUDGE

- Fresh persona agents per sample; each saw ONLY its persona file +
  two variants labeled VERSION 1/2; no tells list; no other judges'
  output; forced PICK with hesitation notes kept visible (three samples
  carry them: longform-2's tie-break note, social-1's, social-2's).

## REPORT

| Skill | Samples | Skill-arm picks | Notes |
|---|---|---|---|
| id-translate | 2 | 1/2 | loss = UI-path language rule (now structures.md #21) |
| id-humanizer | 2 | 0/2 | loss = closing formulas (now voice.md rule) |
| id-longform | 2 | 1/2 | loss = audience-age register weighting (now SKILL.md INTAKE) |
| id-social | 2 | 2/2 | platform rules quoted back by both judges |

Aggregate: **4/8 across 8 forced picks by 8 fresh blind judges.**
n=8 total but skills differ — per-skill n=2. **Directional, not
statistics**, and that sentence is mandatory per protocol.md.

## ARCHIVE

Every arm retained verbatim: translate + humanize arms in their own
files above; longform + social full arm texts and ALL 16 verdict
JSONs (eight judges, VERSION 1+2 each — hesitation notes included,
visible) in
[`loop5-arms.md`](loop5-arms.md). Orders used are recorded in each
file. No reruns occurred.

## What this run proves about the bench itself

- Forced picks surfaced weak preferences (hesitation notes from three
  samples are retained in the JSONs and the longform-2 tie-break note —
  visible, not erased).
- lost_me_at did its job: both translate losses/picks trace to a
  single UI-path line each — the bench localized the defect, which is
  what makes a fixable finding (and all three fixes landed in the
  skill files the same day).
- One-builder disclosure: repeated here — one builder authored
  samples, personas, skill files, and both arm prompts.

## Loop-7 addendum (same date, second bench round)

The loop-7 sample expansion ran 15 more A/Bs under this same protocol
(3 new samples × 5 skills, fresh judges, orders recorded):
id-copy 3/3, id-translate 2/3, id-humanizer 3/3, id-longform 3/3,
id-social 2/3 → **13/15**. All-time aggregate across loops 3+5+7:
**19/25 skill-arm picks by 25 fresh blind judges.** Losses kept:
translate-4 (the UI-path rule's documented per-reader cost — no new
rule) and social-3 (CTA-reason rule, encoded into tiktok.md
same-day). The same round also ran the protocol's first
non-skill-vs-baseline comparison — the instruction-language A/B
(English-guided vs Indonesian-guided id-copy, n=3, Indonesian-guided
3/3) — recorded in [`instrlang-ab.md`](instrlang-ab.md); all arms
retained verbatim in [`loop7-arms.md`](loop7-arms.md). No reruns
occurred in either round.
