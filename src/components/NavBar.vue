<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { phone } from "../info";

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navLinks = [
  { label: 'Inicio', href: '#inicio' },
  { label: 'Nosotros', href: '#nosotros' },
  { label: 'Servicios', href: '#servicios' },
  { label: 'Contacto', href: '#contacto' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav
    id="navbar"
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
    :class="isScrolled
      ? 'bg-white/97 backdrop-blur-lg shadow-[0_2px_20px_rgba(0,0,0,0.08)]'
      : 'bg-white/95'"
  >
    <div
      class="max-w-[1300px] mx-auto flex items-center justify-between transition-all duration-300"
      :class="isScrolled ? 'px-6 py-4' : 'px-6 py-5'"
    >
      <!-- Logo -->
      <a href="#inicio" class="flex items-center gap-2.5 no-underline text-gray-900" @click="closeMobileMenu">
        <svg class="w-9 h-9 text-accent" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>
        </svg>
        <div class="flex flex-col leading-tight">
          <span class="text-2xl font-extrabold tracking-wide text-gray-900">GALAVIZ</span>
          <span class="text-[13px] font-semibold tracking-widest text-text-light uppercase">AUTOMOTRIZ</span>
        </div>
      </a>

      <!-- Desktop Nav Links -->
      <ul class="hidden md:flex list-none gap-8 m-0 p-0">
        <li v-for="link in navLinks" :key="link.href">
          <a
            :href="link.href"
            class="font-medium text-text-main no-underline relative py-1
                   hover:text-accent transition-colors duration-200
                   after:content-[''] after:absolute after:bottom-[-2px] after:left-0 after:w-0 after:h-0.5
                   after:bg-accent after:rounded-sm after:transition-all after:duration-300
                   hover:after:w-full"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>

      <!-- CTA Button -->
      <a
        :href="`tel:${phone.number}`"
        class="hidden md:inline-flex items-center gap-2.5 bg-accent text-white
               px-5 py-2.5 rounded-lg text-sm font-semibold no-underline
               hover:bg-accent-hover transition-all duration-200"
      >
        <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
        </svg>
        <span class="text-[15px]">{{ phone.display }}</span>
      </a>

      <!-- Mobile Hamburger -->
      <button
        class="flex md:hidden flex-col justify-center gap-[5px] bg-transparent border-none cursor-pointer p-2 z-[1010]"
        @click="toggleMobileMenu"
        aria-label="Abrir menú"
      >
        <span
          class="block w-6 h-0.5 bg-gray-900 rounded-sm transition-all duration-300"
          :class="isMobileMenuOpen ? 'rotate-45 translate-y-[7px]' : ''"
        ></span>
        <span
          class="block w-6 h-0.5 bg-gray-900 rounded-sm transition-all duration-300"
          :class="isMobileMenuOpen ? 'opacity-0' : ''"
        ></span>
        <span
          class="block w-6 h-0.5 bg-gray-900 rounded-sm transition-all duration-300"
          :class="isMobileMenuOpen ? '-rotate-45 -translate-y-[7px]' : ''"
        ></span>
      </button>
    </div>

    <!-- Mobile Drawer -->
    <div
      class="fixed top-0 w-[280px] h-screen bg-white shadow-[-4px_0_30px_rgba(0,0,0,0.1)]
             z-[1005] flex flex-col pt-20 px-8 pb-8 transition-all duration-350
             ease-[cubic-bezier(0.4,0,0.2,1)]"
      :class="isMobileMenuOpen ? 'right-0' : '-right-full'"
    >
      <ul class="list-none m-0 p-0 flex flex-col gap-1">
        <li v-for="link in navLinks" :key="link.href">
          <a
            :href="link.href"
            class="block text-base font-medium text-text-main no-underline py-3.5 px-3
                   rounded-lg hover:bg-bg-alt hover:text-accent transition-all duration-200"
            @click="closeMobileMenu"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>
      <a
        href="tel:+526141234567"
        class="flex items-center justify-center gap-2 bg-accent text-white
               py-3.5 px-6 rounded-lg text-base font-semibold no-underline mt-6
               hover:bg-accent-hover transition-colors duration-200"
        @click="closeMobileMenu"
      >
        <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.362 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.338 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/>
        </svg>
        <span>(614) 123-4567</span>
      </a>
    </div>

    <!-- Overlay -->
    <div
      v-if="isMobileMenuOpen"
      class="fixed inset-0 bg-black/40 z-[1004]"
      @click="closeMobileMenu"
    ></div>
  </nav>
</template>
