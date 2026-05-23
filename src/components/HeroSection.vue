<script setup>
import heroBg from '@/assets/images/hero.jpeg'
import { phone } from '../info';
</script>

<template>
  <section id="inicio"
    class="relative w-full sm:h-screen min-h-150 flex items-center justify-center pt-10 sm:pt-0 overflow-hidden">
    <!-- Background Image -->
    <div class="absolute inset-0 bg-cover bg-left md:bg-center bg-no-repeat z-0"
      :style="{ backgroundImage: `url(${heroBg})` }"></div>

    <!-- Overlay -->
    <div class="absolute inset-0 bg-linear-to-b from-black/35 via-black/50 to-black/65 z-1"></div>

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
      <div class="flex flex-col sm:flex-row items-center justify-center gap-6 sm:gap-8">
        <!-- Phone CTA -->
        <a :href="`tel:${phone.number}`" class="inline-flex items-center justify-center gap-2.5 bg-accent text-white px-6 py-3.5 rounded-xl text-base sm:text-lg font-semibold no-underline
                 shadow-[0_4px_20px_rgba(200,16,46,0.35)] hover:bg-accent-hover transition-all duration-200 min-w-60">
          <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"
            stroke-linecap="round" stroke-linejoin="round">
            <path
              d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z" />
          </svg>
          <span>{{ phone.display }}</span>
        </a>

        <!-- WhatsApp CTA -->
        <a :href="`https://wa.me/${phone.number.replace(/\+/g, '')}`" target="_blank" rel="noopener noreferrer"
          class="inline-flex items-center justify-center gap-2 py-3 border-2 border-green-600 text-green-500 rounded-xl text-lg sm:text-xl font-semibold hover:text-green-600 transition-all duration-200 min-w-60">
          <svg xmlns="http://www.w3.org/2000/svg" width="27" height="27" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
            class="icon icon-tabler icons-tabler-outline icon-tabler-brand-whatsapp">
            <path stroke="none" d="M0 0h24v24H0z" fill="none" />
            <path d="M3 21l1.65 -3.8a9 9 0 1 1 3.4 2.9l-5.05 .9" />
            <path d="M9 10a.5 .5 0 0 0 1 0v-1a.5 .5 0 0 0 -1 0v1a5 5 0 0 0 5 5h1a.5 .5 0 0 0 0 -1h-1a.5 .5 0 0 0 0 1" />
          </svg>
          <span>WhatsApp</span>
        </a>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-8 left-1/2 z-2" style="animation: bounce-scroll 2s infinite;">
      <svg class="w-7 h-7 text-white/70" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"
        stroke-linecap="round" stroke-linejoin="round">
        <polyline points="6 9 12 15 18 9" />
      </svg>
    </div>
  </section>
</template>
