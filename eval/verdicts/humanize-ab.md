# id-humanizer — blind A/B (2026-10-31, loop 5)

n=2 · same harness both arms · blind judges · randomized (recorded) ·
no rerun. Same co-evolution/authorship caveats as ab-test.md.

## Arms

- **Arm A (no skill):** fresh agent, plain instruction ("perbaiki dua
  teks Indonesia di bawah agar terdengar lebih natural dan manusiawi"),
  no repo access.
- **Arm B (id-humanizer):** fresh agent loads `id-humanizer/SKILL.md` +
  voice.md/tells.md/register.md, full 5-step flow; change lists stripped
  before judging.

## Arm A — humanize-1 (announcement)

> **PENGUMUMAN: Perubahan Jam Operasional Layanan Pelanggan**
>
> Mulai 1 Desember, layanan customer service RuteKita akan buka hingga
> pukul 21.00 WIB setiap hari, termasuk Sabtu dan Minggu. Kami
> memperpanjang jam operasional agar Anda lebih leluasa menghubungi
> kami. Terima kasih atas dukungan Anda selama ini.

## Arm B — humanize-1 (announcement)

> **PENGUMUMAN: Perubahan Jam Operasional Layanan Pelanggan**
>
> Mulai 1 Desember, layanan pelanggan RuteKita beroperasi hingga pukul
> 21.00 WIB setiap hari, termasuk hari Sabtu dan Minggu. Perubahan ini
> kami lakukan sebagai bentuk komitmen untuk meningkatkan kualitas
> pelayanan demi kepuasan mitra dan pengguna. Kami berharap seluruh
> pengguna dapat memperoleh manfaat maksimal dari peningkatan layanan
> ini. Demikian pengumuman ini kami sampaikan. Atas perhatian dan kerja
> sama pengguna, kami ucapkan terima kasih.

(Arm B kept the closing formula as "genre convention" — a voice-ledger
judgment its change list named; see finding below.)

## Arm A — humanize-2 (report)

> Ada kabar baik dari proyek fitur cetak struk termal. Tim produk sudah
> mengujinya di 12 toko pilot, dan tingkat keberhasilan cetaknya mencapai
> 94%. Keluhan utamanya kertas macet di 2 toko. Penyebabnya driver
> printer yang belum optimal, dan perbaikannya sudah dijadwalkan pekan
> depan.

## Arm B — humanize-2 (report)

> Ada kabar menggembirakan dari proyek fitur cetak struk termal: tim
> produk telah menguji fitur tersebut di 12 toko pilot, dan hasilnya
> menunjukkan tingkat keberhasilan cetak sebesar 94%. Selain itu,
> keluhan utama adalah kertas yang macet di 2 toko. Masalahnya berasal
> dari driver printer yang belum optimal. Perbaikan driver dijadwalkan
> pada pekan depan. Demikian laporan kemajuan ini disusun untuk menjadi
> bahan pertimbangan bersama.

(Arm B deliberately kept the report's closing formula + protected the
stance word "menggembirakan" + kept the agent-less passive "dijadwalkan"
because the source names no repairer — both flagged in its change list.)

## Verdicts (blind)

humanize-1 · judge fb-user · V1=Arm A, V2=Arm B → **PICK VERSION 1 =
Arm A (no skill)**. On V2: "saya seperti membaca surat dari kantor
kelurahan… 'demikian pengumuman ini kami sampaikan' — penutup surat
resmi yang distempel, bukan yang diucapkan orang." On V1: "alasannya
ditujukan buat saya… terasa seperti ditulis orang yang tahu kita kadang
baru sempat chat cs sore atau malam."

humanize-2 · judge dev-docs · V1=Arm B, V2=Arm A → **PICK VERSION 2 =
Arm A (no skill)**. On V1: "penutup 'Demikian laporan kemajuan ini
disusun…' — closer surat dinas… begitu closer itu muncul, alarm 'ini
template/generated' nyala." On V2: "cara teammate nulis update standup…
paragrafnya berhenti di fakta yang actionable — nggak ada upacara
penutupan."

## Result: 0/2 — the skill protected its own target

Root cause, both losses identical: Arm B treated formulaic closers
("Demikian X kami sampaikan", "Atas perhatian dan kerja sama…") as
genre conventions to preserve; both blind readers flagged exactly those
lines as the machine layer. The skill's distinction (voice vs tell)
mis-classified boilerplate as voice. **Fixed in voice.md** ("Formulaic
closers are tells, not voice" — default cut/compress, keep only for
official surat dinas). Recorded honestly: the fix postdates the A/B;
re-measuring requires new samples (no-rerun rule).

Notable: Arm B's *other* protections survived reader scrutiny — the
stance word, the agent-less passive ("dijadwalkan sama siapa?" was the
judge's content gripe, and Arm B's flag of exactly that question was
correct process), the facts verbatim. The skill's ledger discipline
worked; its genre-formula default didn't.
