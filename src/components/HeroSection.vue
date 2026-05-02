<script setup>
import heroBg from '@/assets/images/hero.webp'
</script>

<template>
  <section id="inicio" class="relative w-full h-screen min-h-[600px] flex items-center justify-center overflow-hidden">
    <!-- Background Image -->
    <div
      class="absolute inset-0 bg-cover bg-center bg-no-repeat z-0"
      :style="{ backgroundImage: `url(${heroBg})` }"
    ></div>

    <!-- Overlay -->
    <div class="absolute inset-0 bg-gradient-to-b from-black/50 via-black/65 to-black/80 z-[1]"></div>

    <!-- Content -->
    <div class="relative z-[2] text-center px-6" style="animation: fadeInUp 0.8s ease-out both;">
      <!-- Badge -->
      <span
        class="inline-block bg-accent/15 border border-accent/40 text-red-400
               text-xs font-semibold tracking-wider uppercase
               px-5 py-1.5 rounded-full mb-6 backdrop-blur-sm"
      >
        Taller Mecánico Profesional
      </span>

      <!-- Title -->
      <h1 class="text-[clamp(2.5rem,7vw,4.5rem)] font-extrabold text-white leading-[1.05] tracking-tight m-0 mb-4">
        GALAVIZ
        <br />
        <span class="font-normal text-[0.5em] tracking-[0.2em] block text-white/75">AUTOMOTRIZ</span>
      </h1>

      <!-- Slogan -->
      <p class="text-[clamp(1rem,2.5vw,1.2rem)] text-white/70 font-normal max-w-[500px] mx-auto mb-10">
        Tu taller de confianza — Servicio profesional garantizado
      </p>

      <!-- CTA -->
      <a
        href="tel:+526141234567"
        class="inline-flex items-center gap-2.5 bg-accent text-white
               px-8 py-3.5 rounded-xl text-lg font-semibold no-underline
               shadow-[0_4px_20px_rgba(200,16,46,0.35)]
               hover:bg-accent-hover hover:-translate-y-0.5
               hover:shadow-[0_6px_28px_rgba(200,16,46,0.45)]
               transition-all duration-200"
      >
        <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
        </svg>
        <span>(614) 123-4567</span>
      </a>
    </div>

    <!-- Scroll Indicator -->
    <div
      class="absolute bottom-8 left-1/2 z-[2]"
      style="animation: bounce-scroll 2s infinite;"
    >
      <svg class="w-7 h-7 text-white/50" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <polyline points="6 9 12 15 18 9"/>
      </svg>
    </div>
  </section>
</template>
