<script>
  let isVisible = false;
  
  const services = [
    {
      title: 'Robotika',
      description: 'Solusi robotika custom untuk otomasi industri, pendidikan, dan riset. Dari desain mekanik hingga implementasi sistem kontrol cerdas.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z"/>`,
      color: 'from-clover-green-400 to-clover-green-600'
    },
    {
      title: 'Embedded System',
      description: 'Pengembangan sistem embedded untuk berbagai aplikasi. Mulai dari mikrokontroler hingga single-board computer dengan optimasi performa tinggi.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z"/>`,
      color: 'from-clover-green-500 to-clover-green-700'
    },
    {
      title: 'Internet of Things (IoT)',
      description: 'Implementasi solusi IoT terintegrasi untuk monitoring, kontrol, dan analisis data real-time. Mendukung berbagai protokol komunikasi modern.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"/>`,
      color: 'from-clover-green-600 to-clover-green-800'
    },
    {
      title: 'Web Application Development',
      description: 'Pengembangan aplikasi web modern, responsif, dan scalable. Menggunakan teknologi terkini untuk performa optimal dan user experience terbaik.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/>`,
      color: 'from-clover-green-500 to-clover-green-700'
    },
    {
      title: 'Company Website Development',
      description: 'Pembuatan website profesional untuk company profile, portfolio, dan landing page. Desain modern dengan SEO optimization dan loading cepat.',
      icon: `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>`,
      color: 'from-clover-green-400 to-clover-green-600'
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
      threshold: 0.1
    });
    observer.observe(node);
    
    return {
      destroy() {
        observer.disconnect();
      }
    };
  }
</script>

<section id="services" class="py-20 lg:py-32 bg-gradient-to-b from-white to-clover-green-50" use:observeSection>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Section Header -->
    <div class="text-center mb-16" class:opacity-0={!isVisible} class:translate-y-[30px]={!isVisible} class:opacity-100={isVisible} class:translate-y-0={isVisible} style="transition: all 0.8s ease-out;">
      <div class="inline-block mb-4">
        <span class="text-clover-green-600 font-semibold text-sm uppercase tracking-wide bg-clover-green-100 px-4 py-2 rounded-full">
          Layanan Kami
        </span>
      </div>
      <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-gray-900 mb-4">
        Solusi Teknologi Komprehensif
      </h2>
      <p class="text-lg text-gray-600 max-w-2xl mx-auto">
        Kami menyediakan berbagai layanan teknologi yang dapat disesuaikan dengan kebutuhan bisnis Anda
      </p>
    </div>

    <!-- Services Grid -->
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6 lg:gap-8">
      {#each services as service, index}
        <div 
          class="group bg-white rounded-xl shadow-lg hover:shadow-2xl transition-all duration-500 overflow-hidden border border-gray-100 hover:border-clover-green-200 cursor-pointer"
          class:opacity-0={!isVisible}
          class:translate-y-[30px]={!isVisible}
          class:opacity-100={isVisible}
          class:translate-y-0={isVisible}
          style="transition: all 0.6s ease-out {0.1 * (index + 1)}s; transform-origin: center;"
        >
          <!-- Card Header with Gradient -->
          <div class="bg-gradient-to-br {service.color} p-6 relative overflow-hidden">
            <div class="absolute top-0 right-0 w-32 h-32 bg-white opacity-10 rounded-full -mr-16 -mt-16"></div>
            <div class="relative z-10">
              <svg class="w-12 h-12 text-white mb-3 transform group-hover:scale-110 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                {@html service.icon}
              </svg>
              <h3 class="text-xl font-bold text-white">{service.title}</h3>
            </div>
          </div>

          <!-- Card Body -->
          <div class="p-6">
            <p class="text-gray-600 leading-relaxed mb-4">
              {service.description}
            </p>
            
            <div class="flex items-center text-clover-green-600 font-semibold group-hover:gap-2 transition-all">
              <span>Pelajari Lebih Lanjut</span>
              <svg class="w-5 h-5 transform group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
              </svg>
            </div>
          </div>

          <!-- Hover Effect Border -->
          <div class="absolute inset-0 border-2 border-clover-green-500 rounded-xl opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none"></div>
        </div>
      {/each}
    </div>

    <!-- Bottom CTA -->
    <div class="mt-16 text-center" class:opacity-0={!isVisible} class:translate-y-[30px]={!isVisible} class:opacity-100={isVisible} class:translate-y-0={isVisible} style="transition: all 0.8s ease-out 0.6s;">
      <p class="text-gray-600 mb-6">
        Tidak menemukan layanan yang Anda cari? Kami siap membantu dengan solusi custom.
      </p>
      <a 
        href="https://wa.me/6281234567890" 
        target="_blank"
        class="inline-flex items-center gap-2 px-8 py-4 bg-clover-green-600 text-white rounded-lg font-semibold hover:bg-clover-green-700 transform hover:-translate-y-1 transition-all duration-300 shadow-lg hover:shadow-xl"
      >
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
        </svg>
        Diskusikan Kebutuhan Anda
      </a>
    </div>
  </div>
</section>
