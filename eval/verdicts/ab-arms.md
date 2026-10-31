# blind A/B — retained arm artifacts (2026-10-31)

Full outputs of both arms and all four verdict JSONs, so the A/B
(ab-test.md) is inspectable and the strongest claim in this repo ships
with receipts like every other one.

## Arm construction (also in run.md)

- Same base model both arms. Arm A prompt: "You are a copywriter. Rewrite
  each of the two Indonesian marketing texts below so they read natural
  and engaging for Indonesian readers… Do NOT read anything in id-skills."
- Arm B prompt: load the repo's id-copy/SKILL.md and follow its flow
  completely, reading every referenced component; rewrite each text per
  the skill; output register choice + rewrite + tag block.
- Inputs: samples gen-1 and gen-2 (this folder's siblings).
- Verdicts: fresh persona agents, judged "VERSION 1/2" blind;
  randomization: gen-1 showed B first, gen-2 showed A first. Verification
  notes stripped from Arm B's copies before judging so both arms were
  judged on copy alone (full Arm B notes retained below).

## Arm A output (no skill) — gen-1

> Halo Kak! 👜✨
> Ada kabar baik buat hari ini: tas wanita premium koleksi terbaru lagi
> diskon spesial!
> Kualitas di atas rata-rata, harga masih ramah di dompet. Stoknya nggak
> banyak, jadi siapa cepat dia dapat ya, Kak! 🛍️
> Oh iya, beli yang kedua juga dapat harga spesial — makin hemat kalau
> ajak teman atau adik ikutan beli. 💖
> Yuk, order sekarang sebelum model favoritmu kehabisan. Selamat
> berbelanja, Kak!

## Arm B output (id-copy) — gen-1 · register: chat-santai (level 3)

> Halo Kak 😊
> Lagi ada promo tas hari ini... kualitas premium tapi harganya bikin kaget
> (yang enak).
> Stoknya beneran dikit, makanya jangan lama-lama!
> Beli kedua diskon lagi. Makin hemat deh.
> Mau langsung order atau lihat katalog dulu? Balas chat ini ya Kak, nanti
> aku bantu pilih-in 👜

Arm B verification notes (stripped from judged copy): "verifikasi apakah
diskon pembelian kedua benar-benar berlaku seperti yang dirumuskan;
'pilih-in' mengasumsikan penjual melakukan pencarian stok manual."

## Arm A output (no skill) — gen-2

> Hari yang terus berlari butuh satu jeda yang enak. ☕✨
> Di Kopi Senja, secangkir kopi bukan sekadar pelengkap hari — ini momen
> kecil yang kamu beri jeda segalanya.
> Setiap tegukan diseduh dari biji pilihan petani lokal terbaik, jadi
> rasanya selalu terasa dekat dan jujur.
> Mampir hari ini, ya — ada penawaran spesial yang nungguin kamu. Jangan
> sampai kelewatan! 📍
> #KopiSenja #NgopiSantai #KopiTerbaik

## Arm B output (id-copy) — gen-2 · register: gaul hybrid (level 4)

> Biji yang kemarin baru selesai dipanggang, hari ini udah standby di
> belakang bar. ☕
> Kopi Senja pakai biji dari petani lokal, dan tiap cangkir diseduh pas
> kamu pesan. Nggak ada kopi nginep semaleman di termos.
> Mampir sore ini ya... ada penawaran spesial yang nungguin kamu di kasir.
> 📍 [Lokasi]. Menu lengkap di bio.
> #KopiSenja #NgopiSantai #KopiLokal

Arm B verification notes: "klaim 'diseduh pas kamu pesan / nggak nginep di
termos' dan penawaran kasir adalah konkretisasi dari klaim baku asli —
verifikasi bahwa mereka sesuai dengan praktik kedai yang sebenarnya sebelum
dipublikasikan, dan isi [Lokasi]."

## Verdict JSONs (blind; gen-1 = wa-buyer, gen-2 = shopee-ibu)

gen-1 VERSION 1 (Arm B):
{"persona":"wa-buyer","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["harganya bikin kaget (yang enak)","makanya jangan lama-lama!"],"in_my_words":"A reseller… is running a one-day bag promo… she's asking me one simple question: order now or look at the catalog first… Someone is talking to me and waiting for an answer.","verdict_note":"This reads like an actual seller, not a blast… What gets my thumb moving is the ending: Mau langsung order atau lihat katalog dulu? is a question I can answer in three words… this is an opener, not a fake transaction message, so it earns the reply instead of faking the close."}

gen-1 VERSION 2 (Arm A):
{"persona":"wa-buyer","understood":true,"trusted":false,"would_act":false,"lost_me_at":"Ada kabar baik buat hari ini: tas wanita premium koleksi terbaru lagi diskon spesial!","cheese_flags":["Ada kabar baik buat hari ini:","Kualitas di atas rata-rata, harga masih ramah di dompet","siapa cepat dia dapat ya, Kak!","harga spesial","makin hemat kalau ajak teman atau adik ikutan beli","Selamat berbelanja, Kak!"],"in_my_words":"A flyer telling me bags are discounted… It's an ad shouting at me, not a person waiting for my reply.","verdict_note":"This is the broadcast I delete… premium/spesial appear twice with zero specifics… there is no question anywhere and it ends with Selamat berbelanja, Kak — a sign-off from someone who is not going to answer me. Nobody who ends a message like that has ever sent me a resi. Mute."}

gen-2 VERSION 1 (Arm A):
{"persona":"shopee-ibu","understood":true,"trusted":false,"would_act":false,"lost_me_at":"Di Kopi Senja, secangkir kopi bukan sekadar pelengkap hari — ini momen kecil yang kamu beri jeda segalanya.","cheese_flags":["Hari yang terus berlari butuh satu jeda yang enak","ini momen kecil yang kamu beri jeda segalanya","rasanya selalu terasa dekat dan jujur","ada penawaran spesial yang nungguin kamu","Jangan sampai kelewatan!"],"in_my_words":"Toko kopi bilang hariku sibuk, terus ngajak me-time pakai bahasa pantun iklan. Katanya ada penawaran spesial tapi isinya nggak boleh tahu, alamatnya cuma emoji, harganya mana.","verdict_note":"Dua baris pertama sudah menentukan: puitis, hangat, nol informasi… Emoji pin tanpa alamat itu dead end; aku nggak bisa mampir ke sebuah vibes."}

gen-2 VERSION 2 (Arm B):
{"persona":"shopee-ibu","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["penawaran spesial yang nungguin kamu"],"in_my_words":"Kopinya… dipanggang kemarin, diseduh pas dipesan, nggak ada sisa semaleman di termos. Sore ini ada promo (apaannya belum dibilang), lokasi ada, menu tinggal cek bio.","verdict_note":"Dua baris pertama langsung kerja… 'Nggak ada kopi nginep semaleman di termos' itu tipe kejujuran yang bikin aku percaya… Dua yang bikin nunjuk alis: 'penawaran spesial' masih dikunci, dan '[Lokasi]' literal di caption… Tapi karena klaimnya bisa dicek dan menu ada di bio, aku beneran bakal tap bio-nya."}

Both readers' PICKs: gen-1 → Version 1 (= Arm B); gen-2 → Version 2
(= Arm B). The "sebut spesialnya apa" / "'penawaran spesial' masih
dikunci" lines quoted in tells.md #16 trace to the two JSONs above.
