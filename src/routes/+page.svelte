<script>
  import { goto } from '$app/navigation';

  const today = new Date().toLocaleDateString('id-ID', {
    weekday: 'long',
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  });

  let headlines = [
    {
        title: "Ma’had Nurul Huda MAN 2 Kota Probolinggo Gelar Kegiatan Briyani (Berbagi Kebaikan di Bulan Suci Ramadhan) Vol. 2",
        subtitle: "MandaProExist – Ma’had Nurul Huda MAN 2 Kota Probolinggo kembali menggelar kegiatan Briyani (Berbagi Kebaikan di Bulan Suci Ramadhan) Vol. 2 pada hari Minggu, 16 Maret 2025, bertempat di Aula MAN 2 Kota Probolinggo. Kegiatan ini diadakan untuk memperingati Nuzulul Quran serta meningkatkan kepedulian sosial di bulan suci Ramadhan.",
        image: "article/briyani.jpeg"
      },
      {
        title: "Tasyakuran Purna Studi MAN 2 Kota Probolinggo, 398 Siswa Resmi Dikukuhkan Sebagai Alumni",
        subtitle: "Probolinggo, 8 Mei 2025 – Sebanyak 398 siswa kelas 12 MAN 2 Kota Probolinggo resmi dikukuhkan sebagai alumni dalam acara Tasyakuran Purna Studi yang berlangsung khidmat dan meriah di Paseban Sena pada Kamis, 8 Mei 2025.",
        image: "article/headline.jpeg"
      },
      {
        title: "MAN 2 Kota Probolinggo Gelar Yudisium Kelas 12",
        subtitle: "Probolinggo, 7 Mei 2025 – Suasana haru dan khidmat menyelimuti Aula Mandapro Exist pada Rabu (7/5), saat MAN 2 Kota Probolinggo menyelenggarakan Yudisium bagi siswa-siswi kelas 12 tahun ajaran 2024/2025.",
        image: "article/yudisium.jpeg"
      },
      {
        title: "Peringatan Hardiknas di MAN 2 Kota Probolinggo",
        subtitle: "robolinggo, 2 Mei 2025 — Dalam rangka memperingati Hari Pendidikan Nasional, MAN 2 Kota Probolinggo menggelar upacara bendera yang berlangsung pada Jumat pagi, 2 Mei 2025, di lapangan upacara madrasah.",
        image: "article/gelar.jpg"
      },
      {
        title: "MandaPro Exist Meriahkan Hari Kartini 2025 dengan Lomba Catwalk dan Cerdas Cermat",
        subtitle: "MandaProExist — Dalam rangka memperingati Hari Kartini, OSIM MAN 2 Kota Probolinggo menggelar serangkaian kegiatan yang penuh semangat dan nuansa budaya. Acara yang berlangsung pada Rabu, 23 April 2025 ini diisi dengan lomba catwalk dan cerdas cermat yang diikuti oleh seluruh perwakilan kelas X dan XI bertempat dihalaman MandaPro Exist.",
        image: "article/catwalk.jpeg"
      },
      {
        title: "Siswa MAN 2 MandaPro Exist Raih Best Presentation di Lomba Silver Paper 2024",
        subtitle: "MandaProExist– Dua siswa berprestasi dari MAN 2 Kota Probolinggo atas nama M. Khauzaky Amkanay (SKS) dan Hilmi Zaki Mumtaz (SKS), berhasil meraih penghargaan Best Presentation dalam ajang lomba Silver Paper 2024 yang diselenggarakan oleh Departemen Teknik Material dan Metalurgi Institut Teknologi Sepuluh Nopember (ITS) Surabaya.",
        image: "article/silver.jpg"
      },
      {
        title: "Dua Siswa MAN 2 Kota Probolinggo Raih Medali di Olimpiade Sains Airlangga 2025",
        subtitle: "MandaProExist – Jaudah Dahlia Saldi (XII IPS 1) meraih medali perak Soshum, dan Muhammad Razaan Zafran (XI IPA 6) meraih medali perunggu Sains Teknologi dalam Olimpiade Sains Airlangga (OSA) 2024 di Universitas Airlangga, Surabaya, 14-15 Desember 2024. Prestasi ini membanggakan mereka dan MAN 2 Kota Probolinggo.",
        image: "article/razan.jpg"
      },
      {
        title: "Tim Procommit MandaPro Exist V.14 Panen Juara di ITS Surabaya Tahun 2024",
        subtitle: "MandaProExist – Tim Procommit MAN 2 Kota Probolinggo kembaliq mengukir prestasi gemilang dalam ajang kompetisi yang diselenggarakan oleh ITS (Institut Teknologi Sepuluh Nopember) Surabaya pada Sabtu, 23 November 2024. ",
        image: "article/procommit.jpg"
      },
      {
        title: "Halal Bihalal Warnai Hari Pertama Pembelajaran di MAN 2 Kota Probolinggo",
        subtitle: "MandaProExist — Mengawali kegiatan pembelajaran setelah libur Hari Raya Idulfitri 1446 H, seluruh warga MAN 2 Kota Probolinggo menggelar kegiatan Halal Bihalal yang penuh kehangatan dan kebersamaan, Rabu (9/4).",
        image: "article/bihalal.jpeg"
      },
      {
        title: "UKHUWAH, ILMU, AKSI (KEMAH DAKWAH LINGKUNGAN MAXIST 2025)d",
        subtitle: "EV market continues to grow as demand spikes globally.",
        image: "article/kemah.jpg"
      },{
      title: "Tasyakuran Purna Studi MAN 2 Kota Probolinggo, 398 Siswa Resmi Dikukuhkan Sebagai Alumni",
    subtitle: "Probolinggo, 8 Mei 2025 – Sebanyak 398 siswa kelas 12 MAN 2 Kota Probolinggo resmi dikukuhkan sebagai alumni...",
    image: "/article/headline.jpeg"}
  ];

  function goToDetail(headline) {
    const slug = slugify(headline.title);
    goto(`/berita/${slug}`, { state: { headline } });
  }

  function slugify(text) {
    return text.toLowerCase().replace(/\s+/g, '-').replace(/[^\w-]+/g, '');
  }
