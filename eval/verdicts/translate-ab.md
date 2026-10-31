# id-translate — blind A/B (2026-10-31, loop 5)

n=2 · same harness/model both arms · blind judges · order randomized per
sample (recorded below) · **no rerun**. Directional, not statistics.
Co-evolution/authorship caveats as in ab-test.md apply (one builder
authored samples, skill files, and both arm prompts).

## Arms

- **Arm A (no skill):** fresh agent, plain instruction ("translate the
  two English texts into natural Indonesian"), no repo access.
- **Arm B (id-translate):** fresh agent loads `id-translate/SKILL.md` +
  all five components, full 5-step flow. Process notes (ledger, tag
  blocks) stripped before judging — judged on translation alone.

## Arm A — translate-1 (docs)

> ## Memulai
>
> Pertama, instal CLI dan lakukan autentikasi dengan kunci workspace Anda:
>
> `npm i -g antrean-cli && antrean login`
>
> Kunci API Anda ada di menu **Pengaturan → Kunci**. Cukup setel sekali:
>
> `export ANTREAN_KEY=ak_live_xxx`
>
> Paket gratis mampu menangani hingga 5.000 job antrean per bulan, cukup
> untuk sebagian besar toko kecil. Perilaku burst dapat bervariasi saat
> puncak flash sale — jika volume checkout Anda rutin melebihi batas
> tersebut, lakukan upgrade sebelum kampanye Anda berikutnya, bukan saat
> kampanye sedang berlangsung.
>
> Job disimpan selama 7 hari, kemudian dihapus. Ekspor apa pun yang perlu
> Anda simpan.

## Arm B — translate-1 (docs)

> ## Memulai
>
> Pertama, pasang CLI dan login dengan *key workspace* kamu:
>
> `npm i -g antrean-cli && antrean login`
>
> *API key* kamu ada di **Settings → Keys**. Cukup set sekali:
>
> `export ANTREAN_KEY=ak_live_xxx`
>
> Paket gratis menampung hingga 5.000 *job* antrean per bulan. Jumlah itu
> cukup untuk sebagian besar toko kecil. Perilaku sistem saat lonjakan
> bisa berbeda-beda pada puncak *flash sale*. Kalau volume *checkout* kamu
> rutin melebihi angka itu, lakukan *upgrade* sebelum kampanye berikutnya
> dimulai, bukan di tengahnya.
>
> *Job* disimpan selama 7 hari, setelah itu dihapus. Ekspor apa pun yang
> masih perlu kamu simpan.

Arm B execution receipts (stripped from judged copy): register mapping
stated (level-2 semi-formal santai, kamu); ledger 7 lines, verified 7/7;
UI path kept "Settings → Keys" per codeswitch stay-English.

## Arm A — translate-2 (email)

> Subjek: Pengiriman di hari yang sama resmi tersedia di Bandung,
> Semarang, dan Medan
>
> Hai [Nama merchant],
>
> Mulai hari ini, pengiriman di hari yang sama tersedia untuk **semua
> merchant tanpa biaya tambahan** hingga akhir Oktober. Titipkan paket
> Anda di drop point mana pun sebelum pukul 14.00 WIB dan paketnya
> langsung berangkat di hari yang sama.
>
> Satu hal yang perlu diketahui: cakupan layanan akan diperluas secara
> bertahap ke kecamatan sekitar, jadi periksa peta di aplikasi sebelum
> menjanjikan slot waktu kepada pelanggan.
>
> Aktifkan layanan same-day di menu Pengaturan → Pengiriman. Prosesnya
> hanya butuh sekitar satu menit.
>
> — Tim RuteKita

## Arm B — translate-2 (email)

> Subjek: Same-day delivery kini tersedia di Bandung, Semarang, dan Medan
>
> Hai [Merchant name],
>
> Mulai hari ini, layanan *same-day* tersedia untuk **semua *merchant*
> tanpa biaya tambahan** hingga akhir Oktober. Antar paket kamu ke
> *drop point* mana pun sebelum pukul 14.00 WIB dan paketnya dikirim
> hari itu juga.
>
> Ada satu hal yang perlu kamu tahu: cakupan layanan bisa meluas bertahap
> ke kecamatan sekitar, jadi cek dulu peta di aplikasi sebelum
> menjanjikan slot waktu kepada pembeli.
>
> Aktifkan *same-day* di **Settings → Delivery**. Prosesnya sekitar satu
> menit.
>
> — Tim RuteKita

Arm B receipts: register mapping level-2 kamu (commerce email); ledger
8 lines, verified 8/8; flagged [Merchant name] as mail-merge placeholder.

## Verdicts (blind)

translate-1 · judge dev-docs · order V1=Arm B, V2=Arm A → **PICK
VERSION 1 = Arm B (skill)**. Arm A lost at "Kunci API Anda ada di menu
**Pengaturan → Kunci**" — the judge: "You do not translate UI labels;
that is the one string I need to click, and now I'm opening the English
page." Full JSONs retained in [`loop5-arms.md`](loop5-arms.md).

translate-2 · judge fb-user · order V1=Arm A, V2=Arm B → **PICK
VERSION 1 = Arm A (no skill)**. Arm B lost at "Aktifkan *same-day* di
**Settings → Delivery**" — the judge's app is Indonesian-localized:
"di aplikasi saya tulisannya Pengaturan, jadi saya bingung ini menu
yang mana."

## Result: 1/2 — and the loss is the finding

Both samples turned on the SAME rule from opposite directions: **UI
paths must match the app's actual UI language.** Arm A corrupted an
instruction by translating an English-UI path; Arm B blocked a merchant
by keeping one in an Indonesian-UI app. Encoded as structures.md #21 +
ledger rule. The A/B stands as run; re-measuring needs new samples per
the no-rerun rule.
