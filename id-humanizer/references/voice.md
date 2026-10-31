# voice.md — the voice ledger + editing backbone (id-humanizer)

`component: id-humanizer` · Editing doctrine cited at bottom;
native-lens critic pass 2026-10-31 (gauntlet loop 6).

The voice ledger is what makes humanizing different from homogenizing.
You are not making the text sound like a generic human — you are making
it sound like **its writer, without the machine layer**. The doctrine
line that governs everything below: **"penyunting naskah bukanlah
penulis naskah!"** — the editor serves the writer, never replaces them
(Haryadi, Keredaksian dan Penyuntingan, 2021). The operational test
(Cell Press CrossTalk): if the author would say "this doesn't sound
like me," the edit failed; when several fixes are correct, pick the one
closest to the author's phrasing; when unsure, flag rather than
rewrite.

## What to inventory (before touching a line)

1. **Sentence rhythm** — average length + variance. A writer of short
   punchy sentences must still write short punchy sentences after the
   pass. A long-flow writer keeps long flows.
2. **Signature vocabulary** — words this writer actually uses
   (including deliberate informality). Do not "upgrade" them to baku
   unless the word IS the tell.
3. **Humor and warmth markers** — jokes, asides, small confessions.
   These are voice gold; they die first in careless edits. Protect
   them explicitly.
4. **Formatting habits** — dash style, emoji use, paragraph length,
   ALL-CAPS for emphasis. Keep unless they collide with a tell.
5. **Pronoun choice** — saya/aku/gue/kami: this IS the voice. Fixing a
   register mismatch may require changing it; if so, that is a big
   change — name it in the change list, don't smuggle it.

## The meaning ledger (inviolable)

- Facts, numbers, dates, names, links: never "improved", never rounded,
  never reinterpreted.
- Claims keep their strength. Humanizing is not editing an argument.
- Terms of art stay.
- If a sentence's meaning is unclear and the fix requires choosing an
  interpretation — flag it; don't choose silently.

## Rules of the pass

- **Fix, never delete.** A cheesy line still carries information;
  rewrite it carrying the same information.
- **Lightest fix wins** when two fixes both kill the tell: the one that
  disturbs the voice ledger least.
- **One tell can be voice.** A writer's genuine quirk that resembles a
  tell (they really do love ellipses…) is theirs to keep; note it,
  don't sand it. When unsure, keep and note.
- **Formulaic closers are tells, not voice.** "Demikian pengumuman ini
  kami sampaikan; atas perhatian dan kerja sama… kami ucapkan terima
  kasih" and its cousins are boilerplate, even though they feel like
  genre tradition. Readers flag them as the machine layer every time
  (loop-5 eval: both humanize judges dinged them; one read the kept
  formula as "surat dari kantor kelurahan"). Default: cut or compress
  to one warm plain line ("Terima kasih.") — keep the full formula
  ONLY for official correspondence that formally requires it (surat
  dinas, legal notices). The voice ledger must never classify
  boilerplate as voice. Note: cutting zero-information boilerplate is
  NOT the forbidden "silent deletion" — the no-delete rule protects
  lines that carry content; formulas carry ceremony. When in doubt,
  compress (keep a one-line terima kasih) rather than cut entirely.
- **Report hollow text.** If after the pass the text reads clean but
  empty — no specifics, no person anywhere — say so. The skill removes
  slop; it doesn't invent a writer.

## Change list format (delivery requirement)

| # | Line (short quote) | Tell / rule | What changed |
|---|---|---|---|
| 1 | "…dalam era digital yang serba cepat ini…" | tells #1 era-opener | dropped the staged era frame; kept the sentence's actual point: X |

Every change appears. "Minor edits throughout" is not a change list.

## Editing backbone (kalimat efektif, used with the tension in mind)

The standard Indonesian line-editing frame — syarat: has subject +
predicate, not wordy, not ambiguous; ciri: kepadanan, keparalelan,
kehematan, kepaduan, kelogisan, kecermatan (doctrine via Badudu et
al.). Applied per-sentence it cleans; applied uniformly it flattens —
uniform S-P-O rhythm is itself a machine tell (see id-longform
structure.md §2). Line-edit, then re-read for rhythm.

Fixes with receipts (Binus Malang / Boros kata doctrine):

| Waste (boros) | Fix |
|---|---|
| *(baku rows apply only when the surface's ladder level is 1–2 — on casual surfaces "meeting/jam" stay, the tell is mismatch not baku)* | |
| "Naik ke atas tangga" | "Naik tangga" (kehematan) |
| "demi untuk", "agar supaya" | "demi", "agar" |
| "para hadirin" | "hadirin" (already plural) |
| "Meeting akan dimulai jam sepuluh" | "Rapat akan dimulai pukul sepuluh" (kata baku) |
| "melakukan pengujian terhadap" | "menguji" (verba > nominalisasi) |

"yang mana / hal mana" as relative connector: taught as non-baku in
academic-writing materials (source-level confidence low — flagged,
owner verify). Emotion marks are not errors: text that is "terlalu
proper dan minim emosi" reads machine (Mahendradita) — a writer's
occasional "!" or "…" survives this pass.

## Doctrine sources

- Cell Press CrossTalk (Kerry Evans), "Preserving author voice during
  copyediting" — invisible editing, the "sounds like me" test, err
  toward query.
- Haryadi (2021), Buku Ajar Keredaksian dan Penyuntingan, UM
  Palembang — editor ≠ author; an editing checklist in that tradition lists
  "gaya penulis" as a thing the editor must attend to.
- Kalimat efektif / boros kata: id.wikipedia (Badudu, Arifin & Tasai,
  Joko Widodo); binus.ac.id/malang kehematan + kata baku examples.
- Machine-tell side (what this pass removes): Batam Pos ChatGPT-phrase
  list; Mahendradita (Medium) punctuation/rhythm tells; BuildWithAngga
  ban-list — all density-weighted weak signals, never proof.
