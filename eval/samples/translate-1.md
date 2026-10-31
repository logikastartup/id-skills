# translate-1 — EN docs section (input for id-translate eval)

**Generated:** 2026-10-31 by the repo builder, from the prompt below
(any base model produces an equivalent input).

**generation prompt (reproduce the EN source):**

```
Write a short "Getting started" section (about 120 words) for the docs
of a fictional developer tool called Antrean — a queue service for
Indonesian e-commerce checkouts. Include: an install command, one
config snippet with an api key placeholder, a note that the free tier
handles up to 5,000 jobs per month, and a hedge that burst behavior
"may vary during flash-sale peaks". Plain professional English, no
marketing tone.
```

## Input text (translate EN → ID)

> ## Getting started
>
> First, install the CLI and authenticate with your workspace key:
>
> `npm i -g antrean-cli && antrean login`
>
> Your API key lives in **Settings → Keys**. Set it once:
>
> `export ANTREAN_KEY=ak_live_xxx`
>
> The free tier handles up to 5,000 queued jobs per month, which covers
> most small stores. Burst behavior may vary during flash-sale peaks —
> if your checkout volume regularly exceeds that, upgrade before your
> next campaign, not during it.
>
> Jobs are retained for 7 days, then deleted. Export anything you need
> to keep.
