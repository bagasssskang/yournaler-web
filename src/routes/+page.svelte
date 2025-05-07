<script>
    let hotNews = {
      title: "NASA Discovers New Earth-Like Planet",
      description: "The newly discovered planet lies within the habitable zone and could contain liquid water.",
      image: "https://images.unsplash.com/photo-1581090700227-1e8d738fd1b9?auto=format&fit=crop&w=600&q=80"
    };
  
    let headlines = [
      {
        title: "Tech Giants Invest Billions in Quantum Computing",
        subtitle: "Major players like Google and IBM double down on quantum technologies.",
        image: "https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "Global Markets Surge After Positive Jobs Report",
        subtitle: "Stock markets around the world rallied after strong economic data was released.",
        image: "https://images.unsplash.com/photo-1542228262-3d663b3063d7?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "Breakthrough in Renewable Energy Storage",
        subtitle: "Scientists develop a new battery technology to store solar power more efficiently.",
        image: "https://images.unsplash.com/photo-1509395176047-4a66953fd231?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "AI Outperforms Doctors in Diagnosing Skin Cancer",
        subtitle: "New study shows AI systems surpass human dermatologists in accuracy.",
        image: "https://images.unsplash.com/photo-1588776814546-ec7aa9f108f4?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "World Leaders Meet to Discuss Climate Strategy",
        subtitle: "The summit in Geneva aims to outline binding emission targets.",
        image: "https://images.unsplash.com/photo-1530031686560-dc6c8763b3a1?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "Innovative Startups Lead Tech Expo 2025",
        subtitle: "Small companies showcased bold ideas at the annual tech event.",
        image: "https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "New Legislation Aims to Protect User Data",
        subtitle: "The digital privacy act could reshape how tech firms collect data.",
        image: "https://images.unsplash.com/photo-1556742031-c6961e8560b0?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "Mars Mission Test Flight Deemed a Success",
        subtitle: "Space agency reports all objectives met during trial run.",
        image: "https://images.unsplash.com/photo-1606481209984-720db5ef5ab1?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "Scientists Find Possible Cure for Rare Disease",
        subtitle: "Early trials show encouraging results using gene therapy.",
        image: "https://images.unsplash.com/photo-1588776814661-5f622f0cae23?auto=format&fit=crop&w=600&q=80"
      },
      {
        title: "Electric Vehicle Sales Hit New Record",
        subtitle: "EV market continues to grow as demand spikes globally.",
        image: "https://images.unsplash.com/photo-1583267740902-b0fdf3f9edc5?auto=format&fit=crop&w=600&q=80"
      },
      // Tambahkan lebih banyak jika diperlukan
    ];
  
    let currentPage = 1;
    let itemsPerPage = 6;
    let totalPages = Math.ceil(headlines.length / itemsPerPage);
  
    $: paginatedHeadlines = headlines.slice((currentPage - 1) * itemsPerPage, currentPage * itemsPerPage);
  </script>
  
  <main class="bg-white text-black min-h-screen">
    <!-- Navbar -->
    <nav class="flex items-center justify-between px-6 py-4 shadow border-b">
      <div class="text-3xl font-bold">MPN</div>
      <ul class="flex space-x-4 text-sm font-medium">
        <li><a href="#" class="hover:text-red-600">News</a></li>
        <li><a href="#" class="hover:text-red-600">Finance</a></li>
        <li><a href="#" class="hover:text-red-600">Tech</a></li>
        <li><a href="#" class="hover:text-red-600">Leadership</a></li>
      </ul>
    </nav>
  
    <!-- Top Layout: Hot News + Headline -->
    <section class="grid grid-cols-1 md:grid-cols-3 gap-6 px-6 py-8">
      <div class="md:col-span-1 bg-gradient-to-r from-red-400 to-pink-300 text-white p-4 rounded-xl shadow">
        <img src={hotNews.image} alt={hotNews.title} class="w-full h-40 object-cover rounded mb-4">
        <h2 class="text-lg font-bold mb-2">{hotNews.title}</h2>
        <p class="text-sm">{hotNews.description}</p>
      </div>
  
      <div class="md:col-span-2 flex flex-col justify-center bg-blue-50 p-6 rounded-xl shadow">
        <h1 class="text-2xl font-bold mb-4 text-blue-800">{headlines[0].title}</h1>
        <p class="text-gray-700 text-md">{headlines[0].subtitle}</p>
      </div>
    </section>
  
    <!-- Segmented News -->
    <section class="grid grid-cols-1 md:grid-cols-3 gap-6 px-6 pb-10">
      {#each paginatedHeadlines as headline}
        <div class="rounded-xl overflow-hidden shadow-lg border border-gray-200 bg-gradient-to-br from-white via-blue-100 to-purple-100">
          <img src={headline.image} alt={headline.title} class="w-full h-40 object-cover">
          <div class="p-4">
            <h3 class="text-lg font-semibold mb-2 text-purple-800">{headline.title}</h3>
            <p class="text-sm text-gray-700">{headline.subtitle}</p>
          </div>
        </div>
      {/each}
    </section>
  
    <!-- Pagination -->
    <div class="flex justify-center items-center space-x-2 pb-10">
      {#each Array(totalPages).fill(0).map((_, i) => i + 1) as page}
        <button on:click={() => currentPage = page} class="px-3 py-1 rounded-full text-sm font-semibold border border-gray-300 hover:bg-gray-200 transition-colors {page === currentPage ? 'bg-blue-600 text-white' : 'bg-white'}">
          {page}
        </button>
      {/each}
    </div>
  
    <!-- Footer -->
    <footer class="bg-gray-100 text-gray-600 text-sm px-6 py-4 text-center">
      &copy; 2025 Fortune Clone. All rights reserved.
    </footer>
  </main>
  
  <style>
    main {
      font-family: 'Inter', sans-serif;
    }
  </style>
  