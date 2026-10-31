# structures.md — the EN→ID transformation bank (id-translate)

`component: id-translate` · Entries carry their evidence:
`[receipt]` = caught live in this repo's loop 4 (gauntlet-progress.md);
`[pattern]` = pattern-level, awaiting the owner's native pass — treat as
strong default, verify before trusting blind; `[EYD/PUEBI …]` = cited
inline to the official rule (see Sources); `[research: …]` = the
research round's finding, with its unresolved status stated.

## A. Sentence shape

1. **No sentence-mapped drafting.** Draft from the ledger + meaning,
   not from EN syntax. If a target sentence can be predicted by
   pointing at its English source sentence, something is wrong.
   `[receipt — the method itself]`
2. **Comma-spliced English rhythm → restructure.** "copy that reads
   like a person wrote it, judged by readers…" is one EN breath; in ID
   it becomes "copy yang terasa ditulis manusia, dinilai langsung oleh
   pembaca…" — restructured, not mirrored. `[receipt]`
3. **Carried participles are forbidden.** "readers, blind and
   order-randomized, picked…" must NOT become "pembaca, dibutakan dan
   urutannya diacak, memilih…" — give the insert its own sentence:
   "Pembaca tidak diberi tahu versi mana hasil skill. Urutan
   bacaannya diacak. Hasilnya: …" `[receipt — loop-4 major]`
4. **Passive-chain limit.** Two di- passives per sentence is plenty;
   3+ = rewrite. Indonesian's native tool is the -nya nominalization
   ("aksennya gampang dikenali"), not stacked di- verbs. `[receipt —
   loop-4 major]`
