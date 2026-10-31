# Loop-8 validity panel — the twin's pre-A/B gate (2026-10-31)

Two fresh critics reviewed `id-humanizer-id` BEFORE any arm ran:
a parity critic (rule-by-rule diff against `id-humanizer`) and a
native-register critic (is the instruction text natively written,
lugas, non-priming). Their reports are retained verbatim below —
they are the backing for instrlang-ab-2.md's validity claim.
Redaction note: absolute workspace paths quoted by the critics are
redacted to repo-relative form (the repo's private-leak gate forbids
absolute local paths in published files) — and one markdown link
shape inside a quoted finding was defused (same reason: the link
checker resolves quoted shapes as real links); wording otherwise
unaltered. The
builder's dispositions follow each report; every finding was fixed
(see "What was fixed") except none were refuted.

## Parity critic — VERDICT: PASS

(checklist + report verbatim)

> lens: PARITY (English-guided id-humanizer vs Indonesian-guided id-humanizer-id)
>
> checklist (pre-registered before semantic reading):
> - C1 Every parent rule present in twin, same content/strength (SKILL.md distinction/5-step flow/honesty/scope; voice.md 5 inventory items, meaning ledger, rules-of-the-pass incl. formulaic-closers surat-dinas exception + compress-not-cut default, change-list format, kalimat-efektif backbone incl. 5-row boros table + baku caveat row + yang-mana low-confidence flag + emotion-marks note; tag block metadata).
> - C2 No added/dropped actionable rules in the twin.
> - C3 Every doctrine/source citation preserved by name.
> - C4 Tells list and register ladder rule-identical, verified by mechanical diff chain: twin files vs id-copy-id's, and parent id-humanizer's vs id-copy's.
> - C5 All relative links inside the twin resolve.
>
> Verification performed:
> - C4 diff chain: diff of id-humanizer/references/tells.md vs id-copy/references/tells.md and register.md vs register.md → only the `copied-from: id-copy@v1` header lines differ; parents genuinely share components. diff of eval/instrlang/id-humanizer-id/references/tells.md and register.md vs id-copy-id's → only the 3-line provenance header differs (names id-humanizer instead of id-copy, matching each twin's own parent). Weights intact through the chain: em-dash LOW, "one tell = note; three+ or any of #1/#3/#4 = rewrite opening/register", formal-is-tell-only-on-mismatch, 5-level ladder, 4 ordered decision rules, Kak guidance, 3-item Never list — all present and identical in content.
> - C1/C2 semantic sweep of SKILL.md and voice.md line-by-line: distinction section, 5 flow steps in order, honesty section, scope in/out lists, 5 inventory items, 4 meaning-ledger bullets, all 5 rules-of-the-pass (incl. surat dinas / pemberitahuan hukum exception and "kalau ragu, padatkan... daripada memotong habis"), 4-column change-list table, syarat/ciri backbone, caveat row + 5 boros rows verbatim, yang mana/hal mana low-confidence flag, emotion-marks note, all 4 doctrine-source bullets — parity holds. Strength words (ONLY→hanya, never→jangan pernah, default→bawaan) carry over.
>
> findings:
> - [minor] id-humanizer-id/references/voice.md:5 (same pattern in tells.md:5 and register.md:4-5) — header says "aturan dan sumber sama dengan `../../../id-humanizer/references/voice.md`", but from `...\id-humanizer-id\references\` three `../` resolve to id-skills/eval/, where no `id-humanizer/` exists (verified: `NO eval/id-humanizer`); the parent is four levels up at id-skills/id-humanizer. These are backticked provenance path mentions, not markdown links, and the identical bug exists in id-copy-id's headers (`../../../id-copy/...`), so it is inherited, not twin-specific drift; no rule lives at the target. Fix: use `../../../../id-humanizer/references/*.md` in all three headers.
> - [minor] id-humanizer-id/references/tells.md:131-132 — "URL sampel liar bersumber ada di `../../../eval/samples/`" resolves to id-skills/eval/eval/samples (doubled `eval`); correct is `../../../../eval/samples/` (verified to resolve to id-skills/eval/samples). Parent's counterpart `../../eval/samples/` is correct from its location. Prose path mention in the sources note only. Fix: drop the extra `eval` segment.
> - [minor] id-humanizer-id/references/voice.md:114 — the doctrine-sources bullet renders the Cell Press test as 'uji "ini gaya saya"', dropping the negation that the parent's bullet has ("the 'sounds like me' test" = shorthand for "this doesn't sound like me"); the operative rule in the twin's body (voice.md:13-16) states it correctly as "ini bukan gaya saya", so no agent following the body acts differently. Fix: quote "ini bukan gaya saya" in the source bullet too.
>
> attempted-breaks:
> - Diffed both C4 chains mechanically (would have caught any verbatim-copy divergence): only provenance headers differ, both sides — held.
> - Counted and content-matched every rule container (5 flow steps, 5 inventory items, 4 ledger bullets, 5 pass rules, 5+1 boros rows, 16 tells, 3 weighting bullets, 5 ladder rows, 4 decision rules, 3 never-items, 4 voice source bullets): no dropped or added rule — held.
> - Hunted strength shifts on modals/hedges (only/never/default/must → hanya/jangan pernah/bawaan) and on the closers exception (surat dinas + legal notices → surat dinas + pemberitahuan hukum): no shift — held.
> - Resolved every relative markdown link from its own directory: twin SKILL.md's `../README.md` and three `references/*.md` links, tells.md's internal `[register.md]` pointing at `register.md`, and the parent's three links all resolve; the only failures were the header/sources path mentions above.
> - Looked for added rules that would confound the A/B: the twin's only additions are meta (description's "Artefak eksperimen bahasa instruksi..., bukan skill rilis" and the header pointer to ../README.md, which resolves); neither changes in-task behavior, and the tag block's `checked: id-humanizer-id@v1` (vs `id-humanizer@v1`) is the twin's own name, with instrlang README control 3 confirming tag blocks are stripped before judging, so it cannot bias the A/B.
> - Cross-checked the shared-component premise itself (README.md:50-56) against the filesystem: id-copy's references set matches id-humanizer's for tells/register, and the twin byte-shares its Indonesian tells/register with id-copy-id — the "no extra variable" claim is true.
>
> Nothing found that breaks parity or invalidates the experiment; the three minors are provenance/path hygiene.

## Native-register critic — VERDICT: NOT PASS (findings fixed before arming)

(checklist + report verbatim)

> lens: NATIVE-INDONESIAN-REGISTER
> checklist: C1 no calques/English-shaped collocations (SKILL.md + voice.md); C2 lugas register matching id-copy-id calibration, no baku-drift; C3 real words, KBBI spellings; C4 coined terms ("leger makna", "catat suara", "pass", "tell") comprehensible and consistent at first use; C5 DETEKSI handles the "Pilih SATU tingkat" vs detect seam at least as clearly as parent step 1; C6 frontmatter/headers natural, matching id-copy-id conventions.
>
> findings:
>
> [major] voice.md:21 — non-word "pendek-pendak" (C3). "Penulis kalimat pendek-pendak harus tetap menulis kalimat pendek-pendak setelah pass ini." "Pendak" is not an Indonesian word; the reduplication of pendek is pendek-pendek. Both occurrences in the line are misspelled, so the exemplar sentence for "Ritme kalimat" is written with a non-word twice. Parity grep confirms the parent ("short punchy sentences") has no such token — this is twin-authored, not inherited. Same class as the earlier loop's "mntul"/"bersubyek" catches. Fix: "pendek-pendek" (both occurrences).
>
> [major] voice.md:52 — non-word "Keanean" (C3). "Satu tell bisa memang suara. Keanean asli penulis yang mirip tell…" Keanean is not a word; the standard derivation from aneh is keanehan. It is the key noun of the rule ("a writer's genuine quirk"), so the rule header sits on a misspelling. Parent parity: parent says "genuine quirk" — again twin-authored. Fix: "Keanehan asli penulis…".
>
> [major] SKILL.md:37-38 and voice.md:55 — English-order collocation "penutup formula" (C1). SKILL.md: "(boilerplate tanpa informasi boleh dipangkas sesuai aturan penutup formula di voice.md)"; voice.md: "Penutup formula itu tell, bukan suara." Both render English "closing formula" word-for-word with the modifier in front. Indonesian heads precede modifiers: formula penutup (cf. kalimat penutup, paragraf penutup). Read natively, penutup formula parses as "the closing of the formula", which is not the intent; a case-insensitive grep shows the natural order formula penutup appears nowhere in the twin. This is precisely the English-shaped collocation C1 bans, in a bolded rule header agents will reread. Fix: "sesuai aturan formula penutup di voice.md" and "Formula penutup itu tell, bukan suara."
>
> [minor] voice.md:105-106 — stacked calque "keyakinan level sumber rendah" (C1). Mirrors English "source-level confidence low" as a noun stack; a native parses it only after a reread. Fix: "kepercayaan pada sumbernya rendah — ditandai…".
>
> [minor] voice.md:88 — "doktrin via Badudu dkk." (C1). English "via" for lewat/dari; the calibration twin files use no "via". Fix: "doktrin lewat Badudu dkk.".
>
> [minor] SKILL.md:30-31 — "inventarisasi yang harus selamat, per references/voice.md" (C1). "Per" here is English "as per"; note the distributive "per media" in step 1 is fine and separate. Fix: "sesuai references/voice.md".
>
> [minor] SKILL.md:34 — "jalankan references/tells.md ke seluruh teks" (C1). Shaped on "run X over the text"; the passed sibling calibration writes "periksa draf terhadap semua entri tells.md". Fix: "jalankan tells.md terhadap seluruh teks".
>
> [minor] voice.md:20 — "variansinya" (C3, verify). KBBI's term for statistical variance is varians; variansi is the common non-standard form. Fix: "variansnya" unless the author verifies "variansi" against KBBI.
>
> [minor] voice.md:78 — "buang bingkai era rekayasa" ambiguity (C4). Cold-read parses "era rekayasa" as "the engineering era"; the intended sense ("staged era frame") only resolves via tells.md's "adegan yang direkayasa". Fix: "buang bingkai 'era' yang direkayasa".
>
> [minor] voice.md:117-118 — "ceklis penyuntingan LMSPada mencantumkan" (inherited). Garbled token, but present verbatim in the parent (id-humanizer/references/voice.md:109 "LMSPada penyuntingan checklist") — a parity carry-over, not a twin register defect. Fix both files after checking Haryadi's checklist name.
>
> attempted-breaks: 1. Baku-drift hunt: grepped and read for ceremonial connectors (dengan demikian, sebagaimana, apabila, sehubungan dengan) and Anda-register instruction voice — none; the twin uses kalau, bare imperatives ("tandai, jangan dikerjakan"), matching id-copy-id's lugas calibration. No priming risk toward stiff output. C2 holds. 2. Non-word inheritance test: parity-grepped the parent voice.md for "pendak"/"Keanean" — absent, so both are twin-authored typos, not faithful-copy exceptions. 3. Tried to defend "penutup formula" as native via the penutup acara analogy — it fails semantically (penutup acara = closing of the event; penutup formula would = closing of a formula), confirming the calque. Confirmed "formula penutup" appears zero times. 4. Tried to break C4: "leger makna"/"leger suara" — leger is a real KBBI word (buku catatan), first use is immediately glossed "(fakta, angka, nama, klaim — tidak boleh disentuh)" (SKILL.md:32-33) and titled "(tidak bisa ditawar)" (voice.md:37); "CATAT SUARA" self-explains via apposition and matches step 4's "catatan suara"; "pass" and "tell" are primed in the description and step names. No term breaks comprehension. C4 holds apart from the voice.md:78 minor. 5. Tried to mislead via the C5 seam: the twin's DETEKSI (SKILL.md:23-29) reproduces the parent's EXPECTED-vs-OBSERVED reframing (parent SKILL.md:24-30) — register.md supplies expected-per-media via its decision rules, textual evidence supplies observed, mismatch = tell #3. An agent following the twin is not misled where the parent's would not be. C5 holds. 6. Considered flagging "slebi" (voice.md:72), "ampelas" (voice.md:54), "emasnya suara" (voice.md:27), "terbaca ditulis orang yang sama" (SKILL.md:3), "Pembeda yang membuat skill ini beda" (SKILL.md:13) — each is grammatical or calibration-consistent (ilfil, nebak, lebay appear in the passed id-copy-id files); rejected as findings or left as color. 7. C6: frontmatter follows the id-copy-id template exactly; headers "Alur (selalu berurutan)", "Kejujuran", "Lingkup (v1)" match; ../README.md link target exists. C6 holds.
>
> Zero-major condition fails on the two non-words and the English-order collocation — all one-word/two-word fixes, but as written the instruction text itself contains the machine-translation traces this experiment is built to eliminate.

## What was fixed (builder dispositions — all findings fixed, none refuted)

- 3 majors: "pendek-pendak"→"pendek-pendek" (×2), "Keanean"→"Keanehan",
  "penutup formula"→"formula penutup" (SKILL.md + voice.md).
- Minors: "keyakinan level sumber rendah"→"kepercayaan pada sumbernya
  rendah"; "doktrin via"→"doktrin lewat"; "per [file]"→"sesuai
  [file]"; "ke seluruh teks"→"terhadap seluruh teks";
  "variansinya"→"variansnya"; "bingkai era rekayasa"→"bingkai 'era'
  yang direkayasa".
- Parity critic's path minors fixed in BOTH twins (id-humanizer-id
  and id-copy-id): provenance header paths ../../../→../../../../;
  eval/samples path deduplicated.
- Inherited garble "LMSPada" (present in the shipped parent too):
  fixed in BOTH parent and twin as "an editing checklist in that
  tradition" / "ceklis penyuntingan dalam tradisi itu" — a citation-
  hygiene fix, not a rule change; parity preserved.
- Post-fix verification: negative grep (pendak|Keanean|penutup
  formula|LMSPada|keyakinan level|doktrin via|variansinya) returned
  zero matches across the twin and parent.
