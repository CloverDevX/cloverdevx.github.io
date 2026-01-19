<script>
  let isVisible = false;
  
  const values = [
    {
      title: 'Teknologi Tepat Guna',
      description: 'Kami memilih dan mengimplementasikan teknologi yang sesuai dengan kebutuhan spesifik Anda, bukan hanya yang terbaru atau paling populer.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/>`
    },
    {
      title: 'Solusi Custom & Scalable',
      description: 'Setiap proyek dirancang khusus untuk kebutuhan Anda dengan arsitektur yang dapat berkembang seiring pertumbuhan bisnis.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0 2.21 3.582 4 8 4s8-1.79 8-4M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4m0 5c0 2.21-3.582 4-8 4s-8-1.79-8-4"/>`
    },
    {
      title: 'Pendekatan Terstruktur',
      description: 'Metodologi pengembangan yang sistematis dari analisis kebutuhan, desain, implementasi, hingga testing dan maintenance.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"/>`
    },
    {
      title: 'Fokus Performa & Keberlanjutan',
      description: 'Optimasi kode dan sistem untuk performa maksimal dengan pertimbangan efisiensi energi dan pemeliharaan jangka panjang.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>`
    }
  ];
  
  function handleIntersection(entries) {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        isVisible = true;
      }
    });
  }
  
  function observeSection(node) {
    const observer = new IntersectionObserver(handleIntersection, {
      threshold: 0.2
    });
    observer.observe(node);
    
    return {
      destroy() {
        observer.disconnect();
      }
    };
  }
</script>

<section class="py-20 lg:py-32 bg-white relative overflow-hidden" use:observeSection>
  <!-- Background Decoration -->
  <div class="absolute inset-0 pointer-events-none">
    <div class="absolute top-0 right-0 w-96 h-96 bg-clover-green-100 rounded-full opacity-30 blur-3xl"></div>
    <div class="absolute bottom-0 left-0 w-96 h-96 bg-clover-green-200 rounded-full opacity-30 blur-3xl"></div>
  </div>

  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <!-- Section Header -->
    <div class="text-center mb-16" class:opacity-0={!isVisible} class:translate-y-[30px]={!isVisible} class:opacity-100={isVisible} class:translate-y-0={isVisible} style="transition: all 0.8s ease-out;">
      <div class="inline-block mb-4">
        <span class="text-clover-green-600 font-semibold text-sm uppercase tracking-wide bg-clover-green-50 px-4 py-2 rounded-full">
          Keunggulan Kami
        </span>
      </div>
      <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-gray-900 mb-4">
        Mengapa Memilih Cloverdev?
      </h2>
      <p class="text-lg text-gray-600 max-w-2xl mx-auto">
        Kami tidak hanya menyediakan teknologi, tetapi solusi yang tepat untuk mengakselerasi bisnis Anda
      </p>
    </div>

    <!-- Values Grid -->
    <div class="grid md:grid-cols-2 gap-8 lg:gap-12">
      {#each values as value, index}
        <div 
          class="group relative"
          class:opacity-0={!isVisible}
          class:translate-y-[30px]={!isVisible}
          class:opacity-100={isVisible}
          class:translate-y-0={isVisible}
          style="transition: all 0.6s ease-out {0.15 * (index + 1)}s;"
        >
          <div class="flex gap-6 bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition-all duration-500 border border-gray-100 hover:border-clover-green-200 h-full">
            <!-- Icon -->
            <div class="flex-shrink-0">
              <div class="w-16 h-16 bg-gradient-to-br from-clover-green-500 to-clover-green-700 rounded-xl flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform duration-300">
                <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  {@html value.icon}
                </svg>
              </div>
            </div>

            <!-- Content -->
            <div class="flex-1">
              <h3 class="text-xl font-bold text-gray-900 mb-3 group-hover:text-clover-green-600 transition-colors">
                {value.title}
              </h3>
              <p class="text-gray-600 leading-relaxed">
                {value.description}
              </p>
            </div>
          </div>

          <!-- Decorative Element -->
          <div class="absolute -z-10 inset-0 bg-gradient-to-br from-clover-green-500 to-clover-green-700 rounded-2xl opacity-0 group-hover:opacity-10 transition-opacity duration-300 transform translate-x-2 translate-y-2"></div>
        </div>
      {/each}
    </div>

    <!-- Additional Stats -->
    <div class="mt-20 grid grid-cols-2 md:grid-cols-4 gap-6" class:opacity-0={!isVisible} class:translate-y-[30px]={!isVisible} class:opacity-100={isVisible} class:translate-y-0={isVisible} style="transition: all 0.8s ease-out 0.8s;">
      <div class="text-center p-6 bg-gradient-to-br from-clover-green-50 to-clover-green-100 rounded-xl hover:shadow-lg transition-shadow">
        <div class="text-4xl font-bold text-clover-green-600 mb-2">100%</div>
        <div class="text-sm text-gray-600 font-medium">Custom Solution</div>
      </div>
      <div class="text-center p-6 bg-gradient-to-br from-clover-green-50 to-clover-green-100 rounded-xl hover:shadow-lg transition-shadow">
        <div class="text-4xl font-bold text-clover-green-600 mb-2">Fast</div>
        <div class="text-sm text-gray-600 font-medium">Development</div>
      </div>
      <div class="text-center p-6 bg-gradient-to-br from-clover-green-50 to-clover-green-100 rounded-xl hover:shadow-lg transition-shadow">
        <div class="text-4xl font-bold text-clover-green-600 mb-2">Pro</div>
        <div class="text-sm text-gray-600 font-medium">Team Support</div>
      </div>
      <div class="text-center p-6 bg-gradient-to-br from-clover-green-50 to-clover-green-100 rounded-xl hover:shadow-lg transition-shadow">
        <div class="text-4xl font-bold text-clover-green-600 mb-2">Long</div>
        <div class="text-sm text-gray-600 font-medium">Term Partnership</div>
      </div>
    </div>
  </div>
</section>
