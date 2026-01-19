<script>
  let scrollY = 0;
  
  function scrollToServices() {
    document.getElementById('services')?.scrollIntoView({ behavior: 'smooth' });
  }
  
  function scrollToContact() {
    document.getElementById('contact')?.scrollIntoView({ behavior: 'smooth' });
  }
</script>

<svelte:window bind:scrollY />

<section class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-clover-green-50 via-white to-clover-green-50 overflow-hidden">
  <!-- Decorative Elements -->
  <div class="absolute inset-0 overflow-hidden pointer-events-none">
    <div class="absolute -top-40 -right-40 w-96 h-96 bg-clover-green-200 rounded-full opacity-20 blur-3xl"></div>
    <div class="absolute -bottom-40 -left-40 w-96 h-96 bg-clover-green-300 rounded-full opacity-20 blur-3xl"></div>
  </div>

  <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 text-center">
    <!-- Logo/Brand -->
    <div class="mb-8 animate-fade-in">
      <div class="inline-flex items-center justify-center mb-4">
        <div class="w-16 h-16 bg-clover-green-600 rounded-full flex items-center justify-center">
          <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 2C10.9 2 10 2.9 10 4C10 4.7 10.4 5.4 11 5.7C11 5.8 11 5.9 11 6C11 7.1 10.1 8 9 8C7.9 8 7 7.1 7 6C7 5.9 7 5.8 7 5.7C7.6 5.4 8 4.7 8 4C8 2.9 7.1 2 6 2C4.9 2 4 2.9 4 4C4 4.7 4.4 5.4 5 5.7C5 5.8 5 5.9 5 6C5 8.2 6.8 10 9 10C9.5 10 9.9 9.9 10.4 9.7C10.8 11 11.8 12 13 12.3V13C13 14.1 12.1 15 11 15C9.9 15 9 14.1 9 13C9 12.9 9 12.8 9 12.7C9.6 12.4 10 11.7 10 11C10 9.9 9.1 9 8 9C6.9 9 6 9.9 6 11C6 11.7 6.4 12.4 7 12.7C7 12.8 7 12.9 7 13C7 15.2 8.8 17 11 17C11.5 17 11.9 16.9 12.4 16.7C12.8 18 13.8 19 15 19.3V20C15 21.1 14.1 22 13 22C11.9 22 11 21.1 11 20C11 19.9 11 19.8 11 19.7C11.6 19.4 12 18.7 12 18C12 16.9 11.1 16 10 16C8.9 16 8 16.9 8 18C8 18.7 8.4 19.4 9 19.7C9 19.8 9 19.9 9 20C9 22.2 10.8 24 13 24C15.2 24 17 22.2 17 20V19.3C18.2 19 19.2 18 19.6 16.7C20.1 16.9 20.5 17 21 17C23.2 17 25 15.2 25 13C25 12.9 25 12.8 25 12.7C25.6 12.4 26 11.7 26 11C26 9.9 25.1 9 24 9C22.9 9 22 9.9 22 11C22 11.7 22.4 12.4 23 12.7C23 12.8 23 12.9 23 13C23 14.1 22.1 15 21 15C19.9 15 19 14.1 19 13V12.3C20.2 12 21.2 11 21.6 9.7C22.1 9.9 22.5 10 23 10C25.2 10 27 8.2 27 6C27 5.9 27 5.8 27 5.7C27.6 5.4 28 4.7 28 4C28 2.9 27.1 2 26 2C24.9 2 24 2.9 24 4C24 4.7 24.4 5.4 25 5.7C25 5.8 25 5.9 25 6C25 7.1 24.1 8 23 8C21.9 8 21 7.1 21 6C21 5.9 21 5.8 21 5.7C21.6 5.4 22 4.7 22 4C22 2.9 21.1 2 20 2C18.9 2 18 2.9 18 4C18 4.7 18.4 5.4 19 5.7C19 5.8 19 5.9 19 6C19 8.2 17.2 10 15 10C14.5 10 14.1 9.9 13.6 9.7C13.2 8.4 12.2 7.4 11 7.1V6C11 5.9 11 5.8 11 5.7C11.6 5.4 12 4.7 12 4C12 2.9 11.1 2 10 2Z"/>
          </svg>
        </div>
      </div>
      <h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold text-gray-900 mb-2">
        <span class="text-clover-green-600">Clover</span>Dev
      </h1>
    </div>

    <!-- Headline -->
    <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-gray-900 mb-6 text-balance max-w-4xl mx-auto">
      Solusi Teknologi Terpadu untuk Masa Depan Digital Anda
    </h2>

    <!-- Subheadline -->
    <p class="text-lg sm:text-xl text-gray-600 mb-12 max-w-3xl mx-auto leading-relaxed">
      Spesialis dalam <span class="font-semibold text-clover-green-600">Robotika</span>, 
      <span class="font-semibold text-clover-green-600">Embedded System</span>, 
      <span class="font-semibold text-clover-green-600">IoT</span>, dan 
      <span class="font-semibold text-clover-green-600">Web Development</span>. 
      Kami menghadirkan inovasi teknologi yang efektif, efisien, dan berkelanjutan.
    </p>

    <!-- CTA Buttons -->
    <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
      <a 
        href="https://wa.me/6281234567890" 
        target="_blank"
        class="group px-8 py-4 bg-clover-green-600 text-white rounded-lg font-semibold text-lg shadow-lg hover:bg-clover-green-700 hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300 flex items-center gap-2"
      >
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
        </svg>
        Konsultasi Sekarang
      </a>
      <button 
        on:click={scrollToServices}
        class="px-8 py-4 bg-white text-clover-green-600 rounded-lg font-semibold text-lg border-2 border-clover-green-600 hover:bg-clover-green-50 transform hover:-translate-y-1 transition-all duration-300"
      >
        Lihat Layanan
      </button>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <svg class="w-6 h-6 text-clover-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/>
      </svg>
    </div>
  </div>
</section>

<style>
  @keyframes fade-in {
    from {
      opacity: 0;
      transform: translateY(-20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .animate-fade-in {
    animation: fade-in 1s ease-out;
  }
</style>
