<script>
  import { page } from '$app/stores';
  import { onMount } from 'svelte';

  let slug;
  let headline;

  let headlines = [{
    title: "Ma’had Nurul Huda MAN 2 Kota Probolinggo Gelar Kegiatan Briyani (Berbagi Kebaikan di Bulan Suci Ramadhan) Vol. 2",
    subtitle: "MandaProExist – Ma’had Nurul Huda MAN 2 Kota Probolinggo kembali menggelar kegiatan Briyani (Berbagi Kebaikan di Bulan Suci Ramadhan) Vol. 2 pada hari Minggu, 16 Maret 2025, bertempat di Aula MAN 2 Kota Probolinggo. Kegiatan ini diadakan untuk memperingati Nuzulul Quran serta meningkatkan kepedulian sosial di bulan suci Ramadhan.",
    image: "/article/briyani.jpeg",
    content: `
      <div class="border-b-2 border-indigo-500 w-20 mb-4"></div>
      <p>MandaProExist – Ma’had Nurul Huda MAN 2 Kota Probolinggo kembali menggelar kegiatan Briyani (Berbagi Kebaikan di Bulan Suci Ramadhan) Vol. 2 pada hari Minggu, 16 Maret 2025, bertempat di Aula MAN 2 Kota Probolinggo. Kegiatan ini diadakan untuk memperingati Nuzulul Quran serta meningkatkan kepedulian sosial di bulan suci Ramadhan.</p>
      <br>
      <p>Acara dimulai dengan pemberian santunan kepada 40 anak yatim piatu, sebuah bentuk perhatian dan kepedulian terhadap mereka yang membutuhkan. Santunan tersebut diberikan dengan penuh kehangatan oleh panitia kepada anak-anak yang hadir, diiringi doa agar mereka senantiasa diberikan kebahagiaan dan keberkahan.</p>
      <br>
      <p>Setelah santunan, acara dilanjutkan dengan Khotmil Qur’an yang dipimpin oleh Kepala MAN 2 Kota Probolinggo, Bapak M. Alfan Makmur, M.M. Kegiatan ini bertujuan untuk meningkatkan kecintaan terhadap Al-Qur’an sekaligus sebagai salah satu bentuk perayaan Nuzulul Qur’an, di mana malam turunnya wahyu pertama kepada Nabi Muhammad SAW diperingati oleh umat Islam.<p>
      <br>
      <p>Tak kalah pentingnya, kegiatan dilanjutkan dengan Shalat Magrib berjamaah yang diikuti oleh kepala madrasah, dewan guru, staf, ustad/ah, serta seluruh santri Ma’had Nurul Huda. Semangat kebersamaan dan kekhusyukan terasa kental dalam pelaksanaan shalat tersebut.</p>
      <br>
      <p>Sebagai penutup, acara diakhiri dengan buka bersama yang melibatkan seluruh peserta, termasuk kepala madrasah, dewan guru, ustad/ah, staf, dan santri. Momen buka bersama ini menjadi kesempatan untuk mempererat tali silaturahmi dan meningkatkan ukhuwah Islamiyah di kalangan warga Ma’had Nurul Huda MAN 2 Kota Probolinggo.</p>
      <br>
      <p>Melalui kegiatan Briyani Vol. 2 ini, Ma’had Nurul Huda MAN 2 Kota Probolinggo berharap dapat memberi manfaat dan kebaikan bagi sesama serta memperkuat nilai-nilai kebersamaan dalam bulan suci Ramadhan.</p>
      <br> `
  },
    {
    title: "Tasyakuran Purna Studi MAN 2 Kota Probolinggo, 398 Siswa Resmi Dikukuhkan Sebagai Alumni",
    subtitle: "Probolinggo, 8 Mei 2025 – Sebanyak 398 siswa kelas 12 MAN 2 Kota Probolinggo resmi dikukuhkan sebagai alumni...",
    image: "/article/headline.jpeg",
    content: `
      <p><strong>Probolinggo, 8 Mei 2025</strong> – Sebanyak 398 siswa kelas 12 MAN 2 Kota Probolinggo resmi dikukuhkan sebagai alumni dalam acara Tasyakuran Purna Studi yang berlangsung khidmat dan meriah di Paseban Sena pada Kamis, 8 Mei 2025.</p>

      <p>Rangkaian acara dimulai sejak pagi hari dengan kirab siswa-siswi kelas 12 yang disambut hangat oleh para guru, orang tua, dan tamu undangan. Suasana semakin semarak dengan penampilan silat serta kolaborasi seni hadroh dan gamelan dari santri Ma’had Nurul Huda Mandapro Exist.</p>

      <p>Acara dilanjutkan dengan sambutan dari Ketua Panitia yang juga menjabat sebagai Ketua Komite Madrasah, Bapak Sudarmoto, S.T. Kemudian, Kepala Madrasah MAN 2 Kota Probolinggo, Bapak M. Alfan Makmur, M.M., memberikan sambutannya dengan mengangkat tema besar tasyakuran tahun ini: <em>“Tumbuh Erat dalam Harmoni, Terbang Bebas Raih Mimpi.”</em></p>

      <p>Dari total 398 siswa yang lulus, 39 berasal dari program Tahfidz, 29 dari kelas percepatan, dan 330 dari kelas reguler. Momentum kebanggaan ini menjadi penanda keberhasilan madrasah dalam mencetak lulusan berprestasi di berbagai bidang.</p>

      <p>Acara tasyakuran semakin semarak dengan penampilan dari tim nasyid dan tim paduan suara MAN 2 Kota Probolinggo. Puncak kegiatan ditandai dengan prosesi pengukuhan alumni yang berlangsung penuh haru dan kebanggaan.</p>
    `
    } ,
    {
      title: "MAN 2 Kota Probolinggo Gelar Yudisium Kelas 12",
      subtitle: "Probolinggo, 7 Mei 2025 – Suasana haru dan khidmat menyelimuti Aula Mandapro Exist pada Rabu (7/5), saat MAN 2 Kota Probolinggo menyelenggarakan Yudisium bagi siswa-siswi kelas 12 tahun ajaran 2024/2025.",
      image: "/article/yudisium.jpeg",
      content: `
      <p><strong>Probolinggo, 7 Mei 2025</strong> – Suasana haru dan khidmat menyelimuti Aula Mandapro Exist pada Rabu (7/5), saat MAN 2 Kota Probolinggo menyelenggarakan Yudisium bagi siswa-siswi kelas 12 tahun ajaran 2024/2025. Acara ini dihadiri oleh seluruh peserta yudisium, para Pembimbing Akademik (PA), jajaran Wakil Kepala Madrasah, serta Kepala MAN 2 Kota Probolinggo, Bapak M. Alfan Makmur, M.M.</p>
      <p>Rangkaian acara dimulai dengan pembukaan, dilanjutkan dengan menyanyikan lagu kebangsaan Indonesia Raya dan Mars Madrasah. Dalam suasana penuh kebanggaan, Kepala Madrasah memberikan sambutan yang menekankan pentingnya menjaga nilai-nilai akhlak dan integritas saat melangkah ke jenjang selanjutnya.</p>
      <p>Momen yang paling dinanti adalah pembacaan Surat Keputusan (SK) Penetapan Kelulusan oleh Kepala Madrasah. Dengan suara lantang dan penuh makna, dinyatakan bahwa seluruh peserta yudisium dinyatakan lulus. Tak lama kemudian, dilakukan pengukuhan alumni secara simbolis, menandai transisi resmi para siswa dari status pelajar menjadi alumni MAN 2 Kota Probolinggo.</p>
      <p>Acara semakin emosional ketika salah satu perwakilan alumni menyampaikan pesan dan kesan. Ia menyampaikan terima kasih kepada guru-guru atas bimbingan dan dedikasi yang telah diberikan selama tiga tahun masa pendidikan.</p>
      <p>Setelah seluruh rangkaian acara yudisium selesai, para siswa diarahkan ke kelas masing-masing untuk menerima rapor kelulusan sebagai penutup kegiatan hari itu.</p>
      <p>Kegiatan yudisium ini menjadi titik akhir dari perjuangan panjang para siswa di bangku madrasah, sekaligus awal dari perjalanan baru untuk menapaki masa depan yang lebih gemilang.</p>    `
    },
    {
      title: "Peringatan Hardiknas di MAN 2 Kota Probolinggo",
      subtitle: "robolinggo, 2 Mei 2025 — Dalam rangka memperingati Hari Pendidikan Nasional, MAN 2 Kota Probolinggo menggelar upacara bendera yang berlangsung pada Jumat pagi, 2 Mei 2025, di lapangan upacara madrasah.",
      image: "/article/gelar.jpg",
    content: `
      <p><strong>Probolinggo, 2 Mei 2025</strong> — Dalam rangka memperingati Hari Pendidikan Nasional (Hardiknas) yang jatuh setiap tanggal 2 Mei, MAN 2 Kota Probolinggo menyelenggarakan upacara bendera dengan khidmat pada Jumat pagi, 2 Mei 2025. Kegiatan ini dilaksanakan di lapangan utama madrasah dan diikuti oleh seluruh civitas akademika MAN 2 Kota Probolinggo, mulai dari para siswa, dewan guru, staf Tata Usaha, hingga unsur pimpinan madrasah. Upacara dimulai tepat pukul 07.30 WIB dan berlangsung selama kurang lebih tiga puluh menit hingga pukul 08.00 WIB.</p>
      <br>
      <p>Suasana pagi yang cerah turut mendukung jalannya upacara yang berlangsung tertib dan penuh semangat. Seluruh peserta upacara menunjukkan sikap disiplin dan antusiasme dalam mengikuti rangkaian kegiatan, mencerminkan semangat nasionalisme dan kepedulian terhadap pentingnya pendidikan. Para petugas upacara yang berasal dari siswa-siswi MAN 2 Kota Probolinggo juga menjalankan tugasnya dengan penuh tanggung jawab dan percaya diri.</p>
      <br>
      <p>Bertindak sebagai pembina upacara adalah Kepala MAN 2 Kota Probolinggo, Drs. Alfan Makmur, MM. Dalam amanatnya, beliau menyampaikan pesan yang menggugah semangat seluruh peserta upacara. Beliau menekankan pentingnya pendidikan sebagai pondasi utama dalam membentuk generasi muda yang unggul, cerdas, dan berakhlak mulia. "Hari Pendidikan Nasional bukan hanya momen untuk mengenang jasa para pahlawan pendidikan seperti Ki Hadjar Dewantara, tetapi juga menjadi momentum untuk merefleksikan sejauh mana kita telah berkontribusi dalam memajukan pendidikan," ujar beliau dalam sambutannya.</p>
      <br>
      <p>Lebih lanjut, Drs. Alfan Makmur mengajak seluruh siswa untuk terus menumbuhkan semangat belajar dan pantang menyerah dalam meraih cita-cita. Ia juga mengingatkan bahwa pendidikan bukan hanya soal nilai akademik, tetapi juga mencakup pembentukan karakter, etika, dan tanggung jawab sosial. "Madrasah ini bukan sekadar tempat menimba ilmu, tetapi juga tempat kalian dibentuk menjadi insan yang siap menghadapi tantangan zaman dengan iman dan ilmu," tambahnya.</p>
      <br>
      <p>Kegiatan upacara peringatan Hardiknas di MAN 2 Kota Probolinggo ini menjadi wujud nyata komitmen madrasah dalam menghargai dan menumbuhkan kesadaran akan pentingnya pendidikan. Dengan pelaksanaan yang tertib dan penuh makna, diharapkan momentum ini dapat menjadi inspirasi bagi seluruh warga madrasah untuk terus berinovasi dan berprestasi dalam dunia pendidikan.</p>    `
    },
    {
      title: "MandaPro Exist Meriahkan Hari Kartini 2025 dengan Lomba Catwalk dan Cerdas Cermat",
      subtitle: "MandaProExist — Dalam rangka memperingati Hari Kartini, OSIM MAN 2 Kota Probolinggo menggelar serangkaian kegiatan yang penuh semangat dan nuansa budaya. Acara yang berlangsung pada Rabu, 23 April 2025 ini diisi dengan lomba catwalk dan cerdas cermat yang diikuti oleh seluruh perwakilan kelas X dan XI bertempat dihalaman MandaPro Exist.",
      image: "/article/catwalk.jpeg",
    content: `
      <p><strong>MandaProExist</strong> — Dalam rangka memperingati Hari Kartini, OSIM MAN 2 Kota Probolinggo menggelar serangkaian kegiatan yang penuh semangat dan nuansa budaya. Acara yang berlangsung pada Rabu, 23 April 2025 ini diisi dengan lomba catwalk dan cerdas cermat yang diikuti oleh seluruh perwakilan kelas X dan XI bertempat dihalaman MandaPro Exist.<p>
      <br>
      <p>Suasana semakin meriah ketika para peserta lomba cerdas cermat berhasil menjawab berbagai pertanyaan yang dilontarkan oleh dewan juri. Sorak sorai penonton turut menambah semangat para peserta, menjadikan acara ini penuh antusiasme dan kekompakan antar kelas</p>
      <br>
      <p>Tak hanya itu, seluruh warga MAN 2 Kota Probolinggo, yang dikenal dengan sebutan Mandapro Exist, turut serta memeriahkan peringatan Hari Kartini dengan mengenakan pakaian adat Jawa. Mulai dari siswa, guru, hingga staf tata usaha tampil anggun dan berwibawa dalam balutan busana tradisional, menciptakan atmosfer yang kental dengan nilai-nilai budaya Nusantara.</p>
      <br>
      <p>Kegiatan ini tidak hanya menjadi ajang kompetisi, tetapi juga menjadi momen untuk menumbuhkan semangat kebangsaan, cinta budaya, serta mengenang jasa-jasa R.A. Kartini sebagai pelopor emansipasi wanita di Indonesia.</p>
      <br>
      <p>Dengan suksesnya acara ini, OSIM MAN 2 Kota Probolinggo berharap dapat terus menginspirasi generasi muda untuk menghargai sejarah dan melestarikan budaya bangsa.</p>
      <p>Tambahkan HTML apapun di sini seperti , <em>teks miring</em>, dan lain-lain.</p>
    `
    },
    {
      title: "Siswa MAN 2 MandaPro Exist Raih Best Presentation di Lomba Silver Paper 2024",
      subtitle: "MandaProExist– Dua siswa berprestasi dari MAN 2 Kota Probolinggo atas nama M. Khauzaky Amkanay (SKS) dan Hilmi Zaki Mumtaz (SKS), berhasil meraih penghargaan Best Presentation dalam ajang lomba Silver Paper 2024 yang diselenggarakan oleh Departemen Teknik Material dan Metalurgi Institut Teknologi Sepuluh Nopember (ITS) Surabaya.",
      image: "/article/silver.jpg",
    content: `
      <p><strong>MandaProExist</strong>– Dua siswa berprestasi dari MAN 2 Kota Probolinggo atas nama M. Khauzaky Amkanay (SKS) dan Hilmi Zaki Mumtaz (SKS), berhasil meraih penghargaan Best Presentation dalam ajang lomba Silver Paper 2024 yang diselenggarakan oleh Departemen Teknik Material dan Metalurgi Institut Teknologi Sepuluh Nopember (ITS) Surabaya. Lomba yang digelar pada tanggal 20 Desember 2024 ini diikuti oleh berbagai peserta dari seluruh Indonesia, dan menjadi ajang bergengsi di kalangan pelajar dan mahasiswa.</p>
      <br>
      <p>M. Khauzaky dan Hilmi Zaki berhasil menyajikan presentasi yang menarik dan penuh inovasi, memukau dewan juri dengan kemampuan analisis serta penyampaian materi yang jelas dan terstruktur. Topik yang diangkat oleh mereka dalam kompetisi ini adalah tentang pengembangan material baru dengan aplikasi teknologi terbaru, yang relevan dengan perkembangan ilmu pengetahuan dan teknologi saat ini.</p>
      <br>
      <p>Lomba Silver Paper 2024 ini tidak hanya menguji pengetahuan peserta dalam bidang teknik material dan metalurgi, tetapi juga kemampuan komunikasi ilmiah yang sangat penting untuk mengedukasi dan menyebarkan informasi teknologi kepada masyarakat luas. Keberhasilan M. Khauzaky dan Hilmi Zaki menjadi bukti nyata bahwa generasi muda Indonesia, khususnya dari MAN 2 Kota Probolinggo, memiliki potensi besar dalam bidang sains dan teknologi.</p>
      <br>
      <p>Dengan prestasi ini, keduanya berharap dapat terus mengembangkan minat dan bakat mereka di dunia teknik dan material, serta memberi kontribusi positif bagi kemajuan ilmu pengetahuan di Indonesia.</p>
    `
    },
    {
      title: "Dua Siswa MAN 2 Kota Probolinggo Raih Medali di Olimpiade Sains Airlangga 2025",
      subtitle: "MandaProExist – Jaudah Dahlia Saldi (XII IPS 1) meraih medali perak Soshum, dan Muhammad Razaan Zafran (XI IPA 6) meraih medali perunggu Sains Teknologi dalam Olimpiade Sains Airlangga (OSA) 2024 di Universitas Airlangga, Surabaya, 14-15 Desember 2024. Prestasi ini membanggakan mereka dan MAN 2 Kota Probolinggo.",
      image: "/article/razan.jpg",
    content: `
      <p><strong>MandaProExist</strong> – Dua siswa MAN 2 Kota Probolinggo atas nama Jaudah Dahlia Saldi (XII IPS 1) dan Muhammad Razaan Zafran (XI IPA 6), berhasil meraih prestasi gemilang dalam ajang Olimpiade Sains Airlangga (OSA) 2024 yang diselenggarakan oleh Universitas Airlangga. Kompetisi yang berlangsung pada 14-15 Desember 2024 di Kampus MERR C Surabaya ini mengukir prestasi mereka dalam bidang studi masing-masing.</p>
      <br>
      <p>Jaudah Dahlia Saldi berhasil meraih medali perak (silver) di bidang Soshum, sementara Muhammad Razaan Zafran meraih medali perunggu (bronze) di bidang Sains Teknologi. Keberhasilan ini tidak hanya membanggakan bagi mereka, tetapi juga bagi madrasah.</p>
      <br>
      <p>Kepala MAN 2 Kota Probolinggo, M. Alfan Makmur, M.M., mengungkapkan kebanggaannya atas prestasi siswa-siswinya. “Ini adalah kebanggaan bagi kami dan merupakan bukti bahwa MAN 2 Probolinggo mampu bersaing di tingkat nasional. Kami berharap prestasi ini dapat terus ditingkatkan di masa mendatang,” ujar Pak Alfan.<p>
      <br>    `
    },
    {
      title: "Tim Procommit MandaPro Exist V.14 Panen Juara di ITS Surabaya Tahun 2024",
      subtitle: "MandaProExist – Tim Procommit MAN 2 Kota Probolinggo kembaliq mengukir prestasi gemilang dalam ajang kompetisi yang diselenggarakan oleh ITS (Institut Teknologi Sepuluh Nopember) Surabaya pada Sabtu, 23 November 2024. ",
      image: "/article/procommit.jpg",
      content: `
      <p>MandaProExist – Tim Procommit MAN 2 Kota Probolinggo kembali mengukir prestasi gemilang dalam ajang kompetisi yang diselenggarakan oleh ITS (Institut Teknologi Sepuluh Nopember) Surabaya pada Sabtu, 23 November 2024. Dalam kompetisi yang diikuti oleh peserta dari berbagai sekolah di Indonesia, Tim Procommit Maxist berhasil meraih sejumlah penghargaan di berbagai kategori, diantaranya:.</p>
      <p>Alhamdulillah Tim Procommit V. 14 Maxist panen juara di ITS. diantaranya :</p>
      <p>1. Juara 1 kategori desain poster ananda Nassitha Hayu Afandi  – XII A5</p>
      <p>2. Juara 3 kategori Excel Programming ananda M. Khauzaky Amkanaky – XI A7</p>
      <br>
      <p>3. Juara terbaik 4 kategori desain poster ananda Pandu Adi Mondtara – XII A5</p>
      <p>4. Juara terbaik 4 kategori LowCode programming ananda Wahyu Izharullah K – XI A1 dan Ahmad Rafi Fahrur B – XI A1</p>
      <br>
      <p>5. Juara terbaik 4 Apresiasi Karya Akhir ananda Sachio Jumana – XII A2</p>
      <p>6. Juara terbaik 5 Animasi ananda Rizka Salsabila – XII B3 dan Nafisah Sasikirana Putri – XII B3</p>
      <p>Keberhasilan Tim Procommit Maxist ini tidak hanya membanggakan madrasah, tetapi juga menjadi bukti nyata bahwa siswa-siswa di Probolinggo mampu bersaing di tingkat nasional. Prestasi ini semakin mengukuhkan nama MAN 2 Kota Probolinggo sebagai madrasah yang melahirkan talenta-talenta muda yang berpotensi di berbagai bidang teknologi dan seni.</p>
      <p>Selamat kepada para pemenang dan semoga prestasi ini menjadi pemacu semangat bagi seluruh siswa untuk terus berkarya dan berinovasi di masa depan.</p>    `
    },
    {
      title: "Halal Bihalal Warnai Hari Pertama Pembelajaran di MAN 2 Kota Probolinggo",
      subtitle: "MandaProExist — Mengawali kegiatan pembelajaran setelah libur Hari Raya Idulfitri 1446 H, seluruh warga MAN 2 Kota Probolinggo menggelar kegiatan Halal Bihalal yang penuh kehangatan dan kebersamaan, Rabu (9/4).",
      image: "/article/bihalal.jpeg",
      content: `
      <p>MandaProExist — Mengawali kegiatan pembelajaran setelah libur Hari Raya Idulfitri 1446 H, seluruh warga MAN 2 Kota Probolinggo menggelar kegiatan Halal Bihalal yang penuh kehangatan dan kebersamaan, Rabu (9/4).</p>
      <br>
      <p>Kegiatan dimulai dengan apel pagi di halaman madrasah yang diikuti oleh seluruh siswa, dewan guru, serta staf tata usaha. Dalam apel tersebut, kepala madrasah menyampaikan pesan tentang pentingnya menjaga silaturahmi dan saling memaafkan setelah bulan Ramadan, sebagai wujud nyata dari semangat Idulfitri.</p>
      <br>
      <p>Setelah apel, seluruh warga Mandapro Exist mengikuti kegiatan Halal Bihalal dengan saling bersalaman antara siswa, guru, dan staf. Suasana haru dan hangat menyelimuti momen tersebut, mempererat tali silaturahmi antar seluruh elemen madrasah.</p>
      <br>
      <p>Sebagai bagian dari semangat kebersamaan, kegiatan dilanjutkan dengan bersih-bersih kelas oleh masing-masing siswa di bawah bimbingan PA (pendamping akademik). Momen ini tidak hanya menjadi simbol kebersihan fisik, tetapi juga kebersihan hati dalam menyambut semangat baru di awal pembelajaran.</p>
      <br>
      <p>Dengan digelarnya kegiatan ini, MAN 2 Kota Probolinggo berharap dapat terus membina karakter siswa yang santun, peduli, dan menjunjung tinggi nilai-nilai kebersamaan dalam kehidupan sehari-hari.</p>
    `
    },
    {
      title: "UKHUWAH, ILMU, AKSI (KEMAH DAKWAH LINGKUNGAN MAXIST 2025)d",
      subtitle: "EV market continues to grow as demand spikes globally.",
      image: "/article/kemah.jpg",
      content: `
      <p>MandaProExist-Kemah Dakwah Lingkungan 2025 kembali digelar pada 10 hari terakhir Romadhon oleh Kader Lingkungan Adiwiyata MANDAPRO bekerjasama dengan Remaja Masjid (Remas) dan Pecinta Alam (Mandapala). Dengan mengusung tema Ukhuwah, Ilmu dan Aksi, Kemah Dakwah diselenggarakan di Masjid Al Ikhlas, masjid Al Madinah, 3 mushola yakni Roudatul Ma’sum, An Nur dan Al Amin. Sejumlah 95 siswa dan 7 guru pendamping mensukseskan kegiatan kemah dakwah.</p>
      <br>
      <p>Dalam sambutan pemberangkatan Kemah Dakwah, KAMAD MAN 2 berpesan siswa dapat mengimplementasikan pengetahuan Al Qur’an Hadits, Fiqih, Aqidah Akhlak ke Masyarakat dan santri-santri Taman Pendidikan Al Qur’an (TPQ), berbaur dengan masyarakat dalam ibadah maupun kehidupan sehari-hari. Sejumlah 10-15 siswa menempati masing-masig masjid dan mushola yang ditentukan.</p>
      <br>
      <p>Pembagian zakat fitrah mengawali kolaborasi peserta Kemah dengan Amil setempat. Sejumlah 150 paket disalurkan ke warga sekitar masjid Al Madinah di jalan Supriyadi kelurahan Kanigaran (21 paket), Masjid Al Ikhlas kelurahan Pilang (55 paket) dan 74 paket di 3 mushola An Nur, Roudhatul Ma’sum (kelurahan Pilang) dan mushola Al Amin di Perumahan Bromo kelurahan Ketapang. Selain kepada dhuafa, zakat juga tersampaikan kepada fi sabilillah, guru TPQ, muadzin, marbot. Siswa tidak sekedar tahu mengumpulkan zakat fitrah ke panitia zakat namun menyerahkan sendiri dengan kedua tangannya (hands on activity) ke warga yang berhak menerima zakat.</p>
      <br>
      <p>Santri-santri TPQ sangat antusias berinteraksi dengan siswa MAN 2 dengan belajar kisah-kisah Islami yang inspiratif, games edukasi Islami (nama Nabi), Hafalan surat-surat pendek, doa-doa harian. Pertemuan singkat nampaknya menjadi Kesan mendalam bagi peserta Kemah maupun para santri. Dengan polosnya santri-santri menyampaikan: “besok ngaji lagi bersama kakak?” sambil bergelayutan atau duduk di pangkuan kakak MAN 2.</p>
      <br>
      <p>Siswa putra diserahi dipercaya untuk menjadi Muadzin/ Bilal dan Imam sholat fardhu dan sholat taraweh bergantian dengan guru pendamping (Ustadz Hafidz, Ustadz Burhan). Tidak ada keraguan dalam bacaan maupun gestur meski berhadapan dengan Masyarakat umum. Tadarus ada yang diawali selesai sholat Asar (mushola Al Amin dan masjid Al Ikhlas), selebihnya selepas tarawih. Rata-rata 5 juz disuarakan bergantian siswa-siswi Bersama jamaah masjid/mushola. Bahkan selepas saur dan sholat subuh masih dilanjutkan tadarus, di mushola Al Amin menyesaikan 13 juz sampai khatam.</p>
      <br>
      <p>Tambahkan HTML apapun di sini seperti <strong>teks tebal</strong>, <em>teks miring</em>, dan lain-lain.</p>
    `
    },
    {
      title: "Siswa MAN 2 Kota Probolinggo Raih Juara 3 Kelas C Dewasa",
      subtitle: "EV market continues to grow as demand spikes globally.",
      image: "/article/bagas.jpeg",
      content: `<p>MandaProExist — Prestasi membanggakan kembali ditorehkan oleh siswa MAN 2 Kota Probolinggo, Muhammad Bagas Prastya, kelas XII-B2. Bagas berhasil meraih Juara 3 dalam kategori Dewasa Prestasi Putra Kelas C pada Open Tournament Piala Panglima TNI tahun 2025.</p><br>

      <p>Turnamen bergengsi yang diikuti oleh berbagai atlet dari seluruh Indonesia ini menjadi ajang pembuktian kemampuan Bagas di bidangnya. Dengan kerja keras dan dedikasi tinggi, Bagas mampu bersaing dan menampilkan performa terbaiknya hingga akhirnya meraih posisi ketiga.</p><br>

      <p>Kepala MAN 2 Kota Probolinggo menyampaikan rasa bangga atas pencapaian Bagas, sekaligus berharap prestasi ini bisa memotivasi siswa lainnya untuk terus berprestasi, baik di bidang akademik maupun non-akademik.</p><br>

      <p>Prestasi ini tidak hanya menjadi kebanggaan bagi Bagas dan keluarga, tetapi juga membawa harum nama MAN 2 Kota Probolinggo di tingkat nasional.</p>`
    },
  ];
  $: slug = $page.url.pathname.split('/').pop();

  $: headline = headlines.find(h => slugify(h.title) === slug);

  // Helper: safe headline rendering
  $: safeHeadline = headline || { title: '', subtitle: '', image: '', content: '' };

  function slugify(text) {
    return text.toLowerCase().replace(/\s+/g, '-').replace(/[^\w-]+/g, '');
  }
