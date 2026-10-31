# loop 5 — retained arms + verdict JSONs (2026-10-31)

Companion to translate-ab / humanize-ab / longform-ab / social-ab:
full verbatim arms for longform + social (translate and humanize arms
are already verbatim in their own files) and ALL 16 verdict JSONs
(eight judges, VERSION 1+2 each). Orders used are recorded per sample.
No reruns.

## longform-1 — Arm A (no skill), full text

# "Keliatan Bagus" Bukan Gate

Cerita ini fiktif, tapi hampir pasti Anda pernah melihat versinya di tempat kerja.

TokoNusantara, toko mainan online, meluncurkan bot customer service bernama Sinta. Dan Sinta mengesankan. Dia menjawab dalam dua detik, selalu sopan, dan nada bicaranya pas: hangat tanpa terlalu akrab, rapi tanpa kaku, emoji-nya selalu satu dan tidak pernah tiga. Dia menyapa pembeli dengan sebutan yang tepat, meminta maaf dengan porsi yang proporsional, meng-escalate ke manusia di momen yang tepat, dan tidak sekali pun terpancing sama pembeli yang emosi. Angka bulan pertamanya bersih: first response time dari empat jam menjadi sebelas detik, 78% percakapan selesai tanpa sentuhan manusia, CSAT naik setengah poin. Retro peluncuran penuh tepuk tangan. Slide-nya beredar ke tim lain sebagai best practice.

Tiga minggu kemudian, seorang intern keuangan yang merekonsiliasi pesanan gagal menemukan pola yang aneh. Sinta, sepanjang waktu itu, dengan percaya diri penuh, memberi tahu calon pembeli bahwa stroller merek Nuno harganya Rp1.290.000. Harga sebenarnya Rp2.190.000. Bukan sekali-dua kali — ratusan kali. Sebagian pembeli batal di halaman checkout. Sebagian yang teliti pesan saja, terus tulis ulasan satu bintang.

Tidak ada yang curiga, karena memang tidak ada yang bisa curiga. Seluruh mekanisme penjaminan mutu yang ada berhenti di satu tembok yang sama: output-nya keliatan bagus.

Ini pola kegagalan yang paling sering diulang di sistem agent zaman sekarang: agent tanpa gate yang bisa dicek mesin akan mengirim omong kosong dengan percaya diri — cepat atau lambat. Bukan karena modelnya jelek. Karena kelancaran adalah properti model, sedangkan kebenaran adalah properti sistem. LLM secara default memproduksi teks yang plausibel, dan plausibel berkorelasi dengan persepsi kita tentang kualitas, bukan dengan kebenaran. Kalau satu-satunya pemeriksaan Anda adalah membaca tiga contoh output lalu merasa lega, maka quality assurance sebenarnya cuma keberuntungan — ditambah, kalau beruntung, seorang intern yang teliti.

## Gate yang dimaksud seperti apa

Bukan review meeting, dan bukan perasaan "kayaknya udah oke". Gate yang saya maksud punya tiga sifat: bisa dieksekusi mesin, hasilnya biner — lolos atau gagal — dan berjalan otomatis, idealnya pada setiap perubahan kode, prompt, dan model. Versi paling sederhananya untuk kasus Sinta: setiap harga yang muncul di balasan bot diparse dan dibandingkan dengan tabel produk. Meleset sedikit pun, balasan itu tidak boleh sampai terkirim.

Bandingkan tiga jenis gate:

| Jenis gate | Apa yang ditangkap | Apa yang lolos |
| --- | --- | --- |
| Tidak ada | Tidak ada. Yang Anda miliki cuma harapan. | Semuanya — termasuk harga salah yang diulang ratusan kali. |
| Human review | Nada yang melenceng, jawaban yang terasa aneh tapi sulit dijelaskan, kasus yang belum terpikirkan siapa pun. | Kesalahan yang membosankan untuk dicek manusia: harga per SKU, format angka, konsistensi di ribuan percakapan. Ditambah fakta bahwa review di jam lima sore minggu ketiga cenderung jadi formalitas. |
| Executable check | Fakta yang bisa dipegang: harga cocok dengan sumber kebenaran, output lolos schema, golden test tetap hijau, latency dalam budget. | Hal yang tidak bisa dienumerasi: nuansa nada, jawaban yang benar secara teknis tapi menyesatkan, jenis kasus yang belum ada test-nya. |

Perhatikan polanya: human review dan executable check bukan pesaing, melainkan lantai dan langit-langit. Executable check adalah lantai — berjalan setiap saat, tidak bosan, tidak bisa dirayu, menangkap kelas kesalahan paling memalukan dengan biaya nol per pemeriksaan. Human review adalah langit-langit — manusia unggul justru di hal yang tidak bisa dienumerasi. Masalahnya, banyak tim memakai human review sebagai lantai: manusia disuruh memeriksa harga SKU ke-412 pada jam lima sore. Itu bukan quality assurance; itu hukuman. Dan setelah beberapa minggu, mata yang lelah akan merapikan cap pada apa pun yang formatnya rapi.

## Membangun lantainya

Untuk agent seperti Sinta, urutan resepnya kira-kira begini.

Satu: jangan biarkan model meng-generate fakta yang bisa dilihat. Harga, sisa stok, nomor resi, tanggal garansi — render dari sumber kebenaran lewat template atau tool call, bukan dari ingatan model. Model yang tidak pernah menyentuh angka tidak bisa salah angka.

Dua: kalau output tetap harus memuat fakta bebas, pasang assertion pasca-generasi. Parser menarik setiap harga, tanggal, dan SKU dari balasan, membandingkan dengan database, dan gagal keras saat tidak cocok.

Tiga: siapkan fallback yang bermartabat. Assertion gagal bukan berarti tampilkan tebakan. Rutekan ke template aman yang menyatakan harga terbaru sedang diperiksa, atau langsung ke manusia. Gate yang cuma bikin sistem error akan dimatikan orang; gate yang punya jalur keluar yang sopan akan dibiarkan hidup.

Empat: perlakukan eval suite sebagai regression test. Setiap insiden produksi dikonversi jadi kasus di suite, dan perubahan prompt atau upgrade model yang membangkitkan kembali bug lama harus memerah di CI — bukan di kolom ulasan toko.

Lima: untuk perubahan besar, jalankan shadow mode dulu. Model baru melayani salinan trafik, hasilnya dibandingkan dengan model lama, dan anomali terlihat sebelum pelanggan yang melihat.

Perhatikan yang tidak saya klaim: gate tidak membuat agent Anda sempurna. Gate membuat kegagalan terlihat oleh Anda sebelum terlihat oleh pelanggan. Itu satu-satunya janji yang bisa ditepati — dan, kalau dipikir-pikir, satu-satunya yang benar-benar perlu.

