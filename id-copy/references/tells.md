# tells — the "AI Indonesian" blacklist

`component: SHARED` · `version: 1 (2026-10-31)` · one tell per entry:
pattern → why it fails → fix → source. Markers: **[doc]** = documented by
others (named source; URLs in the source lists), **[inf]** = inferred from
documented grammar, **[eval]** = learned from a reader verdict in
`eval/verdicts/`. Fix every hit; never delete the line silently.

1. **"Dalam dunia yang serba cepat ini…" / "Dalam era digital…" opener**
   — the ChatGPT signature. Fits any topic, so it fits nothing.
   → Fix: open with a concrete hook — number, scene, problem. If the
   text supplies no lived detail and none can be asked for, flag it —
   never stage a scene to satisfy the fix.
   **[doc — corpus-level]**: the phrase appears across 8 search-indexed
   pages; evidence is snippet-level (see `eval/samples/wild-3` caveats),
   not 8 fetched bodies.
   ⚠️ **Eval-taught (2026-10-31):** the replacement hook must be *lived or
   specific to a real speaker*, not a staged mood scene — a reader verdict
   on "Jam 11 malam, dan semua temanmu sudah tidur" as a replacement:
   "a mood scene that describes everyone describes no one." Specificity of
   detail ≠ specificity of person. A mechanism promise ("presentasi
   mendadak besok pagi? ada cara latihan 20 menit") survives; a generic
   scene does not.
2. **Essay scaffolding** — "berikut ini adalah…", "Dengan demikian…",
   "sangat penting untuk dicatat bahwa". Textbook machinery in sales copy.
   → Fix: lead with the point; no signposting. **[doc]** (live gov page)
3. **Register lock** — encyclopedia-flat baku everywhere. The tell is
   *mismatch*, not baku: fintech ~90% baku is CORRECT; a teen IG caption in
   baku is robotic. → Fix: check the register ladder
   ([register.md](register.md)) against the surface. **[doc]** (Erafone,
   Xerpihan matrix)
4. **Pronoun mismatch** — Anda in casual social copy; lo/gue in a bank app.
   → Fix: pronoun follows vertical + register choice. **[doc]** (Xerpihan)
5. **Agent-bearing passive** — "ditulis oleh…", "dilakukan oleh…" where a
   human writes "Saya menulis…" / "Kami buat…".
   → Fix: active voice. **[doc]** (Medium "4 Tanda Kaku")
6. **Metronome rhythm** — every sentence subject-predicate-object, uniform
   length, "datar dan terlalu bisa diprediksi". **[doc]** (Medium;
   Erafone)
   → Fix: vary deliberately; a 3-word sentence after a long one.
7. **Comma at every pause** — grammar-diagram punctuation, "kaku dan
   bertele-tele". → Fix: punctuate by breath; let some clauses run.
   **[doc]** (Medium "4 Tanda Kaku")
8. **Semicolon showmanship** — titik koma in casual copy = academic/machine.
   → Fix: period, or "dan"/"tapi". **[doc]** (Medium "4 Tanda Kaku")
9. **Zero "!" and "…"** — emotion-free punctuation in a register that uses
   both. → Fix: use sparingly and irregularly, like a person. **[doc]**
   (Medium "4 Tanda Kaku")
10. **Calqued English metaphors** — "lanskap yang terus berkembang",
    "membuka jalan", "menyelami/mendalami", "leverage".
    → Fix: plain verbs — "makin banyak", "pelajari lebih jauh". **[doc]**
    (LinkedIn pet-peeves; humanization lists — some URLs unstable)
11. **Word-for-word translate-ese** — English-shaped order and collocations
    (GT's most frequent failure mode, 38.73% literal in one study).
    → Fix: translate meaning, re-order for Indonesian rhythm. **[doc]** (SSRN
    EN-ID evaluation located; "word-for-word" study URL unverified)
12. **"para" on every plural human noun** — "para pelanggan/para pengguna"
    as a calque of English "-s". Bare noun is default; para is ceremonial.
    → Fix: "pelanggan"; "banyak pelanggan" if quantity matters. **[inf]** —
    para's restricted grammar is documented; its MT-overuse is inference
13. **UI register flattening** — bare "Lanjut" (abrupt; Gojek ships "Yuk,
    Mulai"), ambiguous "Bebas"/"Simpan".
    → Fix: politeness particles + specific verbs. **[doc]** (Xerpihan)
14. **Flawless but soulless** — "rapi tanpa typo tapi kaku, kering";
    pet-phrase repetition; over-explaining basics.
    → Fix: cut repetition; keep one human quirk or opinion. **[doc]**
    (writers'-group thread; Erafone)
    ⚠️ **[eval]** stiffness hides in single words too — a chat-register
    reader flagged "bermaksud" (stiff) where people type "bukan mau", and
    ambiguous "butuh dengerin" where the meaning is "butuh didengerin".
    Re-read each verb phrase at the chosen register's typing speed.

15. **Punctuation register mismatch in chat** — long dashes, semicolons,
    perfectly balanced clauses in a WhatsApp/social chat-context post.
    A WA-context reader: "siapa yang ngetik strip panjang jam 2 pagi di
    WA?" — long dashes in chat read as paste or machine-rapikan.
    → Fix: in chat surfaces use commas, line breaks, and "..." like a thumb
    types them. **[eval]** (wild-2 after-verdict)

16. **The unspecified "penawaran spesial"** — calling an offer
    special/istimewa/eksklusif without saying WHAT it is. Two blind reader
    verdicts flagged the same phrase independently: "kalau penawarannya
    spesial, sebut spesialnya apa" / "'penawaran spesial' masih dikunci."
    → Fix: name the offer (the discount %, the free item, the price) — or
    cut the word. An unnamed offer is brochure-speak. **[eval]** (blind A/B,
    2026-10-31 — flagged on BOTH arms' outputs; even skill-guided drafts
    leak it, so check for it explicitly in tells pass)
    Related: **placeholders never ship** — a literal "[Lokasi]" in a caption
    reads as an unfinished post to exactly the reader who notices details;
    fill or cut every bracket before publishing.

## Weighting (don't over-fire)

- **Em dash: contested** in Indonesian coverage ("masih diperdebatkan") —
  weight LOW; never fail a piece on em dashes alone. **[doc]**
- One tell in a long piece = a note; three+ or any of #1/#3/#4 = rewrite
  the opening/register.
- Formal register is a tell ONLY when mismatched to surface + audience
  (see register ladder).

## Sources (principal)

Medium "4 Tanda Kaku" (fetched) · Erafone "Ciri-Ciri Tulisan AI" (fetched)
· Xerpihan Indonesian Localization Playbook (fetched) · BBPMP Jateng page
(fetched) · Lemon8 corpus family · r/indonesia 2015 register-gap thread ·
UNSW Johnson 2006 · SSRN EN-ID MT evaluation. Sourced wild-sample URLs live in
`../../eval/samples/`; re-verify any URL before quoting it externally.
