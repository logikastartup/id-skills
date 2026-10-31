# protocol.md — the blind A/B protocol (id-bench)

`component: id-bench` · Extracted from this repo's `eval/run.md`, which
produced `eval/verdicts/ab-test.md` + `ab-arms.md` — read those for a
worked example of every rule below except the hesitation path (those
judges all picked decisively).

## Arm construction

- Variants must share intent (same brief, same information budget) —
  differences in CONTENT are confounds, not results.
- Skill-vs-baseline arms: baseline = plain instruction ("rewrite so it
  reads natural"), NO access to skill files. Skill arm = full router
  flow. Same base model both arms — say which model.
- Strip process notes / verification notes from skill-arm output before
  judging: arms are judged on text alone.

## Blinding + randomization

- Judges see variants as "VERSION 1 / VERSION 2" only. No arm names,
  no provenance, no hints in the prompt.
- Presentation order is randomized PER SAMPLE and the actual order used
  is recorded in the archive (order effects are real; hiding the order
  you used is worse than a possible order effect).
- Each judge sees exactly one persona + the variants for its sample.
  Never both personas' outputs, never the tells list, never other
  judges' verdicts (no anchoring, no circular grading).

## Judging

- Persona agents emit the `id-reader` verdict JSON (understood /
  trusted / would_act / lost_me_at / cheese_flags / in_my_words /
  verdict_note) + end with a forced PICK.
- A judge that cannot pick is told: pick anyway, note the hesitation in
  verdict_note. (Forced picks surface weak preferences; hesitation
  stays visible.)

## Reporting + honesty lines (mandatory)

- Report the table AND retain every JSON verbatim.
- Sample count is stated with the result. Below ~10 picks: "directional,
  not statistics" appears in the same breath.
- Disclose co-evolution: if personas were tuned using earlier runs of
  the same arm family, say it.
- Disclose authorship coupling: if one author wrote the variants AND
  the personas AND the prompts, say it — that is this repo's own
  situation and it is printed on every bench result we ship.

## No-rerun rule

An arm is not re-rolled until it wins. A losing skill-arm result is
recorded as a finding about the skill (that is how this repo's eval
kept an honest failure in `results.md`). Reruns are allowed ONLY as a
new, separately-reported experiment with new samples.

## What a bench result can and cannot prove

CAN: directional preference under specific personas; which lines lost
readers (lost_me_at is often more valuable than the pick).
CANNOT: statistical superiority at small n; anything about readers the
persona set doesn't contain; anything about quality dimensions the
verdict JSON doesn't measure.