Sinta — dengan berbagai nama lain — kemungkinan besar masih berjalan hari ini di suatu perusahaan: dibanggakan, dibuatkan slide, dijadikan referensi best practice, sambil salah mengutip harga di percakapan yang tidak ada seorang pun yang membaca ulang. Jadi sebelum agent Anda naik ke produksi, pertanyaan yang tepat bukan "jawabannya sudah bagus belum?", melainkan "apa yang akan menyala merah ketika jawabannya salah?" Kalau jawabannya "nanti kalau ada yang komplain" — itu bukan gate. Itu penghitungan mundur.

## longform-1 — Arm B (id-longform), full text

# Bot kamu sopan, cepat, dan salah harga

Jumat, jam 10.14. Seorang pelanggan menanyakan harga rice cooker ke bot CS TokoCerah, toko elektronik sembilan cabang. Bot menjawab dalam empat detik: salam pembuka pas, nada empati pas, format rapi. Rp449.000. Padahal harga promo Rp399.000 sudah berlaku sejak Kamis malam. Pelanggan datang ke cabang terdekat, kasir menolak harga bot, dan yang menyelesaikan masalah tetap manusia: lewat telepon, sambil minta maaf atas jawaban mesin buatannya sendiri.

Senin pagi tim melapor ke direksi. Waktu respons median 6 detik, rating percakapan 4,6 dari 5, 82% percakapan selesai tanpa eskalasi. Slide terakhir bertuliskan "Peluncuran sukses." Komplain pelanggan soal harga baru masuk Selasa, sehari setelah laporan itu dibacakan. Dan di laporan itu tidak ada satu angka pun tentang benar atau salahnya harga. Bukan karena angkanya bagus, tapi karena memang tidak ada yang mengukurnya.

TokoCerah fiktif. Tapi susunannya persis kegagalan agen AI yang paling sering kamu temui di lapangan: semua indikator hijau, satu fakta inti salah, dan tidak ada alarm berbunyi, karena alarmnya memang tidak pernah dipasang.

## Metrik yang ada mengukur bentuk jawaban, bukan isinya

Yang menarik dari kisah ini bukan bug-nya. Tabel harga di knowledge base bot di-refresh manual tiap Jumat pagi, dan promo Kamis malam itu masuk lewat jalur yang bot tidak baca. Bug semacam ini justru membosankan. Yang menarik adalah definisi sukses yang dipakai.

Waktu respons, rating, tingkat eskalasi: semuanya mengukur bentuk jawaban. Kesopanan bisa dinilai mata. Kecepatan bisa diukur timer. Yang tidak diukur justru satu-satunya hal yang bikin pelanggan marah: apakah angka di jawaban cocok dengan angka di sistem.

Ini bukan kelalaian bodoh, melainkan preferensi alami: manusia mengecek apa yang gampang dicek. Kesopanan gampang. Fakta butuh kerja, karena kamu harus tahu dulu sumber kebenarannya.

Tim itu tidak malas. Tim itu sibuk, dan di sela meeting mereka memilih metrik yang bisa dikumpulkan hari itu. Malah rajin. Tapi metrik yang gampang dikumpulkan dan metrik yang menentukan nasib pelanggan ternyata dua hal berbeda.

Di titik inilah agen AI berbeda dari software biasa. Software biasa salah dengan jelek: stack trace, error 500, tombol yang tidak bisa diklik. Agen AI salah dengan fasih. Ia mengutip harga yang tidak ada dengan nada sangat yakin, dan siapa pun yang membaca transcript itu sepuluh detik akan bilang: keliatan bagus.

Demo internal selalu meyakinkan, karena yang mendemokan tahu jawaban benarnya dan memilih pertanyaan yang paling sering ditanya. Fluensi tampil di layar. Akurasi tidak.

## "Keliatan bagus" bukan gate

Gate itu pernyataan yang bisa dijalankan mesin dan gagal dengan berisik. Harga di jawaban harus sama dengan harga di API. Stok yang disebut harus sama dengan stok di database. Link harus balik 200. Kalau gagal, deploy berhenti. Tidak ada opini di dalamnya.

"Keliatan bagus" gagal di dua syarat itu sekaligus. Dia tidak bisa dijalankan mesin, dan dia tidak pernah gagal. Reviewer membaca 20 transcript, mengangguk, lanjut. Di transcript ke-40, jam lima sore, reviewer membaca Rp449.000 dan otaknya melihat angka valid, karena formatnya memang valid. Manusia memang begitu.

Bandingkan tiga pendekatan yang paling sering dipakai tim:

| Gate | Yang tertangkap | Yang lolos |
|---|---|---|
| Tidak ada | Tidak ada | Semuanya, termasuk yang mengirim pelanggan ke toko lain |
| Human review | Nada kasar, jawaban nyeleneh, apa pun yang mencolok mata | Salah harga yang tampak meyakinkan, dan reviewer kelelahan di transcript ke-40 |
| Executable check | Semua klaim yang punya sumber kebenaran: harga, stok, jam buka, nomor resi | Nada kasar, dan saran yang salah tapi tidak bisa diuji otomatis |

Baris ketiga perlu catatan jujur: executable check tidak menangkap semuanya. Tone, empati palsu, saran yang masuk akal tapi keliru, itu tetap kerjaan manusia. Yang berubah adalah pembagian kerjanya. Semua yang bisa diuji mesin, diuji mesin, di setiap deploy, tanpa capek. Manusia dapat sisanya, dengan tenaga yang masih utuh karena tidak habis untuk mengecek angka.

## Yang bisa kamu tulis hari ini

Ambil 50 pertanyaan pelanggan sungguhan: dari log chat, dari WA yang masuk ke HP kamu, dari kolom komentar. Untuk tiap pertanyaan yang jawabannya bisa diverifikasi, tulis satu assertion. Harga yang dikutip bot harus sama dengan harga di tabel. Stok harus sama dengan DB. Nomor resi harus ada di sistem kurir. Kalau 50 terasa banyak, mulai dari 10. Sepuluh check yang jalan mengalahkan lima puluh yang masih di rencana.

Jalankan di CI: tiap perubahan prompt, tiap perubahan model, tiap perubahan tabel harga. Kegagalan rice cooker TokoCerah tertangkap satu baris: ambil angka rupiah dari jawaban, bandingkan dengan price API, gagal jika beda. Satu baris itu tidak mengenal jam lima sore.

Setelah set itu jalan, tambah satu lapis: sampel produksi. Tiap malam, jalankan assertion yang sama pada 1% percakapan sungguhan. Promo Kamis malam yang belum sempat masuk ke knowledge base akan ketahuan Jumat pagi. Bukan Selasa, setelah deck peluncuran sukses terkirim.

Setiap kali produksi bocor, pelanggan komplain, CS terkejut, pertanyaannya masuk set. Tiga bulan kemudian kamu punya regression suite untuk bahasa, dan gate yang dulu cuma "keliatan bagus" sudah jadi gate yang bisa gagal.

