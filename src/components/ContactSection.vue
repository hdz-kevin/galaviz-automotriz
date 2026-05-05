<script setup>
import { ref, onMounted } from 'vue'

const sectionRef = ref(null)
const isVisible = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        isVisible.value = true
        observer.disconnect()
      }
    },
    { threshold: 0.15 }
  )
  if (sectionRef.value) observer.observe(sectionRef.value)
})
</script>

<template>
  <section id="contacto" ref="sectionRef" class="py-20 md:py-28 bg-white">
    <div class="max-w-325 mx-auto px-6">
      <!-- Heading -->
      <div class="text-center mb-14">
        <span class="inline-block w-15 h-0.75 bg-accent rounded-sm mb-4"></span>
        <h2 class="text-3xl md:text-4xl font-extrabold text-gray-900 tracking-tight mb-3">Contáctanos</h2>
        <p class="text-lg text-text-light">Estamos para servirte</p>
      </div>

      <!-- Content -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 lg:gap-14">
        <!-- Info Column -->
        <div
          class="flex flex-col gap-6 transition-all duration-700 ease-out"
          :class="isVisible ? 'opacity-100 translate-x-0' : 'opacity-0 -translate-x-10'"
        >
          <!-- Ubicación -->
          <div class="flex items-start gap-4 border-b border-b-gray-200 pt-5 pb-9 sm:px-5">
            <div>
              <svg class="w-6 h-6 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
            </div>
            <div>
              <h3 class="font-semibold text-lg m-0 mb-1">Ubicación</h3>
              <p class="m-0 leading-loose">
                Av. Tecnológico #4500, Col. Las Granjas<br />
                Chihuahua, Chih. CP 31160
              </p>
            </div>
          </div>

          <!-- Horario -->
          <div class="flex items-start gap-4 border-b border-b-gray-200 pt-5 pb-9 sm:px-5">
            <div>
              <svg class="w-6 h-6 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10"/>
                <polyline points="12 6 12 12 16 14"/>
              </svg>
            </div>
            <div>
              <h3 class="font-semibold text-lg m-0 mb-1">Horario</h3>
              <div class="leading-loose">
                <p class="m-0 font-normal">Lunes a Viernes: <span class="font-normal pl-1">8:00 AM - 8:00 PM</span></p>
                <p class="m-0 font-normal">Sábado: <span class="font-normal pl-1">9:00 AM - 2:00 PM</span></p>
                <p class="m-0 font-normal">Domingo: <span class="text-accent font-normal pl-1">Cerrado</span></p>
              </div>
            </div>
          </div>

          <!-- Teléfono -->
          <div class="flex items-start gap-4 pt-5 pb-9 sm:px-5">
            <div>
              <svg class="w-6 h-6 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
              </svg>
            </div>
            <div class="leading-loose">
              <h3 class="font-semibold text-lg m-0 mb-1">Teléfono</h3>
              <a href="tel:+526141234567" class="font-medium underline text-sm">
                (614) 123-4567
              </a>
            </div>
          </div>
        </div>

        <!-- Map Column -->
        <div
          class="transition-all duration-700 ease-out delay-200"
          :class="isVisible ? 'opacity-100 translate-x-0' : 'opacity-0 translate-x-10'"
        >
          <div class="w-full h-full min-h-95 rounded-2xl overflow-hidden border border-white/10 shadow-lg">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m13!1m8!1m3!1d2362.983163802857!2d-97.37991151092535!3d19.8101127668149!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zMTnCsDQ4JzM2LjgiTiA5N8KwMjInNDUuNSJX!5e1!3m2!1ses-419!2smx!4v1777989242960!5m2!1ses-419!2smx"
              width="100%"
              height="100%"
              style="border:0; min-height: 380px;"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              title="Ubicación de Galaviz Automotriz"
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
