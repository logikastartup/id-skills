# id-humanizer — before / after

The claim, stated plainly: **0/2 in loop 5 — then 3/3 in loop 7 after
the fix.** Aggregate **3/5**, and the turnaround is the story: both
loop-5 losses pointed at one defect, fixed the same day; loop 7's
three fresh samples (CS broadcast, LinkedIn post, product update) all
went to the skill arm. This exhibit shows the original loss, not a
curated win — a humanizer must be judged on what it does to formula,
not on vibes.

## Before (the input's machine layer)

Sample humanize-1, a stiff internal announcement (generation prompt
embedded in the sample file):

> Di era digital yang serba cepat ini, RuteKita senantiasa berkomitmen
> untuk memberikan pelayanan terbaik bagi para pengguna; … Demikian
> pengumuman ini kami sampaikan; atas perhatian dan kerja sama para
> pengguna, kami ucapkan terima kasih.

## After (the skill arm — and why it lost)

The skill arm cleaned the era opener, protected every fact — and kept
the closing formulas, judging them a genre convention:

> Perubahan ini kami lakukan sebagai bentuk komitmen untuk
> meningkatkan kualitas pelayanan demi kepuasan mitra dan pengguna. …
> Demikian pengumuman ini kami sampaikan. Atas perhatian dan kerja
> sama pengguna, kami ucapkan terima kasih.

The blind reader (fb-user) flagged exactly those lines: *"saya seperti
membaca surat dari kantor kelurahan… 'demikian pengumuman ini kami
sampaikan' — itu penutup surat resmi yang distempel, bukan yang
diucapkan orang."* The no-skill arm cut the ceremony and won both samples' picks.

## What the skill got right (the reader confirmed it)

- Every number and fact survived verbatim — on the losing humanize-2
  arm, the judge still opened *"Faktanya lengkap — 12 toko, 94%, 2 toko
  macet…"*.
- Its flag of the agent-less passive was correct process: the judge
  pressed the same question on both arms — on the winning one, *"'sudah
  dijadwalkan' tetap nggak bilang siapa ownernya…"* — the exact question
  the skill's change list had raised.

## The fix

`voice.md` now says it outright: **"Formulaic closers are tells, not
voice."** — default cut/compress, keep only for official surat dinas.
The fix postdates the loop-5 A/B (no reruns — re-measuring takes new
samples) — so read the loop-5 half as a loss with its root cause, not
a vindication. **Loop 7 supplied the new samples** (fix in place) and
the skill arm swept 3/3: the WA reader *"[rasanya] kayak notifikasi
kurir yang beneran… aku screenshot jadwalnya"*; the LinkedIn reader
*"ini suara orang yang benar-benar ada di timeline saya… saya nggak
merasa dimanipulasi untuk komen"*; the dev reader *"ini kayak changelog
yang ditulis, bukan diterjemahkan."* Full arms + JSONs both rounds:
[`humanize-ab.md`](../verdicts/humanize-ab.md) ·
[`loop7-arms.md`](../verdicts/loop7-arms.md) · inputs:
[`humanize-1.md`](../samples/humanize-1.md)–[`5.md`](../samples/humanize-5.md)
