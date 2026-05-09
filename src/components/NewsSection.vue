<!-- components/NewsSection.vue -->
<template>
  <section class="py-32 bg-white">
    <div class="max-w-7xl mx-auto px-4 md:px-8">
      <div class="flex justify-between items-end mb-12">
        <div>
          <h2 class="text-4xl font-extrabold text-slate-900 mb-2">News & Events</h2>
          <p class="text-slate-500">Stay updated with our latest activities and achievements</p>
        </div>
        <button class="hidden md:flex items-center gap-2 text-red-700 font-bold hover:gap-3 transition-all">
          View All News <ArrowRight size="18" />
        </button>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div 
          v-for="(item, i) in news" 
          :key="i"
          v-motion
          :hover="{ y: -10 }"
          class="group cursor-pointer"
        >
          <div class="relative aspect-[4/3] rounded-3xl overflow-hidden mb-6">
            <img :src="item.img" :alt="item.title" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" referrerpolicy="no-referrer" />
            <div class="absolute top-4 left-4">
              <span class="bg-white/90 backdrop-blur px-3 py-1 rounded-full text-[10px] font-bold uppercase tracking-wider text-red-700">
                {{ item.category }}
              </span>
            </div>
          </div>
          <p class="text-xs font-bold text-red-600 mb-2 uppercase tracking-widest">{{ item.date }}</p>
          <h3 class="text-xl font-bold text-slate-900 group-hover:text-red-700 transition-colors mb-3 leading-tight">
            {{ item.title }}
          </h3>
          <p class="text-slate-500 text-sm line-clamp-2">
            Join our community as we celebrate academic success, sportsmanship, and our mission programs...
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ArrowRight } from 'lucide-vue-next'

const news = [
  {
    title: "Senior High Graduation 2026",
    date: "May 20, 2026",
    category: "Academic",
    img: "https://images.unsplash.com/photo-1523050854058-8df90110c9f1?auto=format&fit=crop&q=80&w=600"
  },
  {
    title: "Inter-school Sports Festival",
    date: "June 05, 2026",
    category: "Sports",
    img: "https://images.unsplash.com/photo-1544648100-302efd974411?auto=format&fit=crop&q=80&w=600"
  },
  {
    title: "Community Outreach Program",
    date: "April 15, 2026",
    category: "Mission",
    img: "https://images.unsplash.com/photo-1509062522246-3755977927d7?auto=format&fit=crop&q=80&w=600"
  }
]
</script>