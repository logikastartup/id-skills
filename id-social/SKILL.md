---
name: id-social
description: Write Indonesian social posts for TikTok (captions + video scripts), LinkedIn, and Facebook — each platform's own register, hook conventions, and platform-specific tells (LinkedIn humblebrag slop, TikTok dated-slang, FB generational norms). Instagram captions and WhatsApp stay in id-copy. Slang always carries dated/evergreen status. Use when the surface is TikTok/LinkedIn/Facebook for Indonesian audiences.
---

# id-social — Indonesian social, per platform

**Router only.** One file per platform under `references/` — load the
one the task names, nothing more. Instagram captions and WhatsApp live
in `id-copy` ( [`../id-copy/references/platforms.md`](../id-copy/references/platforms.md) );
this skill cross-references, never duplicates (the link needs id-copy
present if you copy only this folder — IG/WA surfaces live there). Each
flow step carries a
one-line Indonesian gloss (English line = the rule).

## Flow (always in order)

1. **INTAKE** — platform FIRST (tiktok | linkedin | facebook), format
   (post | video script | caption), goal, audience.
   *Indonesian:* Tentukan platformnya dulu, lalu formatnya, tujuannya,
   dan siapa pembacanya.
2. **PLATFORM LOAD** — read the one platform file
   ( [`references/tiktok.md`](references/tiktok.md) ·
   [`references/linkedin.md`](references/linkedin.md) ·
   [`references/facebook.md`](references/facebook.md) ) and adopt its
   norms: length, register range, hook convention, emoji law.
   *Indonesian:* Baca file platform-nya dan ikuti aturannya: panjang,
   rentang register, pola hook, aturan emoji.
3. **REGISTER** — explicit choice from
   [`references/register.md`](references/register.md) **within the
   platform's range**; slang is handled per
   [`references/codeswitch.md`](references/codeswitch.md) — but the
   **platform file's slang status overrides** codeswitch.md's generic
   status when they disagree (tiktok.md marks santuy dead for Gen Z;
   codeswitch.md alone doesn't). Every slang word carries
   `status: evergreen | dated <date> | dead`.
   *Indonesian:* Pilih register secara eksplisit dalam rentang
   platform-nya; tiap kata slang dicatat statusnya — masih hidup atau
   basi, per tanggal berapa.
4. **HOOK + STRUCTURE** — build the format's skeleton before drafting:
   a TikTok script is timed (hook lands in the first 2 seconds);
   a LinkedIn post is one idea in the first 2 lines; a Facebook post
   may run long and story-shaped.
   *Indonesian:* Bangun kerangkanya dulu: script TikTok ketat waktunya
   (hook di dua detik pertama); post LinkedIn satu gagasan di dua baris
   pertama; post Facebook boleh panjang dan bercerita.
5. **DRAFT + PLATFORM TELLS** — draft, then check against the shared
   [`references/tells.md`](references/tells.md) AND the platform
   file's own tells section.
   *Indonesian:* Tulis, lalu periksa dengan daftar tell umum dan
   daftar tell khusus platform-nya.
6. **POLISH + TAG** — delivery, then:

```
platform: <p> · format: <f> · register: <r> ·
slang: <none | term=evergreen|dated <date>|dead, …> · checked: id-social@v1
⚠️ hand to a native Indonesian reader before publishing.
```

   *Indonesian:* Serahkan hasilnya plus blok tag — platform, format,
   register, status slang, pengingat native reader.

## Honesty

Social platforms date faster than any other surface in this repo — a
TikTok register audit has a shelf life measured in months. The dated
markers are not decoration; re-check them before trusting any
slang-bearing line.

*Indonesian:* Platform sosial basi lebih cepat dari permukaan lain di
repo ini — status tanggalnya bukan hiasan; cek ulang sebelum memakai
baris yang mengandung slang.

## Scope (v1)

**In:** Indonesian posts/scripts/captions for TikTok, LinkedIn,
Facebook. **Out of scope:** Instagram + WhatsApp (→ `id-copy`); paid ad
copy targeting (→ future `id-ads-research`); cross-posting the same
text everywhere (that's the disease, not the use); English-language
posts.
