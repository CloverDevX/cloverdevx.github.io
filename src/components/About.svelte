<script>
  let isVisible = false;
  
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

<section id="about" class="py-20 lg:py-32 bg-white" use:observeSection>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid lg:grid-cols-2 gap-12 items-center">
      <!-- Left: Visual Element -->
      <div class="relative" class:opacity-0={!isVisible} class:translate-x-[-50px]={!isVisible} class:opacity-100={isVisible} class:translate-x-0={isVisible} style="transition: all 0.8s ease-out;">
        <div class="relative bg-gradient-to-br from-clover-green-500 to-clover-green-700 rounded-2xl p-12 shadow-2xl">
          <div class="absolute -top-6 -right-6 w-32 h-32 bg-clover-green-300 rounded-full opacity-50 blur-2xl"></div>
          <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-clover-green-400 rounded-full opacity-50 blur-2xl"></div>
          
          <div class="relative text-white space-y-8">
            <div class="flex items-center gap-4">
              <svg class="w-12 h-12" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"/>
              </svg>
              <div>
                <p class="text-sm opacity-90">Fokus Kami</p>
                <p class="font-bold text-xl">Inovasi Teknologi</p>
              </div>
            </div>
            
            <div class="flex items-center gap-4">
              <svg class="w-12 h-12" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
              </svg>
              <div>
                <p class="text-sm opacity-90">Pendekatan</p>
                <p class="font-bold text-xl">Solusi Berbasis Kebutuhan</p>
              </div>
            </div>
            
            <div class="flex items-center gap-4">
              <svg class="w-12 h-12" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/>
              </svg>
              <div>
                <p class="text-sm opacity-90">Komitmen</p>
                <p class="font-bold text-xl">Teknologi Berkelanjutan</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Right: Content -->
      <div class:opacity-0={!isVisible} class:translate-x-[50px]={!isVisible} class:opacity-100={isVisible} class:translate-x-0={isVisible} style="transition: all 0.8s ease-out 0.2s;">
        <div class="inline-block mb-4">
          <span class="text-clover-green-600 font-semibold text-sm uppercase tracking-wide bg-clover-green-50 px-4 py-2 rounded-full">
            Tentang Kami
          </span>
        </div>
        
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-gray-900 mb-6">
          Startup Teknologi yang Menghadirkan Solusi Inovatif
        </h2>
        
        <div class="space-y-4 text-gray-600 text-lg leading-relaxed">
          <p>
            <strong class="text-gray-900">Cloverdev</strong> adalah startup teknologi yang berfokus pada pengembangan 
            <strong class="text-clover-green-600">solusi teknologi terpadu</strong> untuk membantu individu, institusi, 
            dan perusahaan dalam mengadopsi teknologi secara efektif, efisien, dan berkelanjutan.
          </p>
          
          <p>
            Kami mengkhususkan diri dalam bidang <strong class="text-gray-900">Robotika</strong>, 
            <strong class="text-gray-900">Embedded System</strong>, 
            <strong class="text-gray-900">Internet of Things (IoT)</strong>, dan 
            <strong class="text-gray-900">Web Application Development</strong>.
          </p>
          
          <p>
            Dengan pendekatan <strong class="text-clover-green-600">berbasis kebutuhan klien</strong> dan 
            penggunaan <strong class="text-clover-green-600">teknologi tepat guna</strong>, 
            kami memastikan setiap solusi yang kami berikan tidak hanya memenuhi kebutuhan saat ini, 
            tetapi juga dapat berkembang seiring dengan pertumbuhan bisnis Anda.
          </p>
        </div>

        <div class="mt-8 grid grid-cols-3 gap-4">
          <div class="text-center p-4 bg-clover-green-50 rounded-lg hover:bg-clover-green-100 transition-colors">
            <p class="text-3xl font-bold text-clover-green-600">5+</p>
            <p class="text-sm text-gray-600 mt-1">Teknologi</p>
          </div>
          <div class="text-center p-4 bg-clover-green-50 rounded-lg hover:bg-clover-green-100 transition-colors">
            <p class="text-3xl font-bold text-clover-green-600">100%</p>
            <p class="text-sm text-gray-600 mt-1">Custom</p>
          </div>
          <div class="text-center p-4 bg-clover-green-50 rounded-lg hover:bg-clover-green-100 transition-colors">
            <p class="text-3xl font-bold text-clover-green-600">24/7</p>
            <p class="text-sm text-gray-600 mt-1">Support</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
