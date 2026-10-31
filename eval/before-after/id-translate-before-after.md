# id-translate — before / after

The claim: **1/2** — one win, one loss, and both turned on the same
rule from opposite directions. Sample translate-1: a "Getting started"
docs section, EN → ID, same model both arms.

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
+ a ledger rule. The A/B stands as run; re-measuring needs new samples (no-rerun rule).

n=2 · directional. Full arms + all four JSONs:
[`eval/verdicts/translate-ab.md`](../verdicts/translate-ab.md) ·
inputs: [`translate-1.md`](../samples/translate-1.md),
[`translate-2.md`](../samples/translate-2.md)