</script>

<style>
  :global(body) {
    background: linear-gradient(to bottom right, #f9fafb, #e5e7eb);
  }
</style>

<main class="relative z-10 max-w-4xl mx-auto p-6 mt-12 bg-white rounded-xl shadow-2xl">

  <!-- Ornamen SVG -->
  <div class="absolute -top-16 -left-16 opacity-10 z-0">
    <svg width="300" height="300" fill="none" xmlns="http://www.w3.org/2000/svg">
      <circle cx="150" cy="150" r="150" fill="#a78bfa" />
    </svg>
  </div>

  <!-- Gambar -->
  <div class="rounded-xl overflow-hidden shadow-md mb-6">
    <img src={safeHeadline.image} alt={safeHeadline.title} class="w-full h-72 object-cover" on:error={(e) => { if(e.target && e.target instanceof HTMLImageElement) e.target.src = '/fallback.jpg'; }} />
  </div>

  <!-- Tanggal -->
  <p class="text-sm text-indigo-600 uppercase tracking-wide font-semibold mb-2">
    {'date' in safeHeadline && safeHeadline.date ? safeHeadline.date : 'Berita'}
  </p>

  <!-- Judul -->
  <h1 class="text-4xl font-extrabold text-gray-900 mb-4 leading-tight">
    {safeHeadline.title}
  </h1>

  <!-- Divider -->
  <div class="w-20 h-1 bg-indigo-500 rounded-full mb-6"></div>

  <!-- Konten -->
  <div class="text-lg text-gray-700 space-y-5 leading-relaxed">
    {@html safeHeadline.content}
  </div>
</main>

<footer class="text-center mt-16 text-sm text-gray-500 pb-6">
  &copy; 2025 MAN 2 Kota Probolinggo. Semua Hak Dilindungi.
</footer>