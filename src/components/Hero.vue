<!-- components/Hero.vue -->
<template>
  <section class="relative h-[90vh] min-h-[600px] flex items-center mb-24 md:mb-32">
    <!-- Background with Grid Overlay -->
    <div class="absolute inset-0 bg-red-900 overflow-hidden">
      <img 
        src="https://images.unsplash.com/photo-1541339907198-e08756ebafe3?auto=format&fit=crop&q=80&w=2000" 
        alt="School Campus" 
        class="w-full h-full object-cover opacity-40"
        referrerpolicy="no-referrer"
      />
      <div class="absolute inset-0 modern-grid opacity-10"></div>
      <div class="absolute inset-0 bg-gradient-to-tr from-red-950 via-red-900/40 to-transparent"></div>
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 md:px-8 w-full">
      <div 
        v-motion
        :initial="{ opacity: 0, x: -50 }"
        :enter="{ opacity: 1, x: 0 }"
        :transition="{ duration: 0.8 }"
        class="max-w-2xl"
      >
        <div class="inline-flex items-center gap-2 bg-red-600/20 backdrop-blur-md border border-red-500/30 px-3 py-1 rounded-full text-red-200 text-xs font-semibold mb-6 uppercase tracking-wider">
          <span class="w-2 h-2 bg-red-500 rounded-full animate-pulse"></span>
          Enrollment for 2026-2027 is now open
        </div>
        <h1 class="text-5xl md:text-7xl font-extrabold text-white leading-[1.1] mb-6">
          Building a <span class="text-yellow-400">Foundation</span> for Lifelong Excellence
        </h1>
        <p class="text-lg md:text-xl text-white/80 mb-8 leading-relaxed">
          Sto. Niño Catholic School provides a holistic education rooted in Catholic values, 
          preparing students for a bright future in a changing world.
        </p>
        <div class="flex flex-wrap gap-4">
          <button class="bg-red-700 hover:bg-red-600 text-white px-8 py-4 rounded-full font-bold shadow-lg shadow-red-900/40 flex items-center gap-2 transition-all group">
            Apply Now <ArrowRight size="18" class="group-hover:translate-x-1 transition-transform" />
          </button>
          <button class="bg-white/10 hover:bg-white/20 backdrop-blur-md border border-white/30 text-white px-8 py-4 rounded-full font-bold transition-all">
            Explore Programs
          </button>
        </div>
      </div>
    </div>

    <!-- Floating Info Cards -->
    <div class="absolute bottom-0 left-0 right-0 transform translate-y-1/2 z-20 hidden md:block">
      <div class="max-w-7xl mx-auto px-8">
        <div class="grid grid-cols-3 gap-6">
          <div 
            v-for="(item, i) in infoCards" 
            :key="i"
            v-motion
            :initial="{ opacity: 0, y: 50 }"
            :enter="{ opacity: 1, y: 0 }"
            :transition="{ delay: 0.5 + (i * 0.1) }"
            class="bg-white p-6 rounded-2xl shadow-xl flex items-start gap-4 border border-slate-100 group hover:-translate-y-2 transition-all cursor-default"
          >
            <div class="bg-red-100 p-3 rounded-xl text-red-700 group-hover:bg-red-700 group-hover:text-white transition-colors">
              <component :is="item.icon" size="24" />
            </div>
            <div>
              <h3 class="text-lg font-bold text-slate-900 mb-1">{{ item.title }}</h3>
              <p class="text-sm text-slate-500 leading-snug">{{ item.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ArrowRight, CheckCircle2 } from 'lucide-vue-next'

const infoCards = [
  { title: "ESC & TLC", desc: "Participating School with government subsidies", icon: CheckCircle2 },
  { title: "PaDSS Member", desc: "Pasig Diocesan School System network", icon: CheckCircle2 },
  { title: "No Top Up", desc: "Zero additional fees for SHS voucher holders from public schools", icon: CheckCircle2 }
]
</script>