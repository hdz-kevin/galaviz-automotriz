<script setup>
import { ref, onMounted } from 'vue'
import aboutImg from '@/assets/images/about.webp'

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

const stats = [
  { value: '15+', label: 'Años de experiencia' },
  { value: '1,000+', label: 'Clientes satisfechos' },
  { value: '100%', label: 'Garantía en servicio' },
]
</script>

<template>
  <section id="nosotros" ref="sectionRef" class="py-20 md:py-28 bg-bg-alt">
    <div class="max-w-[1300px] mx-auto px-6">
      <!-- Heading -->
      <div class="text-center mb-14">
        <span class="inline-block w-[60px] h-[3px] bg-accent rounded-sm mb-4"></span>
        <h2 class="text-3xl md:text-4xl font-extrabold text-gray-900 tracking-tight mb-3">Nosotros</h2>
        <p class="text-lg text-text-light">Conoce nuestra historia y compromiso</p>
      </div>

      <!-- Content: Image + Text -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-16 items-center mb-16">
        <!-- Image -->
        <div
          class="transition-all duration-700 ease-out"
          :class="isVisible ? 'opacity-100 translate-x-0' : 'opacity-0 -translate-x-10'"
        >
          <img
            :src="aboutImg"
            alt="Taller Galaviz Automotriz"
            class="w-full rounded-2xl shadow-lg object-cover max-h-[450px]"
          />
        </div>

        <!-- Text -->
        <div
          class="transition-all duration-700 ease-out delay-200"
          :class="isVisible ? 'opacity-100 translate-x-0' : 'opacity-0 translate-x-10'"
        >
          <h3 class="text-2xl font-bold text-gray-900 mb-4">
            Más de 15 años cuidando tu vehículo
          </h3>
          <p class="text-text-light leading-loose mb-4">
            En <strong class="text-gray-900">Galaviz Automotriz</strong> nos especializamos en brindar un servicio
            mecánico integral de la más alta calidad. Desde nuestros inicios, hemos atendido a cientos
            de clientes con profesionalismo, honestidad y un compromiso inquebrantable con la excelencia.
          </p>
          <p class="text-text-light leading-loose mb-7">
            Contamos con más de 15 años de experiencia laboral para
            garantizar que tu vehículo reciba la atención que merece. Nuestro objetivo es que salgas
            del taller con total confianza y tranquilidad.
          </p>

          <!-- Pagos con tarjeta badge -->
          <div class="flex items-center gap-4 bg-white rounded-xl p-4 border border-gray-200 shadow-sm">
            <div class="hidden sm:flex shrink-0 w-12 h-12 bg-accent/10 rounded-lg items-center justify-center">
              <svg class="w-6 h-6 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <rect x="1" y="4" width="22" height="16" rx="2" ry="2"/>
                <line x1="1" y1="10" x2="23" y2="10"/>
              </svg>
            </div>
            <div>
              <p class="font-semibold text-gray-900 m-0">Aceptamos pagos con tarjeta</p>
              <p class="text-[13px] text-gray-800 m-0 mt-1">Débito y crédito · Visa, Mastercard y más</p>
            </div>
            <div class="flex items-center gap-2 ml-auto">
              <!-- Visa -->
              <svg class="h-7" viewBox="0 0 48 32" fill="none">
                <rect width="48" height="32" rx="4" fill="#1A1F71"/>
                <path d="M19.5 21h-3l1.9-11h3l-1.9 11zm12.2-10.7c-.6-.2-1.5-.5-2.7-.5-3 0-5.1 1.5-5.1 3.7 0 1.6 1.5 2.5 2.7 3.1 1.2.6 1.6.9 1.6 1.4 0 .8-.9 1.1-1.8 1.1-1.2 0-1.9-.2-2.9-.6l-.4-.2-.4 2.5c.7.3 2 .6 3.4.6 3.2 0 5.2-1.5 5.2-3.8 0-1.3-.8-2.3-2.5-3.1-1-.5-1.7-.9-1.7-1.4 0-.5.5-1 1.7-1 1 0 1.7.2 2.2.4l.3.1.4-2.3zm7.8-.3h-2.3c-.7 0-1.3.2-1.6.9L31 21h3.2l.6-1.8h3.9l.4 1.8h2.8l-2.4-11zm-3.3 7.1l1.6-4.2.8 4.2h-2.4zM17.2 10l-2.8 7.5-.3-1.5c-.5-1.7-2.1-3.6-3.9-4.5l2.7 9.5h3.2L20.4 10h-3.2z" fill="white"/>
                <path d="M12.2 10H7.1l-.1.3c3.8.9 6.3 3.2 7.4 5.9L13.1 11c-.2-.7-.7-.9-1-.9z" fill="#F9A51A"/>
              </svg>
              <!-- Mastercard -->
              <svg class="h-7" viewBox="0 0 48 32" fill="none">
                <rect width="48" height="32" rx="4" fill="#252525"/>
                <circle cx="19" cy="16" r="8" fill="#EB001B"/>
                <circle cx="29" cy="16" r="8" fill="#F79E1B"/>
                <path d="M24 10.3a8 8 0 0 1 0 11.4 8 8 0 0 1 0-11.4z" fill="#FF5F00"/>
              </svg>
            </div>
          </div>
        </div>
      </div>

      <!-- Stats -->
      <div
        class="grid grid-cols-1 sm:grid-cols-3 gap-6 transition-all duration-700 ease-out delay-400"
        :class="isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-8'"
      >
        <div
          v-for="stat in stats"
          :key="stat.label"
          class="text-center bg-white rounded-xl py-6 px-4 border border-gray-100 shadow-sm"
        >
          <p class="text-3xl md:text-4xl font-extrabold text-accent m-0 mb-2">{{ stat.value }}</p>
          <p class=" text-text-main m-0">{{ stat.label }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
