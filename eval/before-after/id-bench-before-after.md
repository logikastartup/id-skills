# id-bench — before / after

id-bench is this repo's evaluation discipline, productized: blind
persona judges, randomized recorded orders, forced picks, hesitation
notes kept visible, all arms retained verbatim. Its demo receipts are
the repo's own eval rounds, run per its protocol. Aggregate across
loops 3+5+7: **19/25** skill-arm picks by 25 fresh blind judges —
every loss localized to a line and either fixed or recorded as a
rule's known cost.

## Before (the usual way two texts get compared)

Two versions, a hallway opinion, a winner by vibes. The preference may
be real, but nothing is recorded: no blinding, no order randomization,
no retained arms — nothing anyone can audit, re-run, or learn a
fixable lesson from.

## After (a bench run)

The actual REPORT table from the loop-5 run, verbatim:

| Skill | Samples | Skill-arm picks | Notes |
|---|---|---|---|
| id-translate | 2 | 1/2 | loss = UI-path language rule (now structures.md #21) |
| id-humanizer | 2 | 0/2 | loss = closing formulas (now voice.md rule) |
| id-longform | 2 | 1/2 | loss = audience-age register weighting (now SKILL.md INTAKE) |
| id-social | 2 | 2/2 | platform rules quoted back by both judges |

Every pick came from a fresh persona judge who saw only its persona
file + two unlabeled variants (VERSION 1/2), order randomized per
sample and recorded, forced PICK. Hesitations stay in the record —
the longform-2 tie-break, verbatim:

> "Version 1 is the better argument and Version 2 is the better
> conversation, and I buy from conversations. PICK: VERSION 2"

The diagnostic work was done by `lost_me_at`: both translate picks
trace to a single UI-path line each, the humanizer losses to specific
closing lines, the longform loss to one register decision. That
localization is what turned losses into fixes instead of vibes.

n=25 total picks across three rounds (loops 3, 5, 7 — per-skill n=5)
— **directional, not statistics** (that sentence is mandatory in
every bench report). Loop 7 also ran the bench's first
non-skill-vs-baseline experiment through the same protocol: the
instruction-language A/B (English-guided vs Indonesian-guided id-copy
— Indonesian-guided 3/3; record:
[`instrlang-ab.md`](../verdicts/instrlang-ab.md)). Protocol:
[`id-bench/references/protocol.md`](../../id-bench/references/protocol.md) ·
demo mapping: [`eval/verdicts/bench-demo.md`](../verdicts/bench-demo.md) ·
all arms + all JSONs: [`loop5-arms.md`](../verdicts/loop5-arms.md) ·
[`loop7-arms.md`](../verdicts/loop7-arms.md)