</script>

<style>
  :global(body) {
    background-color: #f9fafb;
  }
</style>

<header class="sticky top-0 z-50 bg-white shadow-sm border-b border-gray-200">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-16">

      <!-- Tanggal -->
      <div class="text-sm text-gray-600 font-medium">
        {today}
      </div>

      <!-- Nama Website -->
      <div class="text-xl font-serif font-bold tracking-wide text-gray-800">
        Yournaler
      </div>

      <!-- Icon Search -->
      <div>
        <button class="text-gray-500 hover:text-black transition">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none"
               viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round"
                  d="M21 21l-4.35-4.35m0 0A7.5 7.5 0 1016.65 16.65z" />
          </svg>
        </button>
      </div>

    </div>
  </div>
</header>

<main class="p-6 max-w-7xl mx-auto space-y-6">
  <h1 class="text-3xl md:text-4xl font-extrabold text-gray-800">Headline Berita</h1>

  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
    {#each headlines as headline}
      <div
        class="group border rounded-2xl overflow-hidden shadow-lg bg-white hover:shadow-indigo-200 transition-all duration-300 transform hover:-translate-y-1 cursor-pointer"
        on:click={() => goToDetail(headline)}
      >
        <div class="relative">
          <img
            src={headline.image}
            alt={headline.title}
            class="w-full h-44 object-cover group-hover:scale-105 transition-transform duration-300"
            on:error={(e) => e.target.src = '/fallback.jpg'}
          />
          <!-- Badge tanggal/kategori -->
          <span class="absolute top-2 left-2 bg-indigo-500 text-white text-xs px-2 py-0.5 rounded-full shadow">
            {headline.date || 'Berita'}
          </span>
        </div>

        <div class="p-4 space-y-2">
          <h2 class="text-lg font-semibold text-gray-900 line-clamp-2">{headline.title}</h2>
          <p class="text-sm text-gray-600 line-clamp-2">{headline.subtitle}</p>
        </div>
      </div>
    {/each}
  </div>
</main>

      