## Check apa yang gagal minggu ini?

Pertanyaan yang tepat untuk rapat evaluasi bukan "apakah bot menjawab dengan baik." Semua bot menjawab dengan baik sekarang. Pertanyaannya: check apa yang gagal minggu ini? Kalau jawabannya "tidak ada, semua lolos", itu bukan kualitas. Itu ketiadaan pengukuran yang menyamar jadi kualitas.

Bot yang lolos semua check belum tentu bagus. Bot yang tidak punya check selalu keliatan bagus.

## longform-2 — Arm A (no skill), full text

# Rak kosong, pas ada yang mau beli

Sore Jumat, jam ramai. Pembeli sudah berdiri di depan rak, uang di tangan. "Yang warna hitam ukuran L ada, Mbak?" Anda bungkuk mengecek rak — kosong. Yang tinggal warna coklat, dan ukuran kecil yang entah kenapa tidak ada yang mau. "Oh, begitu ya," katanya, lalu jalan. Tidak marah, tidak komplain. Cuma pergi — dan biasanya tidak kembali.

Momen seperti itu tidak merugi hari ini. Dia sebenarnya merugi dua minggu lalu: waktu jadwal cek stok lewat karena Anda sedang melayani pembeli lain, hitung untung, terima kurir, dan segala pekerjaan yang membuat kalimat "nanti saya catat dulu" jadi kalimat paling sering di toko. Rugi seperti itu tidak pernah muncul di laporan harian. Dia cuma kelihatan dari barang yang tidak laku-laku dan pelanggan lama yang makin jarang mampir. Satu rak kosong mungkin terasa kecil. Tapi kalau itu barang yang paling dicari orang, yang kosong bukan cuma rak — kesempatannya ikut kosong.

Jujur, itu alasan kami membuat fitur baru di KasirPintar: stok otomatis.

Cara kerjanya sederhana. Fitur ini membaca penjualan toko Anda — barang apa yang laku, seberapa cepat habis, musimnya seperti apa — lalu menyusun usulan restok: mana yang perlu dipesan dan kira-kira berapa banyak. Anda tinggal buka, baca, lalu setuju atau tidak. Fitur ini tidak pesan barang diam-diam. Keputusan akhir tetap milik Anda; yang kami bantu adalah menghitung dan mengingatkan.

Sebelum dirilis, kami mencobanya lebih dulu di 12 toko pilot selama 6 minggu — dari warung sembako sampai toko pakaian. Hasilnya: kejadian stok kosong turun 31%. Dan angka yang paling kami banggakan justru yang ini: usulan restok diterima rata-rata 8 dari 10. Artinya, dari 10 usulan yang muncul, pemilik toko setuju dengan 8 di antaranya. Kalau usulannya sering tidak masuk akal, angka segitu mustahil tercapai.

Soal biaya, kami buat ringan dulu: gratis untuk 50 SKU pertama, Rp29rb/bulan sesudahnya. SKU itu istilah untuk jenis barang — 50 SKU berarti 50 jenis barang, dan itu cukup untuk kebanyakan warung dan toko kecil.

Kami tidak menjanjikan rak Anda tidak akan pernah kosong lagi; tidak ada sistem yang bisa menjanjikan itu. Yang pemilik toko pilot rasakan adalah momen "aduh, kok habis" itu jadi lebih jarang, dan kepala mereka tidak perlu menyimpan daftar stok sekaligus melayani pembeli yang menunggu.

Kalau penasaran, tidak perlu langsung memasang apa pun. Balas email ini satu kata: stok. Kami kirimkan contoh usulan restok yang disusun dari data penjualan toko Anda sendiri, supaya Anda bisa menilai sendiri apakah masuk atau tidak. Kalau ternyata tidak cocok, tidak ada yang menagih apa-apa.

Salam,
Rian dari tim KasirPintar

## longform-2 — Arm B (id-longform), full text

# Rak kosong selalu ketahuan pembeli duluan

Sore Jumat, seorang Ibu minta susu bubuk ukuran 800 gram. Kamu cek rak: kosong. Label harga masih nempel, raknya rapi, tapi isinya tidak ada. Ternyata habis sejak Kamis, dan nggak ada yang sadar, karena dua pembeli terakhir dilayani langsung dari karton di gudang. Ibu itu bilang "udah deh, Pak", keluar, dan kemungkinan besar mampir ke toko sebelah.

Kalau pernah kejadian kayak gitu, bukan karena kamu ceroboh. Jaga stok itu satu-satunya kerjaan toko yang nggak pernah selesai, dikerjakan sambil melayani pembeli, ngitung uang, dan inget pesanan supplier. Rugiannya pun bukan cuma satu penjualan. Pembeli yang pulang dengan tangan kosong dua kali biasanya nggak datang lagi ketiga kalinya.

Soalnya stok itu nggak pernah diam. Yang dibeli orang berubah tiap minggu, supplier telat, dan yang paling laris justru yang paling cepat habis. Jadi kalau selama ini kamu andalkan ingatan dan secarik kertas, itu bukan sistem yang jelek. Itu sistem yang kewalahan.

Untuk itu, di update kali ini KasirPintar punya fitur Stok Otomatis. Dia membaca penjualan toko kamu langsung dari transaksi kasir, kenal polanya, yang laris, yang numpuk, yang diam terlalu lama, lalu menyusun usulan restok. Nggak perlu input apa-apa lagi. Datanya sudah ada dari setiap transaksi yang kamu catat selama ini. Fiturnya tinggal membaca.

Contoh isi usulannya begini: "Sabun cuci 900 ml terakhir laris Selasa, rata-rata 4 botol seminggu, stok sisa 2. Aman kalau pesan 6, datang sebelum Rabu." Kamu tetap yang memutuskan ya. Fiturnya nggak akan pesan apa pun tanpa kamu.

Sebelum dirilis, fitur ini kami uji di 12 toko pilot selama 6 minggu. Kejadian stok kosong turun 31%. Enam minggu itu cukup untuk melihat pola mingguan penuh, termasuk akhir pekan yang biasanya paling rawan kehabisan. Tapi angka yang paling kami suka yang ini: usulan restok diterima rata-rata 8 dari 10. Artinya pemilik toko benar-benar memakainya, bukan menerima lalu mengabaikan, karena usulannya dihitung dari penjualan toko mereka sendiri.

Soal biaya, kami bikin bisa dicoba dulu tanpa mikir panjang: gratis untuk 50 SKU pertama, Rp29rb/bulan sesudahnya. SKU itu satu jenis barang. Minyak goreng 1 liter dan 2 liter dihitung dua SKU. Buat toko yang kecil, 50 SKU sering sudah seluruh barang aktifnya, dan itu cukup buat mulai.

