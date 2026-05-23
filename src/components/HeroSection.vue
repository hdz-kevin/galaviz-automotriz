<script setup>
import heroBg from '@/assets/images/hero.jpeg'
import { phone } from '../info';
</script>

<template>
  <section id="inicio" class="relative w-full sm:h-screen min-h-150 flex items-center justify-center pt-8 sm:pt-0 overflow-hidden">
    <!-- Background Image -->
    <div
      class="absolute inset-0 bg-cover bg-left md:bg-center bg-no-repeat z-0"
      :style="{ backgroundImage: `url(${heroBg})` }"
    ></div>

    <!-- Overlay -->
    <div class="absolute inset-0 bg-linear-to-b from-black/35 via-black/50 to-black/60 z-1"></div>

    <!-- Content -->
    <div class="relative z-2 text-center px-6" style="animation: fadeInUp 0.8s ease-out both;">
      <!-- Title -->
      <h1 class="text-4xl sm:text-6xl font-extrabold text-white leading-[1.05] m-0 mb-7 uppercase">
        Galaviz Automotriz
      </h1>

      <!-- Slogan -->
      <p class="text-base sm:text-xl text-white leading-relaxed max-w-125 mx-auto mb-11">
        Tu taller de confianza — Servicio profesional garantizado
      </p>

      <!-- CTA Buttons -->
      <div class="flex items-center justify-center gap-4">
        <!-- Phone CTA -->
        <a
          :href="`tel:${phone.number}`"
          class="inline-flex items-center justify-center gap-2.5 bg-accent text-white px-8 py-3.5 rounded-xl text-base sm:text-lg font-semibold no-underline
                 shadow-[0_4px_20px_rgba(200,16,46,0.35)] hover:bg-accent-hover transition-all duration-200 min-w-65"
        >
          <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
          </svg>
          <span>{{ phone.display }}</span>
        </a>

        <!-- WhatsApp CTA -->
        <a
          :href="`https://wa.me/${phone.number.replace(/\+/g, '')}`"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center justify-center bg-[#25D366] text-white p-5 rounded-full text-base sm:text-lg font-semibold no-underline
                 shadow-[0_4px_20px_rgba(37,211,102,0.35)] hover:bg-[#20BA5A] transition-all duration-200"
        >
          <svg class="w-5 h-5" viewBox="0 0 24 24" fill="currentColor">
            <path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946C.06 5.348 5.397.01 12.008.01c3.202.001 6.212 1.246 8.477 3.514 2.266 2.268 3.507 5.28 3.505 8.484-.004 6.657-5.34 11.997-11.953 11.997-2.005-.001-3.973-.502-5.724-1.457L0 24zm6.59-4.846c1.6.95 3.188 1.449 4.793 1.451 5.48.002 9.938-4.455 9.94-9.934.001-2.652-1.03-5.148-2.902-7.022C16.549 1.77 14.058.736 11.406.736 5.923.736 1.467 5.19 1.465 10.672c-.001 1.793.48 3.544 1.39 5.105l-1.008 3.685 3.78-1.002-.507-.291zm11.387-5.464c-.3-.149-1.774-.875-2.046-.975-.272-.1-.471-.149-.669.149-.198.3-.769.975-.943 1.173-.173.198-.348.223-.648.074-.3-.149-1.267-.467-2.414-1.491-.893-.797-1.496-1.782-1.671-2.08-.174-.299-.018-.46.131-.609.135-.134.3-.349.449-.523.15-.174.2-.299.3-.497.1-.198.05-.372-.025-.521-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.299-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.774-.726 2.022-1.429.247-.704.247-1.307.173-1.43-.075-.124-.272-.198-.57-.347z"/>
          </svg>
        </a>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div
      class="absolute bottom-8 left-1/2 z-2"
      style="animation: bounce-scroll 2s infinite;"
    >
      <svg class="w-7 h-7 text-white/70" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="6 9 12 15 18 9"/>
      </svg>
    </div>
  </section>
</template>
