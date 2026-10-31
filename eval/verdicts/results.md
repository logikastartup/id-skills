# eval results — 2026-10-31, id-copy@1

Before → after, fresh persona-only verdict agents (never saw the tells or
each other). Raw before/after JSONs + rewrites live in the per-sample files
in this folder (`wild-1…5-*.md`).

| sample | before (und/trust/act) | after | what moved it |
|---|---|---|---|
| wild-1 gov blog | ✓ ✗ ✗ | ✓ ✓ ✓ | concrete-use hook; falsifiable close ("kalau nggak ngefek, tulis komentar") |
| wild-2 Lemon8 diary | ✓ ✗ ✗ | ✓ ✓ ✓ | killed the two-voice seam; chat particles; kept diary register consistent |
| wild-3 opener family | ✓ ✗ ✗ | ✓ ✗ ✗ (openers) | **HONEST FAILURE — see below** |
| wild-4 Wikipedia paste | ✓ ✗ ✗ | ✓ ✓ ✓ | answered her actual questions (apa itu / bayar nggak) + honesty caveat ("jawabannya kadang salah… dicek ulang ya, Kak") |
| wild-5 newswire headline | ✓ ✗ ✗ | ✓ ✓ ✓ | falsifiable claim instead of noun-stack |

## The honest failure (wild-3)

Replacing "Dalam dunia yang serba cepat ini…" with *staged* concrete scenes
("Jam 11 malam, dan semua temanmu sudah tidur") did NOT recover trust —
the reader called them "three costumes of the same manufactured stress
scene… a mood scene that describes everyone describes no one." Only the
opener carrying a real mechanism promise ("presentasi mendadak besok pagi?
Ada cara latihan 20 menit") survived.

**Finding encoded into the skill:** tell #1's fix is upgraded — a concrete
hook must be *lived or specific-to-a-real-speaker*, not a manufactured mood
scene. Specificity of detail ≠ specificity of person.

## Reader-taught refinements (also encoded)

- **Chat punctuation register** (wa-buyer): long dashes in a chat-context
  post read as paste/AI — "siapa yang ngetik strip panjang jam 2 pagi di
  WA?" → new tell #15.
- Word-level stiffness the ear caught: "bermaksud" → "bukan mau";
  "butuh dengerin" ambiguous → "butuh didengerin". Fix guidance added to
  tells #14.
- startup-linkedin: em-dash tolerance is ~2 per short piece — consistent
  with the low-weight em-dash rule in tells.md weighting.

## Per-sample records

- wild-1: before — lost_me_at "Revolusi Industri 4.0 melanda"; flags:
  era-opener, "berikut ini adalah", Anda register, "Dengan demikian";
  "content-farm output". After — trusted=true, would_act=true; note:
  "invitation to failure is what makes me believe"; conditions: first list
  item must open with a concrete result; two em-dashes = at the limit.
- wild-2: before — "Jujur ya Kak… aku tiap minggu delete broadcast
  beginian… nggak ada satu kalimat pun yang kedengeran kayak orang biasa
  ngetik cepat di chat." After — trusted/act true; "kebaca kayak status
  temen, bukan broadcast"; flags kept: em-dash ×2, "bermaksud", "butuh
  dengerin". Fix applied in the record above.
- wild-3: before — "three posts wearing the exact same cardboard opener…
  screenshot-mock material." After (openers) — staged-scene finding (above);
  no variant recovered the openers, and that stands as the v1 limit.
- wild-4: before — "suasananya seperti dosen ngajar… tidak ada harga, tidak
  ada bukti… cukup menggeser ke atas lagi." After — "malam ini aku coba
  tanya menu seminggu"; the honesty caveat ("jawabannya kadang salah…")
  compared to "seller yang jujur bilang warna bisa beda dikit sama foto".
- wild-5: before — "consultant-keynote claim… 'Reinvensi' smells like a
  translated slide deck." After — "earns the click… falsifiable claim about
  where money goes"; conditions: paragraph one needs a number and a name.

Rewrites live in the per-sample verdict files; regenerate any of them by
running id-copy on the samples per `run.md`. A sixth input family,
`samples/gen-1` (reproducibly generated cheese with its prompt embedded),
is banked for the next eval round.
