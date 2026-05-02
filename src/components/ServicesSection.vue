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
    { threshold: 0.1 }
  )
  if (sectionRef.value) observer.observe(sectionRef.value)
})

const services = [
  {
    title: 'Servicio de Frenos',
    description: 'Revisión completa de pastillas, discos y líquido de frenos para garantizar tu seguridad en el camino.',
    icon: 'brakes',
  },
  {
    title: 'Cambio de Aceite y Filtro',
    description: 'Cambio de aceite de motor y filtro con lubricantes de alta calidad para proteger y alargar la vida de tu motor.',
    icon: 'oil',
  },
  {
    title: 'Afinación (Tune Up)',
    description: 'Afinación completa del motor: bujías, filtros, cables e inyección para un rendimiento óptimo de tu vehículo.',
    icon: 'tuneup',
  },
  {
    title: 'Servicio de Baterías',
    description: 'Diagnóstico, carga y reemplazo de baterías. Evita quedarte varado en el camino con un mantenimiento adecuado.',
    icon: 'battery',
  },
  {
    title: 'Suspensión y Dirección',
    description: 'Revisión y reparación de amortiguadores, resortes, rótulas y sistema de dirección para una conducción estable.',
    icon: 'suspension',
  },
  {
    title: 'Aire Acondicionado',
    description: 'Diagnóstico, recarga de gas y reparación del sistema de climatización para tu confort en todo momento.',
    icon: 'ac',
  },
  {
    title: 'Diagnóstico Computarizado',
    description: 'Lectura de códigos de error con escáner profesional para identificar fallas electrónicas con precisión.',
    icon: 'diagnostic',
  },
  {
    title: 'Sistema Eléctrico',
    description: 'Diagnóstico y reparación de alternador, marcha, luces y todo el sistema eléctrico de tu vehículo.',
    icon: 'electrical',
  },
  {
    title: 'Servicio de Llantas',
    description: 'Rotación, balanceo, alineación y cambio de llantas para una conducción segura y un desgaste uniforme.',
    icon: 'tires',
  },
]
</script>

<template>
  <section id="servicios" ref="sectionRef" class="py-20 md:py-28 bg-white">
    <div class="max-w-[1200px] mx-auto px-6">
      <!-- Heading -->
      <div class="text-center mb-14">
        <span class="inline-block w-[60px] h-[3px] bg-accent rounded-sm mb-4"></span>
        <h2 class="text-3xl md:text-4xl font-extrabold text-gray-900 tracking-tight mb-3">Nuestros Servicios</h2>
        <p class="text-lg text-text-light">Lo que hacemos por ti y tu vehículo</p>
      </div>

      <!-- Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(service, index) in services"
          :key="service.title"
          class="bg-white border border-gray-200 rounded-2xl p-7
                 transition-all duration-300 ease-out cursor-default
                 hover:-translate-y-1 hover:shadow-lg hover:border-l-[3px] hover:border-l-accent
                 group"
          :class="isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-8'"
          :style="isVisible ? `transition-delay: ${index * 80}ms` : ''"
        >
          <!-- Icon -->
          <div class="w-14 h-14 rounded-xl bg-accent/10 flex items-center justify-center mb-5 group-hover:bg-accent/15 transition-colors duration-300">
            <!-- Brakes -->
            <svg v-if="service.icon === 'brakes'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="10"/>
              <circle cx="12" cy="12" r="4"/>
              <line x1="12" y1="2" x2="12" y2="5"/>
              <line x1="12" y1="19" x2="12" y2="22"/>
              <line x1="2" y1="12" x2="5" y2="12"/>
              <line x1="19" y1="12" x2="22" y2="12"/>
            </svg>
            <!-- Oil -->
            <svg v-else-if="service.icon === 'oil'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <path d="M12 2C12 2 7 8.5 7 13a5 5 0 0 0 10 0c0-4.5-5-11-5-11z"/>
            </svg>
            <!-- Tune Up -->
            <svg v-else-if="service.icon === 'tuneup'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>
            </svg>
            <!-- Battery -->
            <svg v-else-if="service.icon === 'battery'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <rect x="2" y="7" width="18" height="14" rx="2"/>
              <line x1="22" y1="11" x2="22" y2="17"/>
              <line x1="6" y1="3" x2="6" y2="7"/>
              <line x1="14" y1="3" x2="14" y2="7"/>
              <line x1="8" y1="12" x2="12" y2="12"/>
              <line x1="10" y1="10" x2="10" y2="14"/>
            </svg>
            <!-- Suspension -->
            <svg v-else-if="service.icon === 'suspension'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="19" r="3"/>
              <path d="M12 2v4"/>
              <path d="M8 6l4 4 4-4"/>
              <path d="M12 10v6"/>
            </svg>
            <!-- AC -->
            <svg v-else-if="service.icon === 'ac'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <path d="M12 2v8l4-4"/>
              <path d="M12 10l-4-4"/>
              <path d="M20 12h-8l4 4"/>
              <path d="M12 12l4-4"/>
              <path d="M4 12h8l-4 4"/>
              <path d="M12 12l-4-4"/>
              <path d="M12 22v-8l4 4"/>
              <path d="M12 14l-4 4"/>
            </svg>
            <!-- Diagnostic -->
            <svg v-else-if="service.icon === 'diagnostic'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <rect x="2" y="3" width="20" height="14" rx="2"/>
              <line x1="8" y1="21" x2="16" y2="21"/>
              <line x1="12" y1="17" x2="12" y2="21"/>
              <polyline points="6 8 10 12 14 7 18 11"/>
            </svg>
            <!-- Electrical -->
            <svg v-else-if="service.icon === 'electrical'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/>
            </svg>
            <!-- Tires -->
            <svg v-else-if="service.icon === 'tires'" class="w-7 h-7 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="10"/>
              <circle cx="12" cy="12" r="6"/>
              <circle cx="12" cy="12" r="2"/>
            </svg>
          </div>

          <!-- Title -->
          <h3 class="text-lg font-bold text-gray-900 mb-2">{{ service.title }}</h3>

          <!-- Description -->
          <p class="text-sm text-text-light leading-relaxed m-0">{{ service.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