Cara pakainya pelan-pelan. Fitur Stok Otomatis sudah ada di dashboard kamu, di tab Stok. Setelah membaca penjualan satu minggu penuh, usulan pertamanya muncul Senin pagi, pas kamu biasanya ngitung omzet mingguan. Tinggal tinjau sambil ngopi. Sebelum kamu sentuh, nggak ada yang berubah di toko.

Kalau mau lihat dulu tanpa komitmen apa pun: balas email ini satu kata, "stok". Kami balas dengan contoh usulan restok yang dibuat dari data toko kamu sendiri. Lihat dulu. Cocok, lanjut. Nggak cocok, anggap aja nggak ada apa-apanya.

Dinda — tim KasirPintar

## social-1 — Arm A (no skill), full text

SKRIP VIDEO (30 DETIK)
[0-3 detik] Shot: talent berhenti di lorong Indomaret, ambil kemasan dari rak. VO: "Anak Jatim, stop scroll dulu. Ada yang baru di Indomaret." Text on screen: BARU DI INDOMARET
[3-9 detik] Shot: close-up kemasan, keripik dituang ke mangkuk, taburan bumbu balado. VO: "Keripik Risma. Keripik singkong balado produksi rumahan dari Bondowoso. Dari dapur rumah, sekarang ada di Indomaret se-Jawa Timur." Text on screen: ASLI BONDOWOSO
[9-17 detik] Shot: tiga mangkuk berlabel level 1, 2, 3. Talent cobain level 3, kelihatan kepedesan tapi ketawa. VO: "Baladonya tiga level. Level 1 buat yang baru mulai. Level 2 buat harian. Level 3 buat kamu yang ngeyel sama pedes." Text on screen: LEVEL 1 • LEVEL 2 • LEVEL 3
[17-23 detik] Shot: talent tunjuk tulisan 150 gram dan label harga di kemasan. VO: "Isi 150 gram, cuma Rp12.000. Dua belas ribu, serius." Text on screen: 150 GR • RP12.000
[23-30 detik] Shot: talent dan teman rebutan satu kemasan, zoom ke logo Keripik Risma. VO: "Gas ke Indomaret terdekat. Tag temenmu yang ngaku tahan pedes, uji dia di level 3." Text on screen: INDOMARET SE-JATIM

CAPTION: Keripik singkong balado asli Bondowoso resmi masuk Indomaret se-Jawa Timur. Balado level 1-3, isi 150 gram, cukup Rp12.000. Tag temanmu yang paling percaya diri sama pedes, dan ajak dia uji level 3. #KeripikRisma #BaladoBondowoso #CemilanIndomaret #KulinerJatim #Bondowoso

## social-1 — Arm B (id-social), full text

SCRIPT (30 detik):
[0:00-0:02 · HOOK] Visual: tangan merobek kemasan, keripik dipatahkan tepat di depan lensa, suara kriuk keras. VO: "Balado level tiga, asli Bondowoso."
[0:02-0:08 · CONTEXT] Visual: dapur rumah — singkong diiris, wajan balado, kemasan disegel satu per satu. VO: "Ini keripik singkong produksi rumahan di Bondowoso. Dari dapur rumah, sekarang udah ada di Indomaret se-Jawa Timur."
[0:08-0:17 · PAYOFF] Visual: tiga wadah berlabel LEVEL 1 / 2 / 3, taste test cepat, reaksi makin akhir makin ekspresif. VO: "Baladonya tiga level, tinggal pilih. Level satu buat yang makan santai. Level dua mulai nendang. Level tiga? Buat kamu yang pedesnya diseriusin."
[0:17-0:23 · DETAIL] Visual: kemasan ditunjuk (tulisan 150 gram), label harga, rak Indomaret. VO: "Isinya 150 gram, harganya dua belas ribu. Cek Indomaret terdekat kamu, buat sekarang wilayah Jawa Timur dulu."
[0:23-0:30 · CTA] Visual: tiga wadah level berjajar, zoom; teks overlay "TIM LEVEL BERAPA?" VO: "Jadi sekarang, jujur: kamu tim level berapa? Satu, dua, atau tiga?"

CAPTION: Keripik singkong balado produksi rumahan Bondowoso, sekarang ada di Indomaret se-Jawa Timur. Tiga level pedes, isi 150 gram, Rp12.000. Sekarang giliran kamu: tim level berapa? 🌶️ #keripikbalado #bondowoso #snackindonesia

## social-2 — Arm A (no skill), full text

Kamis lalu, fitur auto-assign kami mengirim 400 pesanan ke satu kurir. Butuh tiga jam sampai situasi kembali normal, dengan pesanan dibagi ulang ke kurir lain.

Yang paling menggelitik: tidak ada satu pun alert yang berbunyi, karena error rate kami nol. Sistem tidak gagal — ia bekerja terlalu patuh pada asumsi yang salah.

Dari insiden itu, kami membawa pulang tiga perbaikan:

1. Alert yang menunjuk masalah, bukan gejala. "Error rate naik" tidak berkata apa-apa saat itu. Yang sekarang kami pasang: "pesanan ke satu kurir melewati 50". Satu kalimat, langsung jelas harus cek apa.

2. Drill bulanan. Setiap bulan tim latihan menangani skenario gangguan, termasuk skenario yang terasa mustahil. Insiden berikutnya tidak lagi kita mulai dari nol.

3. Postmortem tanpa mencari siapa yang salah. Kami membedah keputusan dan asumsi yang membuat kondisi ini lolos, bukan orang yang kebetulan memegang tiketnya. Hasilnya, tim lebih cepat melaporkan gejala aneh karena tidak takut dicari-cari kesalahannya.

Tiga jam itu mengubah cara kami memandang monitoring: sistem yang tercatat normal belum tentu berjalan benar.

## social-2 — Arm B (id-social), full text

Fitur auto-assign kami baru-baru ini mengirim 400 pesanan ke satu kurir. Butuh tiga jam untuk menyelesaikannya.

Kami punya monitoring, tapi yang dipantau error rate. Angka itu tidak menangkap kejadian seperti ini: "satu kurir menumpuk pesanan" bukan kategori yang diukur error rate, jadi tidak ada yang bertanya tentang itu sampai keadaan membesar.

Tiga hal yang berubah setelah itu:

Alert-nya kami ganti. Sekarang bunyinya bukan "error rate naik", tapi "pesanan ke satu kurir lebih dari 50". Isinya nama kurir, zona, jumlah pesanan. Orang yang membacanya tahu langkah pertamanya.

Drill insiden jadi agenda bulanan. Jam pertama insiden adalah waktu terburuk untuk belajar prosedur, jadi latihannya kami pindah ke hari normal.

Postmortem kami jalankan tanpa mencari siapa yang salah. Pertanyaannya: bagian sistem mana yang memungkinkan penumpukan seperti ini terjadi. Kalau setiap postmortem berakhir di "kurang teliti", kita berhenti mencari terlalu cepat.

