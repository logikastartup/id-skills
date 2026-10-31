# id-longform — blind A/B (2026-10-31, loop 5)

n=2 · same harness both arms · blind judges · randomized (recorded) ·
no rerun. Same co-evolution/authorship caveats as ab-test.md.

## Arms

- **Arm A (no skill):** fresh agent, "tulis dua tulisan dari dua brief
  di bawah", no repo access.
- **Arm B (id-longform):** fresh agent loads `id-longform/SKILL.md` +
  structure/register/tells/codeswitch, full 6-step flow; angle/outline/
  self-check notes stripped before judging.

## Full arm texts

Retained verbatim in [`loop5-arms.md`](loop5-arms.md) — both articles
per arm, complete, plus all four verdict JSONs. Briefs:
`samples/longform-1.md` (dev blog, 800-1000 kata) and
`samples/longform-2.md` (B2B newsletter to pemilik toko, 400-500 kata).
Below: shape markers for navigation.

### longform-1 — Arm A

Title: "'Keliatan Bagus' Bukan Gate" — Sinta the polite bot quoting the
wrong stroller price for weeks; Anda-addressed; essay-shaped; semicolon
punchlines ("Itu bukan quality assurance; itu hukuman."); five-step
recipe; strong operational insights (dignified fallback, shadow mode).

### longform-1 — Arm B

Title: "Bot kamu sopan, cepat, dan salah harga" — TokoCerah, Jumat
10.14, rice cooker Rp449.000 vs promo Rp399.000; kamu-consistent;
headings-as-assertions; verbatim numbers; "Yang bisa kamu tulis hari
ini" (50 questions → start at 10 → CI → nightly 1% sampling);
table of three gate types; closing lands on a question, not a summary.

(Full verbatim texts of both arms: `loop5-arms.md`.)

### longform-2 — Arm A

> # Rak kosong, pas ada yang mau beli
>
> [Opens: buyer at the shelf, "Yang warna hitam ukuran L ada, Mbak?" —
> Anda-addressed throughout; the "nanti saya catat dulu" line; feature
> explained; pilot numbers verbatim (12 toko, 6 minggu, 31%, 8 dari 10,
> 50 SKU / Rp29rb); "Kami tidak menjanjikan rak Anda tidak akan pernah
> kosong lagi; tidak ada sistem yang bisa menjanjikan itu."; CTA:
> balas satu kata "stok". Signed: Rian dari tim KasirPintar.]

### longform-2 — Arm B

> # Rak kosong selalu ketahuan pembeli duluan
>
> [Opens: Ibu minta susu 800g, "udah deh, Pak"; kamu + nggak/kayak/
> ngitung register; feature + a CONCRETE sample suggestion quoted
> ("Sabun cuci 900 ml… aman pesan 6, datang sebelum Rabu"); pilot
> numbers verbatim; SKU glossed with the minyak goreng example; CTA:
> balas "stok". Signed: Dinda — tim KasirPintar.]

(Full verbatim texts of both arms: `loop5-arms.md`.)

## Verdicts (blind)

longform-1 · judge dev-docs · V1=Arm A, V2=Arm B → **PICK VERSION 2 =
Arm B (skill)**. "This one survives the scroll… headings are
assertions, so scanning works; 'kamu' is consistent the whole way…
'Yang bisa kamu tulis hari ini' is followable end-to-end… This is the
one I paste into the team channel." Arm A judged "consultant-voiced…
Anda three-plus times reads like a bank letter… I don't forward
consultant-voiced think pieces."

longform-2 · judge fb-user · V1=Arm B, V2=Arm A → **PICK VERSION 2 =
Arm A (no skill)**. The judge, 48, on Arm B: "saya terus-menerus
dipanggil 'kamu'… Saya 48 tahun, kalau sales datang ke toko saya pasti
bilang 'Pak'… kayak dibaca tulisan dari anak orang jakarta yang pintar."
On Arm A: "sopan dan saya dihormati… 'Kami tidak menjanjikan rak Anda
tidak akan pernah kosong lagi' — sales yang mengaku keterbatasannya
biasanya bukan penipu." (Arm B still earned the strongest single
moment: the quoted sample suggestion — "bukan janji, tapi tunjukkan.")

## Result: 1/2 — and the loss is a register lesson

Arm B won where the audience matched its register instinct (devs,
kamu, scannable structure) and lost where it applied "consumer =
santai-kamu" to a 35+ merchant audience who read kamu as junior.
Encoded into SKILL.md INTAKE: audience age/status weighs on register;
respectful semi-formal (Anda/Bapak-Ibu) is warmth for older merchant/
professional readers. Also noted as a candidate register.md ladder
amendment (open — land it via an issue or PR). A/B stands as run;
re-measuring needs new samples.
