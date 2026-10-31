# translate-3 — EN changelog + error docs (input for id-translate eval, loop 7)

**Generated:** 2026-10-31 by the repo builder, from the prompt below.

**generation prompt (reproduce the EN source):**

```
Write a short changelog entry + one error-docs note (about 110 words)
for the fictional Indonesian team-chat app "Lobi". Changelog: new
message scheduling (long-press a chat → Schedule), exported CSV reports
now include timestamps, dark mode moved to Settings → Appearance.
Error note: code 429 means rate-limited — wait 60 seconds before
retrying; if it persists, check the Dashboard → API page. Plain
professional English, no marketing tone.
```

- **Surface:** developer changelog + error docs · **Suggested persona:**
  dev-docs
- **Task (both arms):** translate into natural Indonesian.
- **Built-in probes:** two UI paths (long-press flows,
  Settings → Appearance, Dashboard → API), one technical hedge
  ("if it persists"), code 429 stays code 429.

## Input text (translate EN → ID)

> ## What's new (v2.4)
>
> You can now schedule messages: long-press any chat, then pick
> **Schedule**. Exported CSV reports include timestamps by default.
> Dark mode moved to **Settings → Appearance**.
>
> ## Error 429 ("rate limited")
>
> You're sending requests too quickly. Wait 60 seconds before retrying.
> If the error persists, check your keys on the **Dashboard → API**
> page — an old key on a rotated workspace shows up as 429.
