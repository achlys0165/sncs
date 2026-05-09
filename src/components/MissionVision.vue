<!-- components/MissionVision.vue -->
<template>
  <section class="py-24 bg-white relative overflow-hidden">
    <div class="absolute top-0 right-0 w-96 h-96 bg-red-50 rounded-full blur-3xl opacity-50 -translate-y-1/2 translate-x-1/2"></div>
    <div class="max-w-7xl mx-auto px-4 md:px-8 relative z-10">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
        <div class="relative">
          <div class="aspect-square rounded-[3rem] overflow-hidden shadow-2xl relative z-10">
            <img 
              src="https://images.unsplash.com/photo-1544648100-302efd974411?auto=format&fit=crop&q=80&w=800" 
              alt="Students" 
              class="w-full h-full object-cover"
              referrerpolicy="no-referrer"
            />
          </div>
          <div class="absolute -bottom-6 -right-6 w-48 h-48 bg-yellow-400 rounded-3xl -z-10 animate-pulse"></div>
          <div class="absolute -top-6 -left-6 w-32 h-32 border-4 border-red-700 rounded-[2rem] -z-10"></div>
        </div>
        <div>
          <h2 class="text-4xl font-extrabold text-slate-900 mb-8 leading-tight">
            Guided by Faith, <br />Driven by <span class="text-red-700 underline decoration-yellow-400 underline-offset-8">Excellence</span>
          </h2>
          <div class="space-y-8">
            <div>
              <h3 class="text-xl font-bold text-red-700 mb-3 uppercase tracking-wider">Our Vision</h3>
              <p class="text-slate-600 leading-relaxed">
                To be a premier Catholic educational institution that nurtures Christ-centered, academically excellent, 
                socially responsible, and globally competitive individuals.
              </p>
            </div>
            <div>
              <h3 class="text-xl font-bold text-red-700 mb-3 uppercase tracking-wider">Our Mission</h3>
              <p class="text-slate-600 leading-relaxed">
                We commit ourselves to provide quality education inspired by the teachings of Jesus Christ, 
                fostering a community of learners dedicated to service and spiritual growth.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>