5. **Agent-bearing passives:** fine in credits/status lines ("dibangun
   oleh X" is idiomatic); wrong in instructional prose — use the
   imperative. `[receipt — judge note]`
6. **Verb over nominalization.** "melakukan pemilihan terhadap" →
   "memilih". "adalah bagian dari finalisasi" → restate as an event:
   "masih akan mengoreksi … sebelum v1 difinalkan". `[receipt]`
7. **Split long compounds.** One EN compound sentence → 2-3 ID
   sentences. Indonesian tolerates shorter sentences than translators
   expect. `[pattern]`
8. **Topic-drop is native.** Subjects can drop when context carries
   them ("kalau menulis bahasa Indonesia, aksennya gampang
   dikenali"). Restoring every pronoun reads translated. `[pattern]`

## B. Calque families (kill on sight)

9. **"share X"** = have in common → "memakai X yang sama", never
   "berbagi X" (berbagi = give a share of). `[receipt]`
10. **"as a role"** → "berperan sebagai"; "membaca sebagai" only in
    critic-review contexts. `[receipt]`
11. **"di mana" as relative clause** — "rumah di mana saya tinggal" is
    widely taught as wrong (fix: "rumah tempat saya tinggal" / "yang");
    "di mana pun" (= wherever) is correct and stays. `[pattern —
    language-education consensus; primary source unrecovered, owner
    re-verify]`
12. **"mengambil/membuat keputusan" — DO NOT PRESCRIBE.** Research
    found no Badan Bahasa ruling; corpus evidence shows both coexist,
    with "mengambil keputusan" dominating formal writing. Translate by
    context, not by a calque rule — and never "correct" an author's
    choice here without asking. `[research: unresolved]`
13. **Translated noun piles** — "metafora hasil terjemahan bahasa
    Inggris" → "metafora yang diterjemahkan mentah-mentah dari bahasa
    Inggris". `[receipt]`
14. **Template email openers** — "Semoga email ini menemui Anda dalam
    keadaan baik" is the *established standard rendering* of "I hope
    this email finds you well" (template corpora everywhere) —
    research found no source calling it an error. It is not wrong; it
    is invisible boilerplate. Translate it only when the email is
    meant to feel templated; a letter meant to feel written opens on
    its actual business. `[research: prevalence documented,
    prescription absent]`
15. **"force X" / "part of finalizing X"** spec-shapes → natural
    equivalents ("mewajibkan", "sebelum v1 difinalkan"), never
    "adalah bagian dari". `[receipt]`

## C. Punctuation + form transfer (EYD Edisi V is current; PUEBI 2022-superseded but still-referenced prior)

16. **Semicolons — grammar vs register.** EYD/PUEBI rule III.C allows
    titik koma as conjunction-replacement between equal clauses in
    formal compound sentences — grammatical. But in casual/semi-formal
    copy it is register-marked machine-tell territory (tells #8: 3+ in
    a long piece = rewrite). Translate a source's register, not just
    its words: formal source keeps them; casual source loses them.
    `[EYD/PUEBI III.C + receipt — 9 caught in loop 4]`
17. **Em dashes (tanda pisah)** — official rule restricts them to
    insertions, emphasized appositives, and ranges, UNSPACED
    ("Kemerdekaan bangsa itu—saya yakin—diperjuangkan"). Spaced EN-style
    dashes everywhere = transfer artifact. Restructure or follow the
    unspaced form in formal docs. `[EYD/PUEBI III.F]`
18. **Comma before "dan"** as EN habit → drop unless a real clause
    boundary. `[pattern]`
19. **Foreign words in italics** — untranslated English terms in
    Indonesian prose are italicized per EYD (proper names excepted);
    in markdown docs use *asterisks* in formal registers.
    `[EYD/PUEBI I.G.3]`
20. **Loanword conversions** — absorbed loanwords follow orthography:
    ph→f (fase), q→k (ekuator), th→t (metode), double→single (efek),
    -ty→-tas (kualitas). Keep-English terms (codeswitch.md list) stay
    English + italics. `[EYD/PUEBI unsur serapan]`
21. **UI paths follow the app's UI language, not the source text.**
    "Settings → Keys" stays English if the product UI is English; it
    becomes "Pengaturan → Kunci" if the app is Indonesian-localized.
    When unknown, keep the source form and flag the assumption in the
    delivery note. Reader
    evidence: a dev followed the doc until a translated menu name sent
    him to the English page; a merchant stalled because an English menu
    name didn't exist in her Indonesian app. Both directions of the
    same rule. `[receipt — eval translate-1/2, loop 5]`

## D. Register mapping (quick table)

| EN source register | ID target (register.md ladder) |
|---|---|
| formal / academic | 1 baku-formal |
| professional docs / READMEs | 2 semi-formal santai — default for docs, impersonal or consistent kamu |
| casual / chat | 3 chat-santai |
| social-casual | 4 gaul hybrid (see codeswitch.md slang dates) |

Never map silently: the choice is stated in INTAKE and in the tag.

## Sources

- Loop-4 receipts: `gauntlet-progress.md` (this repo's workspace log)
  + id-gate §7 (the encoded blocklist).
- EYD Edisi V (2022, current) via SK:
  badanbahasa.kemendikdasmen.go.id/resource/doc/files/SK_EYD_Edisi_V_16082022.pdf;
  punctuation/loanword rules cited above via PUEBI mirror
  puebi.js.org (tanda/titik-koma, tanda/pisah, huruf/miring,
  unsur-serapan) — PUEBI superseded 2022-08-16 but rules reported
  tightened, not replaced; owner-check the SK PDF.
- HPI: "Kekakuan dan Keleluasaan dalam Penerjemahan" (webinar,
  2021-04-17) hpi.or.id — rigidity/flexibility stratified by text
  type: source-oriented (legal/academic) tolerates closer translation;
  target-oriented (speeches/journalism/this skill's docs default)
  requires rewriting. Nababan's triad (accuracy/acceptability/
  readability) is the standard QA frame in ID translation programs.
- LBI FIB UI, "6 Kesalahan Umum dalam Penerjemahan" lbifib.ui.ac.id —
  literal translation is error #1; register mismatch ("brosur promosi
  yang santai… tidak sebaiknya diterjemahkan dengan gaya akademik
  yang kaku") is a distinct error → this file's INTAKE mapping step.
- Kalimat efektif doctrine (kehematan/kecermatan/kesejajaran/
  keharmonisan/kelaziman) — binus.ac.id/malang/2022/07 — the editing
  backbone for sections A-B.
- Pastika, "Klitik -nya dalam Bahasa Indonesia" (Adabiyya) — the -nya
  clitic as native definiteness/pronominal tool (entry 4).
- Mozilla Indonesian l10n style guide mozilla-l10n.github.io — "You"→
  Anda for formal products, register by audience, plain verbs ("Buat"
  over "Ciptakan") — supports the register-mapping table.
- Unresolved (encoded as such above): mengambil/membuat keputusan; the
  "di mana" calque's primary source; the email-opener's status.
- Everything still awaits the owner's native pass.
