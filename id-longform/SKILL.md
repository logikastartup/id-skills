---
name: id-longform
description: Write natural Indonesian long-form — blog articles, newsletters, explainers (800+ words) — free of AI-Indonesian scaffolding (era openers, "Dengan demikian" transitions, mechanical "Kesimpulannya" closers, para-overuse). Forces a stated angle and a section-move outline before drafting. Use for Indonesian articles/newsletters; short copy is id-copy, docs translation is id-translate.
---

# id-longform — Indonesian articles that don't smell generated

**Router only.** Components under `references/`; each flow step carries
a one-line Indonesian gloss (English line = the rule).

## Flow (always in order)

1. **INTAKE** — type (blog / newsletter / explainer), audience, goal,
   and — if the author has existing writing — a voice sample for the
   voice ledger (method: [`../id-humanizer/references/voice.md`](../id-humanizer/references/voice.md)
   — optional, needs the whole repo copied; if absent, infer voice from
   the brief). **Audience
   age/status weighs on register**: 35+ merchant/professional readers
   can read santai-kamu as junior ("kalau sales datang ke toko saya
   pasti bilang 'Pak'" — a real reader, loop-5 eval); for them,
   respectful semi-formal (Anda / Bapak-Ibu) is warmth, not stiffness.
   Kamu-santai is a choice for peers and younger audiences, never a
   default for "consumer".
   *Indonesian:* Tentukan jenis tulisannya, pembacanya, tujuannya — dan
   kalau penulisnya punya tulisan lain, simpan contoh gayanya. Umur dan
   kedudukan pembaca menimbang register: pembaca 35+ (pemilik toko,
   profesional) bisa membaca santai-kamu sebagai kurang hormat —
   semi-formal Anda/Bapak-Ibu adalah kehangatan, bukan kekakuan.
2. **ANGLE** — state the ONE thing this piece argues or reveals, and
   the hook: a lived, specific moment — never a staged scene or an era
   frame ("Dalam era digital…" is tells #1 territory).
   *Indonesian:* Nyatakan satu inti tulisan ini, lalu kaitannya
   (hook-nya): momen nyata yang spesifik — bukan pemandangan buatan,
   bukan pembuka era.
3. **OUTLINE** — sections as **moves** (each advances the angle), with
   subheads that carry content, not labels ("Kenapa bot kamu jawab
   'siap'" not "Pembahasan"). No section exists to "introduce the
   topic" in the abstract.
   *Indonesian:* Susun bagian sebagai langkah — tiap bagian menggerakkan
   inti tulisan. Judul bagian berisi isi, bukan sekadar label.
4. **DRAFT** — section by section, register held throughout
   ([`references/register.md`](references/register.md)); transitions
   that don't announce themselves — the scaffolding ban-list lives in
   [`references/structure.md`](references/structure.md); loanword
   choices (unduh vs download, tautan vs link) per
   [`references/codeswitch.md`](references/codeswitch.md).
   *Indonesian:* Tulis bagian demi bagian, register dijaga konsisten;
   transisi jalan diam-diam — daftar frasa jembatan terlarang ada di
   structure.md, pilihan kata serap mengikuti codeswitch.md.
5. **TELLS + STRUCTURE PASS** — [`references/tells.md`](references/tells.md)
   over every paragraph, then the structure checklist: does the close
   land a point or mechanically summarize ("Kesimpulannya" is the
   white flag)? Is "para" doing work a plural marker couldn't?
   *Indonesian:* Periksa tiap paragraf dengan daftar tell, lalu
   strukturnya: penutupnya mendarat atau cuma merangkum?
6. **POLISH + TAG** — delivery, then:

```
type: <t> · register: <r> · angle: <one line> ·
checked: id-longform@v1
⚠️ hand to a native Indonesian reader before publishing.
```

   *Indonesian:* Serahkan tulisannya plus blok tag — jenis, register,
   inti tulisan, dan pengingat native reader.

## Honesty

Long-form is where AI-Indonesian hides best: every sentence local-clean,
the whole thing globally hollow. The angle step exists so the piece has
a spine a reader can feel; if there's no angle, there's no article —
say so instead of generating one anyway.

*Indonesian:* Tulisan panjang adalah tempat AI paling bagus
menyembunyikan dirinya: tiap kalimat rapi, tapi seluruhnya kosong.
Kalau tidak ada sudut pandang, tidak ada tulisan — katakan saja.

## Scope (v1)

**In:** Indonesian long-form prose — blog articles, newsletters,
explainers, announcement posts of substance. **Out of scope:** short
marketing copy (→ `id-copy`); translating English long-form (→
`id-translate`); academic writing with citation standards; SEO
keyword-stuffing (won't); fiction.
