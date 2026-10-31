# ledger.md — the parity ledger (id-translate)

`component: id-translate` · method proven in this repo's own loop 4
(gauntlet-progress.md): the EN↔ID README pair is gate-checked against
these rules before each commit (id-gate §7 — manual discipline, no CI
yet). Alignment with the standard Indonesian QA
triad — keakuratan (accuracy), keberterimaan (acceptability),
keterbacaan (readability; Nababan) — this ledger owns the first; the
flow's other steps own the other two.

The ledger is extracted from the source **before** drafting and
re-verified **after**. It is what makes this translation instead of
transcreation: the information is fixed; only the expression moves.

## What goes in the ledger

Extract each of these as a numbered line:

1. **Claims with strength** — every assertion, with its qualifier
   ("verified", "documented", "some", "often", "both times"). The
   qualifier is part of the claim.
2. **Numbers, dates, names, versions** — verbatim, always. "2/2",
   "2026-10-31", file names, semver. **UI paths** carry one extra
   decision: render them as the app's actual UI shows them (English UI
   → keep English; Indonesian-localized UI → the Indonesian menu
   names); when you can't verify the app's language, keep the source
   form and flag it (see structures.md #21 — reader-caught, loop 5).
3. **Links and references** — targets are inviolate; link text may
   read naturally.
4. **Hedges and honesty markers** — "directional, not statistics",
   "pending", "one honest failure, kept". These ride along even when
   they make the target text less flattering.
5. **Quantifiers** — every "all/every/none/always". Each gets a
   truth-check note: is the universal actually true of the thing it
   describes? (This repo shipped "verified against KBBI" as a false
   universal that survived three review rounds — the ledger exists so
   the next one dies at step 2.)
6. **Disclosures** — anything disclosed in one place that must stay
   symmetric (machine-authorship notes, banner mentions). Asymmetric
   disclosure is a parity break.
7. **Terms of art** — register/tell/verdict-class vocabulary that must
   not be translated into near-synonyms.

## Rules

- Nothing **drops**. Nothing is **added**. Nothing **strengthens** or
  **softens**. A claim missing from the target is a defect equal to a
  wrong number.
- Hedged source → hedged target, same hedge weight. "often" is not
  "sometimes" is not "always".
- If the target language exposes that a source claim is false or
  inflated, flag it in the delivery note — do not silently "fix" the
  source's meaning, and do not carry a lie cleanly either.

## Verification pass (after drafting, before delivery)

Re-walk the ledger line by line against the draft:

- each claim present at same strength? each number verbatim?
- each link live in the target (or the equivalent reference)?
- each hedge riding along? each universal still true?
- disclosures symmetric if the translation ships next to its source?

Record the result in the tag block ("ledger: N/N lines verified").

## Worked micro-example (from this repo)

Source: "…verified against KBBI" (unqualified universal).
Draft 1: "semua diverifikasi ke KBBI" — ADDED quantifier, still false.
Fixed: "dicek ke KBBI atau diberi penanda sumbernya" — matches what the
referenced artifact actually does. The ledger would have caught it at
step 2; the critics caught it at review. Both hurt; the ledger is
cheaper.
