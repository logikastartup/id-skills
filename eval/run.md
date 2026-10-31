# eval — the benchmark (how this skill earns trust)

The skill ships with receipts: real cheesy-AI-Indonesian samples, rewritten
through `id-copy`, judged before/after by `id-reader` personas — plus a
blind A/B against the same model without the skill. Per-skill before/after
exhibits — quoted pairs with the honest scores — live in `before-after/`.

## Per-skill evals (expansion skills, loop 5)

Same rules as above (fresh judges, blind VERSION 1/2 labels, per-sample
randomization recorded, no-rerun, arms retained, co-evolution +
authorship disclosed, n named). All judges emit the `id-reader` verdict
JSON + a forced PICK. Loop 5 gave each expansion skill n=2; loop 7
added 3 more samples per skill (n=5 total; id-copy n=5 via loops 3+7)
→ results are **directional** by construction.

| Skill | Inputs (samples/) | Arm A (no skill) | Arm B | Blind judges |
|---|---|---|---|---|
| id-translate | `translate-1.md`, `translate-2.md` (EN sources, embedded prompts) | "translate these two texts into natural Indonesian" — no repo access | loads `id-translate/SKILL.md` + components, full flow | dev-docs (t-1) · fb-user (t-2) |
| id-humanizer | `humanize-1.md`, `humanize-2.md` (stiff ID inputs) | "perbaiki agar terdengar lebih natural dan manusiawi" | loads `id-humanizer/SKILL.md` | fb-user (h-1) · dev-docs (h-2) |
| id-longform | `longform-1.md`, `longform-2.md` (briefs) | "tulis dari brief ini" | loads `id-longform/SKILL.md` | dev-docs (lf-1) · fb-user (lf-2 — audience is pemilik toko) |
| id-social | `social-1.md`, `social-2.md` (briefs) | plain write | loads `id-social/SKILL.md` + the one platform file | tiktok-viewer (s-1) · startup-linkedin (s-2) |
| id-bench | demo = the loop-5 + loop-7 A/B runs, recorded per its own protocol | — | — | (the runs themselves are the artifact: `verdicts/bench-demo.md`) |
| instrlang (loop 7) | `copy-3.md`–`copy-5.md` (shared with id-copy's loop-7 run) | English-guided id-copy (full skill) | Indonesian-guided twin `eval/instrlang/id-copy-id/` (same rules, instruction language the only variable) | wa-buyer (c-3) · shopee-ibu (c-4/5) — **ID-guided 3/3**, see `verdicts/instrlang-ab.md` |

Arm B's process/verification notes are stripped before judging — arms
are compared on text alone. Records land in `verdicts/<skill>-ab.md`
(both arms verbatim + all verdict JSONs + the order used).

## Inputs

- `samples/wild-*.md` — wild-caught Indonesian text showing documented AI/
  MT patterns (a government blog, a diary post, the opener-pattern corpus,
  a wiki-paste, a headline). Each carries its source URL + capture date
  where one exists; corpus-level captures say so.
- `samples/gen-*.md` — reproducibly generated: the exact generation prompt
  is embedded in the file, so anyone can regenerate equivalent cheese with
  any base model and re-run this benchmark.

## Procedure (per sample)

1. **Baseline verdict** — a FRESH agent loads ONLY the persona file + the
   raw sample (it must not see `id-copy/references/` — no circular
   grading) and emits the `id-reader` verdict JSON.
2. **Rewrite** — run `id-copy` on the sample: full router flow, register
   chosen explicitly for the sample's surface + audience.
3. **After verdict** — another FRESH agent, same persona, rewrite only.
4. **Record** — `verdicts/<sample>.md`: before JSON · rewrite · after JSON
   · one honest line on what changed in the reader's ear.

## Rules

- Verdict agents never see the tells list, the rewrite process, or each
  other's output.
- If the rewrite doesn't move `understood/trusted/would_act`, that is a
  FINDING about the skill, not a reason to rerun until green.
- Wild samples carry their URL; if a source dies, the sample stays with a
  note (they are evidence, not links).

## Blind A/B protocol (see verdicts/ab-test.md + ab-arms.md)

1. Two held-out generated samples (gen-*.md, prompts embedded).
2. Arm A: fresh agent rewrites from a plain instruction ("rewrite so it
   reads natural"), no access to id-skills. Arm B: fresh agent loads
   id-copy fully and follows it. Same base model both arms.
3. Strip Arm B's process notes; both arms judged on copy alone.
4. Fresh persona verdict agents judge BOTH outputs blind as "VERSION 1/2",
   order randomized per sample; they end with a forced PICK.
5. **No-rerun rule applies to arms too:** Arm B is not re-rolled until it
   wins. A sample where Arm A wins is a finding about the skill, recorded.
6. Retain everything: both arms' full outputs + all verdict JSONs
   (ab-arms.md). Known limits to disclose: personas and tells co-evolved
   ([eval] entries derive from earlier verdicts), and one builder authored
   personas, tells, and both arms' prompts — treat A/B results as
   directional, and extend with more samples/personas for statistics.
