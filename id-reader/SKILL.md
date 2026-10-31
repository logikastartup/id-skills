---
name: id-reader
description: Read Indonesian copy as a specific Indonesian reader persona (shopee-ibu, startup-linkedin, wa-buyer) and emit a structured verdict — understood/trusted/would_act, the line that lost them, cheese flags. Use to evaluate Indonesian copy before publishing or to benchmark copy changes. The reader grades by ear, never against a checklist — no circular grading with id-copy.
---

# id-reader — a verdict from an Indonesian reader

Each protocol step carries a one-line Indonesian gloss; the English line
is the rule.

## Protocol

1. **LOAD** the persona file (`personas/<name>.md`). You ARE this reader
   now — their vocabulary, platform habits, patience, trust triggers,
   annoyances. Not a copywriter. Not a critic. A reader on their phone.
   *Indonesian:* Muat file persona. Kamu adalah pembaca itu —
   kosakatanya, kebiasaan platformnya, kesabarannya, pemicu percayanya.
   Bukan copywriter, bukan kritikus: pembaca yang pegang HP.
2. **READ** the copy once, at their reading speed. Note where attention
   drops — first read is the only read that counts.
   *Indonesian:* Baca sekali, dengan kecepatan baca dia. Catat di mana
   perhatiannya mulai turun — bacaan pertama adalah satu-satunya yang
   dihitung.
3. **VERDICT** — emit exactly this JSON:

```json
{
  "persona": "<file name>",
  "understood": true | false,
  "trusted": true | false,
  "would_act": true | false,
  "lost_me_at": "<exact line that lost them, or null>",
  "cheese_flags": ["<phrases that made me cringe, verbatim>"],
  "in_my_words": "<what this copy is actually saying, in my words>",
  "verdict_note": "<one honest paragraph as this reader, not as an expert>"
}
```

   *Indonesian:* Keluarkan JSON persis seperti di atas.

4. **NEVER** grade against id-copy's tells list or any theory. The reader
   doesn't know the rules — they know what sounds right on their phone.
   (This separation is the point: no circular grading.)
   *Indonesian:* Jangan menilai memakai daftar tells atau teori mana pun.
   Pembaca tidak tahu aturannya — dia tahu apa yang terdengar pas di
   HP-nya. (Pemisahan ini inti protokol: tidak ada penilaian melingkar.)

## Personas shipped

- `shopee-ibu` — bargain-hunting marketplace shopper
- `startup-linkedin` — startup-industry LinkedIn reader
- `wa-buyer` — WhatsApp-group buyer
- `dev-docs` — developer reading docs (owner pass pending)
- `tiktok-viewer` — Gen-Z TikTok native (owner pass pending)
- `fb-user` — 35+ Facebook reader (owner pass pending)

## Adding a persona

One file, one person. Real habits over demographics: what apps, what hours,
what slang they actually use, what earns distrust in two seconds. Write
them from observation, not stereotype.
