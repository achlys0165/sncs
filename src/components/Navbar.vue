<!-- components/Navbar.vue -->
<template>
  <nav :class="[
    'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
    isScrolled ? 'bg-white/95 backdrop-blur-sm shadow-md py-3' : 'bg-transparent py-5'
  ]">
    <div class="max-w-7xl mx-auto px-4 md:px-8 flex justify-between items-center">
      <div class="flex items-center gap-3">
        <img src="/Logo.png" alt="School logo" class="w-10 h-10 object-cover rounded-full" />
        <div :class="['flex flex-col', isScrolled ? 'text-slate-900' : 'text-slate-900 md:text-white']">
          <span class="font-display font-bold leading-tight tracking-tight text-sm md:text-lg">Sto. Niño Catholic School, Inc.</span>
          <span class="text-[10px] md:text-xs opacity-80 uppercase tracking-widest font-medium">Established 1985</span>
        </div>
      </div>

      <!-- Desktop Menu -->
      <div class="hidden lg:flex items-center gap-8">
        <div v-for="item in navItems" :key="item.name" class="group relative">
          <a 
            :href="item.href" 
            :class="[
              'flex items-center gap-1 font-medium text-sm transition-colors',
              isScrolled ? 'text-slate-700 hover:text-red-700' : 'text-slate-700 lg:text-white lg:hover:text-red-200'
            ]"
          >
            {{ item.name }}
            <ChevronDown v-if="item.hasDropdown" size="14" class="group-hover:rotate-180 transition-transform" />
          </a>
          <div v-if="item.hasDropdown" class="absolute top-full left-0 mt-2 w-48 bg-white shadow-xl border border-slate-100 rounded-lg opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-200 transform translate-y-2 group-hover:translate-y-0 p-2">
            <a href="#" class="block px-4 py-2 text-sm text-slate-700 hover:bg-slate-50 hover:text-red-700 rounded-md">History</a>
            <a href="#" class="block px-4 py-2 text-sm text-slate-700 hover:bg-slate-50 hover:text-red-700 rounded-md">Vision & Mission</a>
            <a href="#" class="block px-4 py-2 text-sm text-slate-700 hover:bg-slate-50 hover:text-red-700 rounded-md">Faculty</a>
          </div>
        </div>
        <button :class="[
          'p-2 transition-colors',
          isScrolled ? 'text-slate-600 hover:bg-slate-100 rounded-full' : 'text-slate-600 lg:text-white lg:hover:bg-white/10 rounded-full'
        ]">
          <Search size="20" />
        </button>
      </div>

      <!-- Mobile Toggle -->
      <button class="lg:hidden p-2 text-slate-900" @click="isMobileMenuOpen = !isMobileMenuOpen">
        <X v-if="isMobileMenuOpen" size="24" />
        <Menu v-else size="24" />
      </button>
    </div>

    <!-- Mobile Menu -->
    <Transition
      enter-active-class="transition-all duration-200"
      enter-from-class="opacity-0 -translate-y-5"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-200"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-5"
    >
      <div v-show="isMobileMenuOpen" class="lg:hidden absolute top-full left-0 right-0 bg-white shadow-2xl border-t border-slate-100 p-4 flex flex-col gap-4">
        <a v-for="item in navItems" :key="item.name" :href="item.href" class="text-slate-700 font-medium py-2 px-4 hover:bg-slate-50 rounded-lg flex justify-between items-center">
          {{ item.name }}
          <ChevronDown v-if="item.hasDropdown" size="16" />
        </a>
        <div class="flex gap-4 p-4 items-center justify-center border-t border-slate-100">
          <Facebook class="text-blue-600" size="20" />
          <Youtube class="text-red-600" size="20" />
          <Instagram class="text-pink-600" size="20" />
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { ChevronDown, Menu, X, Search, Facebook, Youtube, Instagram } from 'lucide-vue-next'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navItems = [
  { name: 'Home', href: '#' },
  { name: 'About', href: '#', hasDropdown: true },
  { name: 'Registration', href: '#', hasDropdown: true },
  { name: 'Multimedia', href: '#', hasDropdown: true },
  { name: 'Downloadables', href: '#' },
  { name: 'Contacts', href: '#' },
  { name: 'Alumni', href: '#', hasDropdown: true },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>