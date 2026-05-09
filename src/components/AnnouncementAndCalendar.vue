<!-- components/AnnouncementAndCalendar.vue -->
<template>
  <section class="py-24 bg-slate-50">
    <div class="max-w-7xl mx-auto px-4 md:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
        
        <!-- Announcements -->
        <div class="lg:col-span-7">
          <div class="flex items-center gap-3 mb-8">
            <div class="bg-red-700 p-2 rounded-lg text-white">
              <Bell size="24" />
            </div>
            <h2 class="text-3xl font-extrabold text-slate-900 uppercase">Announcements</h2>
          </div>
          
          <div class="space-y-6">
            <div 
              v-for="(item, i) in announcements" 
              :key="i" 
              :class="[
                'p-6 rounded-2xl border transition-all',
                item.active ? 'bg-white shadow-xl border-red-100' : 'bg-transparent border-slate-200'
              ]"
            >
              <div class="flex justify-between items-start mb-3">
                <h3 class="text-lg font-bold text-slate-900 leading-tight">{{ item.title }}</h3>
                <span :class="[
                  'text-[10px] font-bold px-2 py-1 rounded-md uppercase',
                  item.active ? 'bg-red-100 text-red-700' : 'bg-slate-200 text-slate-500'
                ]">
                  {{ item.active ? 'Important' : 'Update' }}
                </span>
              </div>
              <p class="text-sm font-semibold text-red-700 mb-2">{{ item.date }}</p>
              <p class="text-slate-500 text-sm">{{ item.desc }}</p>
            </div>
          </div>
        </div>

        <!-- Calendar -->
        <div class="lg:col-span-5">
          <div class="flex items-center justify-between mb-8">
            <div class="flex items-center gap-3">
              <div class="bg-slate-900 p-2 rounded-lg text-white">
                <CalendarIcon size="24" />
              </div>
              <h2 class="text-3xl font-extrabold text-slate-900 uppercase">School Calendar</h2>
            </div>
          </div>

          <div class="bg-white rounded-[2rem] shadow-2xl p-8 border border-slate-100">
            <div class="flex justify-between items-center mb-8">
              <h3 class="text-xl font-bold text-slate-900">April 2026</h3>
              <div class="flex gap-2">
                <button class="p-2 hover:bg-slate-100 rounded-lg transition-colors"><X size="16" class="rotate-45" /></button>
                <button class="p-2 hover:bg-slate-100 rounded-lg transition-colors"><X size="16" class="-rotate-45" /></button>
              </div>
            </div>

            <div class="grid grid-cols-7 gap-2 text-center mb-4">
              <span v-for="d in ['S', 'M', 'T', 'W', 'T', 'F', 'S']" :key="d" class="text-[10px] font-black text-slate-400 uppercase">{{ d }}</span>
            </div>
            
            <div class="grid grid-cols-7 gap-2 overflow-hidden">
              <button 
                v-for="day in 30" 
                :key="day"
                :class="[
                  'relative aspect-square rounded-xl flex items-center justify-center text-sm font-semibold transition-all',
                  day === 28 ? 'bg-red-700 text-white shadow-lg shadow-red-200 scale-110 z-10' : 'hover:bg-slate-50 text-slate-600'
                ]"
              >
                {{ day }}
                <span v-if="[6, 15, 20].includes(day) && day !== 28" class="absolute bottom-1 w-1 h-1 bg-red-400 rounded-full"></span>
              </button>
            </div>

            <div class="mt-8 space-y-4">
              <div v-for="(event, i) in calendarEvents" :key="i" class="flex items-center gap-4 group cursor-pointer">
                <div :class="['w-2 h-10 rounded-full group-hover:scale-y-110 transition-transform', event.color]"></div>
                <div>
                  <p class="text-xs font-bold text-slate-400 uppercase tracking-widest">{{ event.date }}</p>
                  <p class="text-sm font-bold text-slate-900">{{ event.title }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { Bell, Calendar as CalendarIcon, X } from 'lucide-vue-next'

const announcements = [
  { 
    title: "Enrollment Period for S.Y. 2026-2027", 
    date: "Started April 6, 2026", 
    desc: "Open for transactions Monday to Friday (8:00 AM - 5:00 PM) and Saturday (8:00 AM - 12:00 NN).",
    active: true 
  },
  { 
    title: "Regular Enrollment Schedule", 
    date: "May 4 to May 30, 2026", 
    desc: "Specific schedules for Nursery to Grade 12. Please check your assigned dates to avoid long queues." 
  },
  { 
    title: "Daily Reflection by School Director", 
    date: "Posted Daily", 
    desc: "Join Rev. Fr. Tirso A. Gliponeo for spiritual nourishment in our daily gospel reflections." 
  }
]

const calendarEvents = [
  { date: "Apr 06", title: "Enrollment Period Begins", color: "bg-red-700" },
  { date: "Apr 28", title: "Founders Day Celebration", color: "bg-yellow-400" }
]
</script>