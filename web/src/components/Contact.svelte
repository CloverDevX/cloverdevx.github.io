<script>
  let isVisible = false;
  let formData = {
    name: '',
    email: '',
    phone: '',
    service: '',
    message: ''
  };
  let isSubmitting = false;
  let submitStatus = null;

  const services = [
    'Robotika',
    'Embedded System',
    'Internet of Things (IoT)',
    'Web Application Development',
    'Company Website Development',
    'Lainnya'
  ];

  function handleSubmit(e) {
    e.preventDefault();
    isSubmitting = true;
    
    // Simulate form submission
    setTimeout(() => {
      isSubmitting = false;
      submitStatus = 'success';
      
      // Reset form after 3 seconds
      setTimeout(() => {
        formData = { name: '', email: '', phone: '', service: '', message: '' };
        submitStatus = null;
      }, 3000);
    }, 1500);
  }

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

<section id="contact" class="py-20 lg:py-32 bg-gradient-to-b from-clover-green-50 to-white relative overflow-hidden" use:observeSection>
  <!-- Background Pattern -->
  <div class="absolute inset-0 opacity-5">
    <div class="absolute inset-0" style="background-image: radial-gradient(circle, #16a34a 1px, transparent 1px); background-size: 30px 30px;"></div>
  </div>

  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <!-- Section Header -->
    <div class="text-center mb-16" class:opacity-0={!isVisible} class:translate-y-[30px]={!isVisible} class:opacity-100={isVisible} class:translate-y-0={isVisible} style="transition: all 0.8s ease-out;">
      <div class="inline-block mb-4">
        <span class="text-clover-green-600 font-semibold text-sm uppercase tracking-wide bg-white px-4 py-2 rounded-full shadow-sm">
          Hubungi Kami
        </span>
      </div>
      <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-gray-900 mb-4">
        Mari Diskusikan Kebutuhan Teknologi Anda
      </h2>
      <p class="text-lg text-gray-600 max-w-2xl mx-auto">
        Tim kami siap membantu mewujudkan solusi teknologi yang tepat untuk bisnis Anda
      </p>
    </div>

    <div class="grid lg:grid-cols-2 gap-12 items-start">
      <!-- Left: Contact Info -->
      <div class:opacity-0={!isVisible} class:translate-x-[-30px]={!isVisible} class:opacity-100={isVisible} class:translate-x-0={isVisible} style="transition: all 0.8s ease-out 0.2s;">
        <div class="space-y-8">
          <!-- Quick Contact -->
          <div class="bg-white rounded-2xl p-8 shadow-xl border border-clover-green-100">
            <h3 class="text-2xl font-bold text-gray-900 mb-6">Kontak Langsung</h3>
            
            <div class="space-y-4">
              <!-- WhatsApp -->
              <a 
                href="https://wa.me/6281234567890" 
                target="_blank"
                class="flex items-center gap-4 p-4 bg-clover-green-50 rounded-xl hover:bg-clover-green-100 transition-colors group"
              >
                <div class="w-12 h-12 bg-clover-green-600 rounded-lg flex items-center justify-center group-hover:scale-110 transition-transform">
                  <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
                  </svg>
                </div>
                <div>
                  <p class="font-semibold text-gray-900">WhatsApp</p>
                  <p class="text-sm text-gray-600">+62 812-3456-7890</p>
                </div>
              </a>

              <!-- Email -->
              <a 
                href="mailto:contact@cloverdev.id" 
                class="flex items-center gap-4 p-4 bg-clover-green-50 rounded-xl hover:bg-clover-green-100 transition-colors group"
              >
                <div class="w-12 h-12 bg-clover-green-600 rounded-lg flex items-center justify-center group-hover:scale-110 transition-transform">
                  <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                  </svg>
                </div>
                <div>
                  <p class="font-semibold text-gray-900">Email</p>
                  <p class="text-sm text-gray-600">contact@cloverdev.id</p>
                </div>
              </a>
            </div>
          </div>

          <!-- Info Box -->
          <div class="bg-gradient-to-br from-clover-green-600 to-clover-green-700 rounded-2xl p-8 text-white shadow-xl">
            <svg class="w-12 h-12 mb-4 opacity-90" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
            </svg>
            <h3 class="text-xl font-bold mb-3">Konsultasi Gratis</h3>
            <p class="text-clover-green-50 leading-relaxed">
              Dapatkan konsultasi gratis untuk menentukan solusi teknologi yang paling tepat untuk kebutuhan bisnis Anda.
            </p>
          </div>
        </div>
      </div>

      <!-- Right: Contact Form -->
      <div class:opacity-0={!isVisible} class:translate-x-[30px]={!isVisible} class:opacity-100={isVisible} class:translate-x-0={isVisible} style="transition: all 0.8s ease-out 0.4s;">
        <div class="bg-white rounded-2xl p-8 shadow-xl border border-gray-100">
          <form on:submit={handleSubmit} class="space-y-6">
            <!-- Name -->
            <div>
              <label for="name" class="block text-sm font-semibold text-gray-700 mb-2">
                Nama Lengkap <span class="text-red-500">*</span>
              </label>
              <input
                type="text"
                id="name"
                bind:value={formData.name}
                required
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-clover-green-500 focus:border-transparent transition-all outline-none"
                placeholder="Nama Anda"
              />
            </div>

            <!-- Email -->
            <div>
              <label for="email" class="block text-sm font-semibold text-gray-700 mb-2">
                Email <span class="text-red-500">*</span>
              </label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                required
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-clover-green-500 focus:border-transparent transition-all outline-none"
                placeholder="email@example.com"
              />
            </div>

            <!-- Phone -->
            <div>
              <label for="phone" class="block text-sm font-semibold text-gray-700 mb-2">
                Nomor Telepon
              </label>
              <input
                type="tel"
                id="phone"
                bind:value={formData.phone}
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-clover-green-500 focus:border-transparent transition-all outline-none"
                placeholder="+62 812-3456-7890"
              />
            </div>

            <!-- Service -->
            <div>
              <label for="service" class="block text-sm font-semibold text-gray-700 mb-2">
                Layanan yang Diminati
              </label>
              <select
                id="service"
                bind:value={formData.service}
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-clover-green-500 focus:border-transparent transition-all outline-none bg-white"
              >
                <option value="">Pilih layanan</option>
                {#each services as service}
                  <option value={service}>{service}</option>
                {/each}
              </select>
            </div>

            <!-- Message -->
            <div>
              <label for="message" class="block text-sm font-semibold text-gray-700 mb-2">
                Pesan <span class="text-red-500">*</span>
              </label>
              <textarea
                id="message"
                bind:value={formData.message}
                required
                rows="4"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-clover-green-500 focus:border-transparent transition-all outline-none resize-none"
                placeholder="Ceritakan kebutuhan teknologi Anda..."
              ></textarea>
            </div>

            <!-- Submit Button -->
            <button
              type="submit"
              disabled={isSubmitting}
              class="w-full px-6 py-4 bg-clover-green-600 text-white rounded-lg font-semibold hover:bg-clover-green-700 transform hover:-translate-y-1 transition-all duration-300 shadow-lg hover:shadow-xl disabled:opacity-50 disabled:cursor-not-allowed disabled:transform-none"
            >
              {#if isSubmitting}
                <span class="flex items-center justify-center gap-2">
                  <svg class="animate-spin w-5 h-5" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                  </svg>
                  Mengirim...
                </span>
              {:else}
                Kirim Pesan
              {/if}
            </button>

            <!-- Success Message -->
            {#if submitStatus === 'success'}
              <div class="p-4 bg-clover-green-50 border border-clover-green-200 rounded-lg text-clover-green-700 text-center">
                ✓ Pesan berhasil dikirim! Kami akan menghubungi Anda segera.
              </div>
            {/if}
          </form>
        </div>
      </div>
    </div>
  </div>
</section>
