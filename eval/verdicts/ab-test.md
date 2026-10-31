# blind A/B — does id-copy measurably improve a model's output? (2026-10-31)

The question this repo's credibility rests on. Same base model both arms;
the only difference: Arm B loaded the full id-copy skill, Arm A rewrote
from plain instruction ("rewrite so it reads natural"). Verdict agents were
fresh persona readers judging BOTH outputs blind, order randomized, no
labels.

## Samples (held out from the earlier eval)

1. **gen-1** — WA bag-shop broadcast promo (reproducibly generated; prompt
   in `samples/gen-1-wa-promo.md`)
2. **gen-2** — IG coffee-shop caption, generated the same way ("Di era
   digital yang serba cepat ini… gaya hidup!… Jangan sampai kehabisan!")

## Results

| sample | Arm A (no skill) | Arm B (id-copy) | blind pick |
|---|---|---|---|
| gen-1 WA promo → wa-buyer | understood ✓ trusted ✗ act ✗ ("the broadcast I delete… Nobody who ends a message like that has ever sent me a resi. Mute.") | understood ✓ trusted ✓ act ✓ ("reads like an actual seller… Mau langsung order atau lihat katalog dulu? is a question I can answer in three words") | **B** |
| gen-2 IG caption → shopee-ibu | understood ✓ trusted ✗ act ✗ ("puitis, hangat, nol informasi… aku nggak bisa mampir ke sebuah vibes") | understood ✓ trusted ✓ act ✓ ("dipanggang kemarin, diseduh pas dipesan… klaimnya bisa dicek… aku beneran bakal tap bio-nya") | **B** |

Arm A — the SAME model without the skill — reproduced the documented tells
almost checklist-fashion: hype opener ("Ada kabar baik buat hari ini"),
worn urgency ("siapa cepat dia dapat", "Jangan sampai kelewatan!"), and a
staged mood-scene opener ("Hari yang terus berlari butuh satu jeda yang
enak") — the exact pattern tells.md #1 warns about. Arm B's drafts carried
explicit register choices (level 3 chat-santai; level 4 gaul hybrid), tells
passes, and the skill's honesty notes.

## What the A/B taught (encoded into tells.md)

- **#16**: "penawaran spesial" without naming the offer — flagged by BOTH
  blind readers independently, on both arms' outputs (even skill-guided
  drafts leaked it). Now an explicit tells-pass check.
- **Placeholders never ship** — literal "[Lokasi]" read as an unfinished
  post to the detail-noticing reader.

## Honesty notes

- n=2 samples, n=1 persona each. Directionally strong (2/2 flips, all
  verdict dimensions), not statistics. Re-run with more samples/personas —
  the protocol is in `run.md`.
- **Co-evolution:** the persona files and the tells taxonomy were built by
  the same author, and some tells ([eval] entries) derive from earlier
  persona verdicts — so blind readers partially echo the taxonomy even
  while blind to it. The two skills don't share a checklist, but they
  share an author. Treat results as directional, not independent.
- **Authorship coupling:** one builder wrote the personas, the tells, and
  both arms' instructions. The defense is retained artifacts (ab-arms.md)
  and the re-runnable protocol — anyone can re-run with different
  personas/models.
- **No-rerun rule covers the arms:** Arm B was not re-rolled until it won;
  a sample where Arm A wins would be recorded as a finding about the
  skill (none occurred in this run — which is itself worth re-testing).
- Arm B outputs included verification notes ("verifikasi diskon
  pembelian kedua benar-benar berlaku") — the skill's honesty bias working
  as designed, retained in ab-arms.md, stripped from the judged copy so
  both arms were judged on copy alone.
- Arm order was randomized (gen-1: B shown first; gen-2: A shown first);
  verdict agents saw "VERSION 1/2" only.
