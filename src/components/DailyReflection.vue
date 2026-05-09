<!-- components/DailyReflection.vue -->
<template>
  <section class="py-24 bg-red-900 relative overflow-hidden">
    <div class="absolute inset-0 modern-grid opacity-5"></div>
    <div class="max-w-7xl mx-auto px-4 md:px-8 flex flex-col items-center text-center">
      <div 
        v-motion
        :initial="{ opacity: 0, scale: 0.9 }"
        :visible="{ opacity: 1, scale: 1 }"
        class="max-w-3xl glass-card rounded-[3rem] p-8 md:p-12 relative"
      >
        <div class="w-20 h-20 bg-red-700 rounded-full border-4 border-white shadow-xl flex items-center justify-center text-white mx-auto -mt-20 md:-mt-24 mb-8 overflow-hidden">
           <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&q=80&w=200" alt="Director" class="w-full h-full object-cover" referrerpolicy="no-referrer" />
        </div>
        <span class="text-xs font-bold text-red-700 uppercase tracking-widest mb-4 block">School Director's Daily Reflection</span>
        <h2 class="text-2xl md:text-3xl font-bold text-slate-900 mb-6 italic">
          "The image of the Good Shepherd in the Gospel refers to those who take care of the Christian community..."
        </h2>
        <p class="text-slate-600 mb-8 leading-relaxed max-w-2xl mx-auto">
          Each of us has the responsibility to take care of each other after Jesus' heart. 
          May we find strength in our community today.
        </p>
        <div class="pt-6 border-t border-slate-100 flex flex-col items-center">
          <p class="font-display font-bold text-slate-900">Rev. Fr. Tirso A. Gliponeo</p>
          <p class="text-xs text-slate-500 uppercase tracking-widest font-bold">School Director</p>
        </div>
      </div>
    </div>
  </section>
</template>