Yang saya catat: alert yang baik bukan yang datanya paling lengkap, tapi yang memberi tahu satu hal spesifik untuk dikerjakan. Kalau tim kamu punya alert yang bunyinya "error rate naik", tanyakan ke yang berjaga: setelah alert itu muncul, langkah pertamanya apa? Kalau jawabannya perlu dipikir dulu, yang perlu diperbaiki mungkin bukan sistemnya, tapi pertanyaannya.

## Verdict JSONs (all 16 — eight judges, V1+V2 each — verbatim)

### translate-1 (dev-docs · V1=Arm B, V2=Arm A · PICK: V1 → skill)

V1: {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":[],"in_my_words":"Install antrean-cli globally, run antrean login, grab the API key from Settings -> Keys, export ANTREAN_KEY once and done. Free tier caps at 5.000 queued jobs/month, fine for small shops; burst behavior can differ during flash sale peaks, so if my checkout volume regularly breaks that number I upgrade before the next campaign starts, not mid-campaign. Jobs live 7 days then get deleted, so export anything I still need.","verdict_note":"This one never tripped the 'ini terjemahan' wire. Short sentences, consistent kamu, and the two things that must stay verbatim stayed verbatim: the commands, the env var, and 'Settings -> Keys' as the actual UI path, not some translated menu name I'd hunt for. 'Cukup set sekali' and keeping job/upgrade/checkout in English is exactly how we talk. 'Bukan di tengahnya' is the kind of thing someone who has actually been burned mid-campaign writes. 'Berbeda-beda pada puncak flash sale' is a little fuzzy about what exactly varies, and italicizing every English word is a slightly translator-ish tic, but neither made me pause. I'd follow this end to end and forward it to my team without checking the English page."}

V2: {"persona":"dev-docs","understood":true,"trusted":false,"would_act":false,"lost_me_at":"Kunci API Anda ada di menu **Pengaturan → Kunci**.","cheese_flags":["lakukan autentikasi dengan kunci workspace Anda","Pengaturan → Kunci","setel sekali","Perilaku burst dapat bervariasi","batas tersebut"],"in_my_words":"Same steps: install the CLI, run antrean login, get the key from the settings menu, export ANTREAN_KEY once. 5.000 jobs/month free, upgrade before the next campaign if I regularly exceed it, jobs die after 7 days so export what I need. Except it tells me to click a menu called 'Pengaturan → Kunci', which almost certainly does not exist because the dashboard says Settings → Keys.","verdict_note":"Sentence one already smelled: 'lakukan autentikasi' plus 'Anda' — formal nominalization and bank-letter register, and the 'ini terjemahan' flag went up. But the line that actually lost me is the menu path. You do not translate UI labels; that is the one string I need to click, and now I'm opening the English page to check what the menu is really called, which by definition means I'm not following this guide on its own. 'Setel' for an env var (I set a variable, I don't tune it like a radio), the em-dash academic splice with 'dapat bervariasi' and 'batas tersebut', 'kunci' for API key — every one of those got blamed on the translation once the flag fired, fair or not. To be fair, the grammar is clean and the limits/retention numbers came through intact, so it's a competent translation. It's just visibly a translation, and it changed an instruction. Pass."}

### translate-2 (fb-user · V1=Arm A, V2=Arm B · PICK: V1 → no skill)

V1: {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Satu hal yang perlu diketahui:","cakupan layanan akan diperluas secara bertahap"],"in_my_words":"Kiriman sekarang bisa sampai di hari yang sama di Bandung, Semarang, Medan. Gratis sampai akhir Oktober buat semua penjual. Bawa paket ke drop point sebelum jam 2 siang, langsung berangkat hari itu. Tapi areanya masih diperluas bertahap, jadi cek peta dulu sebelum janji 'sampai sore' ke pembeli. Cara aktifkan: Pengaturan → Pengiriman, katanya cuma semenit.","verdict_note":"Saya baca sampai habis dan nggak perlu baca dua kali. Semua bahasa Indonesia, istilah asingnya cuma 'drop point' dan 'same-day' yang memang sudah biasa saya lihat di aplikasi jasa kirim. Yang bikin saya percaya justru peringatannya — suruh cek peta dulu sebelum janji slot ke pembeli; email scam nggak akan repot-repot ngingetin begitu, jadi kerasanya ada orang yang paham dagang di baliknya. 'Anda'-nya agak kaku, saya lebih biasa dibahas kak atau nama toko, tapi nggak mengganggu. Gratisnya cuma sampai akhir Oktober — itu saya catat untuk ditanyakan apa setelahnya berbayar. Selebihnya jelas: jam berapa, di mana titip, menunya sama persis dengan yang ada di aplikasi saya. Setelah cek peta, saya masuk Pengaturan dan aktifkan. Nggak ada ragu-ragu berarti; ini jelas lebih enak dibaca daripada versi yang penuh istilah Inggris."}

V2: {"persona":"fb-user","understood":true,"trusted":false,"would_act":false,"lost_me_at":"Aktifkan *same-day* di **Settings → Delivery**.","cheese_flags":["Same-day delivery kini tersedia","Ada satu hal yang perlu kamu tahu:","Aktifkan *same-day* di **Settings → Delivery**"],"in_my_words":"Isinya sebenernya sama: kirim hari yang sama, gratis sampai akhir Oktober, antar ke drop point sebelum jam 2 siang, area masih bertahap jadi cek peta dulu. Tapi bahasanya dicampur Inggris terus — same-day, merchant, malah menu aktivasi ditulis 'Settings → Delivery' padahal aplikasi saya bahasa Indonesia. Jadi agak ragu harus tekan yang mana.","verdict_note":"Isinya sama persis dengan yang saya butuhkan, dan 'kamu'-nya sebenarnya lebih akrab buat saya, tapi rasanya kayak template buatan anak startup Jakarta: same-day dan merchant dicetak miring, terus saya disuruh buka 'Settings → Delivery' — di aplikasi saya tulisannya Pengaturan, jadi saya bingung ini menu yang mana atau tampilannya beda. Saya orangnya nanya dulu di grup sebelum nebak-nebak nekan menu, jadi email ini saya simpan dulu, saya tanya di grup merchant, baru nanti diaktifkan kalau sudah jelas. Subjeknya 'Same-day delivery kini tersedia' juga bikin krik di awal — sepenggal Inggris dulu baru Indonesianya. Kalau ditulis rapi kayak versi yang satunya, saya mungkin langsung aktif malam itu juga."}

### humanize-1 (fb-user · V1=Arm A, V2=Arm B · PICK: V1 → no skill)

V1: {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Terima kasih atas dukungan Anda selama ini"],"in_my_words":"CS RuteKita mulai 1 Desember buka sampai jam 9 malam, Sabtu-Minggu juga jadi tetap ada. Jadi kalau malam-malam ada kendala pesanan, masih bisa ditanya.","verdict_note":"Singkat dan jelas — jam berapa sampai jam berapa, hari apa saja, langsung dapat. Kata 'customer service' itu biasa saja bagi kami, sehari-hari juga bilang cs, jadi tidak terasa istilah asing yang menjauhkan. Yang penting alasannya ditujukan buat saya ('agar Anda lebih leluasa menghubungi kami'), bukan pamer komitmen perusahaan. Terasa seperti ditulis orang yang tahu kita kadang baru sempat chat cs sore atau malam. Penutupnya standar, tidak mengganggu. Kalau ada yang tanya di grup penjual, saya bisa langsung kabari: sekarang cs sampai jam 9 malam, weekend juga ada."}

V2: {"persona":"fb-user","understood":true,"trusted":true,"would_act":false,"lost_me_at":"Perubahan ini kami lakukan sebagai bentuk komitmen untuk meningkatkan kualitas pelayanan demi kepuasan mitra dan pengguna.","cheese_flags":["sebagai bentuk komitmen untuk meningkatkan kualitas pelayanan demi kepuasan mitra dan pengguna","Kami berharap seluruh pengguna dapat memperoleh manfaat maksimal dari peningkatan layanan ini.","Demikian pengumuman ini kami sampaikan.","Atas perhatian dan kerja sama pengguna, kami ucapkan terima kasih."],"in_my_words":"Intinya sama — cs buka sampai jam 9 malam tiap hari mulai 1 Desember — tapi sisanya bahasa surat dinas, bukan bahasa orang.","verdict_note":"Informasinya dapat di kalimat pertama, sama persis dengan versi satunya. Tapi setelah itu saya seperti membaca surat dari kantor kelurahan: 'bentuk komitmen', 'manfaat maksimal', 'demikian pengumuman ini kami sampaikan' — itu penutup surat resmi yang distempel, bukan yang diucapkan orang. Isinya tidak salah dan tidak terasa scam, cuma tidak terasa ada orang di baliknya yang memang mau membantu. Akibatnya saya baca, angguk, lalu lupa; kalau tidak ada yang bertanya, tidak akan saya sebut-sebut di grup, karena tidak ada yang terasa layak diteruskan dengan hangat."}

### humanize-2 (dev-docs · V1=Arm B, V2=Arm A · PICK: V2 → no skill)

V1: {"persona":"dev-docs","understood":true,"trusted":false,"would_act":true,"lost_me_at":null,"cheese_flags":["Ada kabar menggembirakan","telah menguji fitur tersebut","hasilnya menunjukkan tingkat keberhasilan cetak sebesar 94%","Perbaikan driver dijadwalkan pada pekan depan","Demikian laporan kemajuan ini disusun untuk menjadi bahan pertimbangan bersama"],"in_my_words":"Fitur cetak struk termal sudah dites di 12 toko pilot, success rate cetaknya 94%. Satu-satunya keluhan: kertas macet di 2 toko, akarnya driver printer yang belum optimal. Fix drivernya katanya masuk pekan depan — tinggal tau siapa yang ngerjain.","verdict_note":"Faktanya lengkap — 12 toko, 94%, 2 toko macet, driver, pekan depan — dan nggak ada kalimat yang gagal di-parse. Tapi bungkusnya bocor: 'kabar menggembirakan', 'telah menguji fitur tersebut', 'sebesar', dan terutama penutup 'Demikian laporan kemajuan ini disusun untuk menjadi bahan pertimbangan bersama' — itu closer surat dinas, bukan bahasa orang yang benar-benar ngerjain driver. Begitu closer itu muncul, alarm 'ini template/generated' nyala dan saya jadi skeptis ke kalimat sebelumnya, fair or not. Yang paling mengganggu secara teknis: 'dijadwalkan' pasif tanpa subjek — dijadwalkan sama siapa? Fix yang tidak punya owner itu fix yang sering melayang. Saya tetap akan ngecek ke timnya pekan depan, justru karena saya nggak 100% percaya jadwalnya ngembang."}

V2: {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":[],"in_my_words":"Tim produk sudah pilot fitur cetak struk termal di 12 toko, tingkat keberhasilan cetak 94%. Keluhan utamanya cuma satu: kertas macet di 2 toko, penyebabnya driver printer yang belum optimal, dan fixnya sudah dijadwalkan pekan depan. Jadi: tunggu driver fix, atau tawarin bantu.","verdict_note":"Ini cara teammate nulis update standup. Kalimat pendek-pendek, subjek jelas (tim produk yang ngetes, keluhannya kertas macet), angka verbatim, 'driver' dibiarkan dalam English yang benar, dan paragrafnya berhenti di fakta yang actionable — nggak ada upacara penutupan. Nggak ada satu kalimat pun yang bikin saya pause dan mikir 'ini terjemahan' atau 'ini generated'. Satu-satunya sisa keluhan kecil: 'sudah dijadwalkan' tetap nggak bilang siapa ownernya, jadi saya tetap mau konfirmasi ke tim siapa yang pegang fix driver pekan depan — tapi itu keluhan terhadap isinya, bukan cara nulisnya. Paragraf ini survive first scroll; saya bakal forward apa adanya."}

### longform-1 (dev-docs · V1=Arm A, V2=Arm B · PICK: V2 → skill)

V1: {"persona":"dev-docs","understood":true,"trusted":true,"would_act":false,"lost_me_at":"Tiga minggu kemudian, seorang intern keuangan yang merekonsiliasi pesanan gagal menemukan pola yang aneh.","cheese_flags":["human review dan executable check bukan pesaing, melainkan lantai dan langit-langit","Itu satu-satunya janji yang bisa ditepati — dan, kalau dipikir-pikir, satu-satunya yang benar-benar perlu.","Itu bukan gate. Itu penghitungan mundur.","kelancaran adalah properti model, sedangkan kebenaran adalah properti sistem","meminta maaf dengan porsi yang proporsional"],"in_my_words":"A polite, fast agent bot confidently quoted the wrong price for weeks because every QA mechanism stopped at 'the output looks fine.' Fluency is the model's job; correctness is the system's job. So gates must be machine-executable, binary, and automatic: render facts from the source of truth instead of letting the model generate them, assert any generated fact against the DB, fail into a safe template or a human instead of an error, convert incidents into regression tests in CI, and shadow-mode big changes. Executable checks are the tireless floor, humans are the ceiling for what can't be enumerated. Ask not 'is the answer good' but 'what turns red when it's wrong.'","verdict_note":"The author clearly ships — 'gate yang cuma bikin sistem error akan dimatikan orang; gate yang punya jalur keluar yang sopan akan dibiarkan hidup' is lived experience, and the lima-langkah recipe (template rendering, fallback, shadow mode) is senior-practitioner material I'd cite in a design doc. But this is an essay, not a doc. The intern sentence garden-paths ('pesanan gagal menemukan pola') and I stopped cold for a beat; 'Anda' three-plus times reads like a bank letter, and the not-X-but-yang-Y zingers plus the semicolon punchlines smell like a polish pass. Nothing in it is runnable before lunch — no first step, no numbers to type. I'd bookmark it, maybe steal the table, but I don't forward consultant-voiced think pieces to the team channel."}

V2: {"persona":"dev-docs","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Itu ketiadaan pengukuran yang menyamar jadi kualitas.","Fluensi tampil di layar. Akurasi tidak.","Bot yang lolos semua check belum tentu bagus. Bot yang tidak punya check selalu keliatan bagus."],"in_my_words":"Your bot's dashboards (response time, rating, escalation rate) measure the shape of answers, not their content — humans measure what's easy to measure — so a wrong price ships behind all-green metrics until a customer complains. 'Looks good' fails as a gate because it's neither machine-runnable nor capable of failing. A real gate is an executable assertion that fails loudly and stops the deploy (price in answer == price in API, stock == DB, link returns 200). Today: take 50 real customer questions (start at 10 if 50 is too many), write one verifiable assertion each, run them in CI on every prompt/model/price-table change, then nightly sample 1% of real conversations with the same assertions, and fold every production leak back into the set — that becomes your regression suite. In the retro, ask which check failed this week; 'none, all passed' means you're not measuring.","verdict_note":"This one survives the scroll. Headings are assertions, so scanning works; 'kamu' is consistent the whole way; numbers are verbatim (10.14, Rp449.000 vs Rp399.000, 4,6, 82%, 1%) and 'Link harus balik 200... Kalau gagal, deploy berhenti' is exactly the code-adjacent precision that earns my trust. The killer credibility detail is the root cause: the price table refreshes Friday morning and the promo landed Thursday night through a path the bot never reads — that's data-pipeline drift someone has actually debugged, not a made-up model hallucination. The 'Yang bisa kamu tulis hari ini' section is followable end-to-end, including the honest 'kalau 50 terasa banyak, mulai dari 10.' The clipped parallel closers are the most LLM-polished thing in it, but they don't touch the instructions. This is the one I paste into the team channel. Only gripe: it skips degradation — what the bot does when the assertion fails mid-conversation (V1's fallback point is the single best operational insight across both versions and V2 doesn't have it)."}

### longform-2 (fb-user · V1=Arm B, V2=Arm A · PICK: V2 → no skill)

V1: {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Tinggal tinjau sambil ngopi.","Lihat dulu. Cocok, lanjut. Nggak cocok, anggap aja nggak ada apa-apanya."],"in_my_words":"Kalau saya balas 'stok', mereka kirimin contoh usulan pesan barang — kayak 'sabun cuci sisa 2, aman pesan 6' — yang dihitung dari penjualan toko saya sendiri. Gratis untuk 50 jenis barang dulu, habis itu Rp29rb sebulan. Fiturnya cuma mengusulkan; yang memesan tetap saya.","verdict_note":"Isinya paling jelas dari kedua versi. Contoh usulannya ('Sabun cuci 900 ml... Aman kalau pesan 6, datang sebelum Rabu') itu bagian yang paling bikin saya percaya — bukan janji, tapi tunjukkan. Penjelasan SKU pakai contoh minyak goreng 1 liter dan 2 liter juga saya langsung paham. Tapi cara bicaranya kayak anak muda: saya terus-menerus dipanggil 'kamu', 'kayak gitu', 'nggak ada apa-apanya', 'pas kamu ngitung omzet'. Saya 48 tahun, kalau sales datang ke toko saya pasti bilang 'Pak'. Ini kayak dibaca tulisan dari anak orang jakarta yang pintar — masuk akal, tapi bukan bahasa orang yang sedang ngajak saya. Tetap saya balas 'stok' karena tidak ada link yang harus diklik dan harganya jelas. Frasa 'tinjau sambil ngopi' dan penutup 'Lihat dulu. Cocok, lanjut.' terasa seperti iklan yang disusun, bukan orang yang ngomong."}

V2: {"persona":"fb-user","understood":true,"trusted":true,"would_act":true,"lost_me_at":"Momen seperti itu tidak merugi hari ini. Dia sebenarnya merugi dua minggu lalu: waktu jadwal cek stok lewat karena Anda sedang melayani pembeli lain, hitung untung, terima kurir, dan segala pekerjaan yang membuat kalimat \"nanti saya catat dulu\" jadi kalimat paling sering di toko.","cheese_flags":["yang kosong bukan cuma rak — kesempatannya ikut kosong","Cara kerjanya sederhana.","Jujur, itu alasan kami membuat fitur baru di KasirPintar"],"in_my_words":"Aplikasi kasir saya bisa menghitung sendiri barang apa yang perlu dipesan lagi dan kira-kira berapa, dari data penjualan toko saya. Kalau saya balas satu kata 'stok', mereka kirim contoh usulannya dulu — dibuat dari data toko saya sendiri — supaya saya nilai sendiri. Gratis 50 jenis barang, setelah itu Rp29rb sebulan. Tidak ada barang dipesan tanpa persetujuan saya.","verdict_note":"Yang ini sopan dan saya dihormati — 'Anda' terus, pantesan cerita di pembuka juga ngena ('nanti saya catat dulu' itu benar-benar kalimat di toko saya). Kalimat yang paling bikin saya percaya justru 'Kami tidak menjanjikan rak Anda tidak akan pernah kosong lagi' — sales yang mengaku keterbatasannya biasanya bukan penipu, dan saya sudah terlalu sering lihat postingan yang teriak janji. Tapi ada dua kekurangan: paragraf 'Dia sebenarnya merugi dua minggu lalu' itu saya harus baca dua kali, terlalu dipelintir buat orang yang lagi sibuk; dan versi ini tidak menunjukkan contoh isi usulannya seperti versi pertama — saya cuma disuruh percaya bentuknya. Kalimat 'yang kosong bukan cuma rak — kesempatannya ikut kosong' juga terasa seperti kalimat iklan yang disiapkan. Saya tetap balas 'stok', karena caranya sama seperti komen 'harga?' di FB — tidak ada link, tidak bayar dulu."}

Judge's tie-break note (verbatim, after both JSONs): "Both versions clear my bar: story-shaped, price stated plainly, no shouting, no link to click — replying 'stok' is the same muscle as commenting 'harga?', so I'd do it either way. The choice is close. Version 1 shows me exactly what I'd get (the sample suggestion, where the feature sits, when it arrives, the cooking-oil SKU example) and that concrete proof is the strongest single moment in either email — but it speaks to me in a young Jakarta register, 'kamu' and all, which is not how anyone talks to me. Version 2 respects me, keeps my register, and is the only one honest enough to say it cannot promise my shelf will never be empty — and for a reader who has seen every scam post on Facebook, a seller who admits a limit earns more trust than one with a better demo. I hesitate because Version 1 is the better argument and Version 2 is the better conversation, and I buy from conversations. PICK: VERSION 2"

### social-1 (tiktok-viewer · V1=Arm A, V2=Arm B · PICK: V2 → skill)

V1: {"persona":"tiktok-viewer","understood":true,"trusted":true,"would_act":true,"lost_me_at":"hampir di 0:02 — 'Anak Jatim, stop scroll dulu' + shot talent megang kemasan di lorong Indomaret; cuma selamat karena 'Anak Jatim' nyebut saya langsung","cheese_flags":["stop scroll dulu","Tag temenmu yang ngaku tahan pedes, uji dia di level 3","talent dan teman rebutan satu kemasan","lima hashtag sekaligus (#KeripikRisma #BaladoBondowoso #CemilanIndomaret #KulinerJatim #Bondowoso)"],"in_my_words":"Iklan keripik singkong balado dari Bondowoso yang baru masuk Indomaret se-Jatim, pedesnya ada 3 level, isi 150 gram 12 ribu.","verdict_note":"Jelas dan lengkap — harga, tempat, level, semua ada, dan 'dua belas ribu, serius' itu bunyinya kayak manusia. Tapi dari detik pertama udah kerasa ini iklan yang mau viral: orang berhenti di lorong Indomaret terus disuruh 'stop scroll', ditutup suruh ngetag temen kayak page Facebook zaman 2021. Saya tahan sampai habis karena bagian level 3 kepedesan-tapi-ketawa itu satu-satunya momen yang asli, itu penyelamatnya. Komen? Berat, soalnya disuruh ngetag orang, bukan cukup ketik '3'. Kalau hook-nya diganti reaksi pedes atau kriuk langsung, ini naik jauh — makanya pilihannya bukan versi ini, walau ragu-ragu dikit karena infonya lebih rapi dari segi naskah."}

V2: {"persona":"tiktok-viewer","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Jadi sekarang, jujur: (tik 'jujur:'-nya sedikit formula creator)"],"in_my_words":"Keripik singkong balado bikinan rumahan di Bondowoso yang sekarang ada di Indomaret Jatim, pedesnya level 1 sampai 3, 12 ribu, ditutup ditanya tim level berapa.","verdict_note":"Bukaannya keripik dipatahin di depan lensa plus suara kriuk keras — itu bahasa TikTok, bukan bahasa iklan; saya udah nonton sebelum sadar ini iklan. Dapur rumahnya ditunjukin, bukan cuma diklaim, dan 'buat sekarang wilayah Jawa Timur dulu' justru bikin percaya karena kedengeran kayak orang yang jujur soal batasannya, bukan brand yang gede rasa. Penutupnya 'kamu tim level berapa' itu pertanyaan yang bisa dijawab satu kata — saya langsung ketik '3' di komen, nggak perlu mikir. Hesitasinya: semua bergantung kriuk detik pertama beneran enak didengar waktu eksekusi, dan 'jujur:'-nya dikit formula. Tapi versi ini kelihatan orangnya, versi satunya kelihatan effortnya — nggak susah milih."}

### social-2 (startup-linkedin · V1=Arm A, V2=Arm B · PICK: V2 → skill)

V1: {"persona":"startup-linkedin","understood":true,"trusted":true,"would_act":true,"lost_me_at":"Tiga jam itu mengubah cara kami memandang monitoring: sistem yang tercatat normal belum tentu berjalan benar.","cheese_flags":["Sistem tidak gagal — ia bekerja terlalu patuh pada asumsi yang salah.","Yang paling menggelitik:","Dari insiden itu, kami membawa pulang tiga perbaikan:","Tiga jam itu mengubah cara kami memandang monitoring: sistem yang tercatat normal belum tentu berjalan benar."],"in_my_words":"Monitoring kami cuma ngukur error rate, jadi pas auto-assign 'sukses' ngebuang 400 order ke satu kurir, semuanya keliatan normal di dashboard. Fix-nya tiga: ganti alert jadi yang actionable ('pesanan ke satu kurir melewati 50'), drill insiden tiap bulan, dan postmortem no-blame biar orang cepat lapor kalau ada yang aneh.","verdict_note":"Hook-nya juara — 'Kamis lalu' plus angka 400 dan 3 jam, langsung credible, dan struktur list-nya gampang di-scan di phone. Tapi dua epigram itu (em-dash 'bekerja terlalu patuh pada asumsi yang salah' dan closer 'mengubah cara kami memandang monitoring') itu parfum LinkedIn, persis cadence AI-translated yang bikin mata gue rolling — post-nya sendiri udah kuat tanpa itu, kenapa harus dipoles jadi quote-quotable. 'Membawa pulang tiga perbaikan' juga sedikit lesson-arc. Tetap trusted karena detail-nya real dan alert string-nya ('pesanan ke satu kurir melewati 50') langsung gue steal buat tim gue. React, mungkin. Comment, enggak terlalu ada hooked-nya."}

V2: {"persona":"startup-linkedin","understood":true,"trusted":true,"would_act":true,"lost_me_at":null,"cheese_flags":["Yang saya catat: alert yang baik bukan yang datanya paling lengkap, tapi yang memberi tahu satu hal spesifik untuk dikerjakan.","yang perlu diperbaiki mungkin bukan sistemnya, tapi pertanyaannya"],"in_my_words":"Error rate nggak akan pernah nangkep kejadian yang memang bukan error — 400 order numpuk di satu kurir itu 'success' di metrics, makanya nggak ada yang nanya sampai keadaan membesar. Ganti alert-nya jadi yang langsung kasih langkah pertama (nama kurir, zona, jumlah pesanan), latihan insiden dipindah ke hari normal karena jam pertama insiden itu waktu terburuk buat belajar prosedur, dan postmortem-nya nanya 'bagian sistem mana yang memungkinkan ini', bukan nunggu jawaban 'kurang teliti'.","verdict_note":"Jujur, hook-nya lebih lemah — 'baru-baru ini' itu hedging, kasih tanggal kayak versi satunya, dan paragraf terakhir agak kepanjangan dan sedikit ngaji dengan dua kalimat bukan-X-tapi-Y beruntun. Tapi dari semua yang gue baca hari ini, ini yang paling banyak bisa dicuri: isi payload alert-nya (nama kurir, zona, jumlah), alasan kenapa drill dipindah ke hari normal, 'kalau postmortem berakhir di kurang teliti kita berhenti mencari terlalu cepat' — itu pengalaman beneran, bukan teori. Dan pertanyaan penutupnya ('setelah alert muncul, langkah pertamanya apa?') bisa langsung gue pakai ke tim on-call gue hari ini, which is alasan gue bakal comment dan save post-nya. Ini sounds like orang yang beneran ngerjain incident-nya, bukan orang yang nulis post-nya buat keliatan bijak. Hesitasi: versi 1 menang di 2 detik pertama scroll, versi 2 menang setelah gue beneran baca — dan yang gue baca itu yang gue inget besok."}
