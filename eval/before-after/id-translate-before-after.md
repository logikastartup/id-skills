# id-translate — before / after

The claim: **3/5 across two rounds** (loop 5: 1/2 — the loss became
the UI-path rule below; loop 7: 2/3, the new loss is the same rule's
known per-reader cost). Sample translate-1: a "Getting started" docs
section, EN → ID, same model both arms.

## Before (no skill)

Clean grammar, correct numbers — and one corrupted instruction:

> Kunci API Anda ada di menu **Pengaturan → Kunci**. Cukup setel sekali:

The source said **Settings → Keys** — the actual menu in the app's
English UI. The blind judge (dev-docs) lost the thread exactly there:
*"You do not translate UI labels; that is the one string I need to
click, and now I'm opening the English page to check what the menu is
really called, which by definition means I'm not following this guide
on its own."* Also caught: "lakukan autentikasi", Anda register,
"setel" for an env var — *"It's just visibly a translation, and it
changed an instruction."*

## After (with id-translate)

Register mapped first (semi-formal santai, kamu — developer docs),
parity ledger 7/7 lines verified, UI path kept clickable:

> *API key* kamu ada di **Settings → Keys**. Cukup set sekali:

Same judge: *"This one never tripped the 'ini terjemahan' wire…
keeping job/upgrade/checkout in English is exactly how we talk… I'd
follow this end to end and forward it to my team without checking the
English page."*

## The loss (kept — it is the finding)

translate-2 (merchant email) went the other way: the skill arm kept
**Settings → Delivery** in English, but the judge's app (fb-user, 48)
is Indonesian-localized: *"di aplikasi saya tulisannya Pengaturan,
jadi saya bingung ini menu yang mana…"* She picked the no-skill arm.

Same rule, opposite directions: **UI paths must match the app's actual
UI language** — which differs per reader. Encoded as structures.md #21
+ a ledger rule. The A/B stands as run; re-measuring needs new samples (no-rerun rule). Loop 7 added three samples (changelog docs,
merchant payout email, logistics blog): 2/3 skill picks — the
payout-email loss was this same rule in its trade-off form (the skill
kept "Help Center" English per the unverified-UI rule; the merchant
reader's app and preference are Indonesian — "Pusat Bantuan" won her).

n=5 across two rounds · directional. Full arms + JSONs both rounds:
[`translate-ab.md`](../verdicts/translate-ab.md) ·
[`loop7-arms.md`](../verdicts/loop7-arms.md) · inputs:
[`translate-1.md`](../samples/translate-1.md)–[`translate-5.md`](../samples/translate-5.md)
