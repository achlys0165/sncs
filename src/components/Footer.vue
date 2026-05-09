<!-- components/Footer.vue -->
<template>
  <footer class="bg-slate-900 text-white pt-24 pb-12">
    <div class="max-w-7xl mx-auto px-4 md:px-8">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-12 mb-16">
        <div class="col-span-1 md:col-span-1">
          <div class="flex items-center gap-3 mb-6">
            <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-red-700 font-bold text-xl">SN</div>
            <span class="font-display font-bold text-xl uppercase tracking-tighter">Sto. Niño Website</span>
          </div>
          <p class="text-slate-400 text-sm leading-relaxed mb-6">
            Empowering students through holistic education and spiritual growth since 1985.
          </p>
          <div class="flex gap-4">
            <a href="#" class="p-2 bg-slate-800 hover:bg-red-700 rounded-full transition-colors"><Facebook size="18" /></a>
            <a href="#" class="p-2 bg-slate-800 hover:bg-red-700 rounded-full transition-colors"><Youtube size="18" /></a>
            <a href="#" class="p-2 bg-slate-800 hover:bg-red-700 rounded-full transition-colors"><Instagram size="18" /></a>
          </div>
        </div>

        <div>
          <h4 class="font-bold text-white mb-6 uppercase tracking-widest text-sm">Quick Links</h4>
          <ul class="space-y-4 text-sm text-slate-400">
            <li><a href="#" class="hover:text-red-400 transition-colors">School History</a></li>
            <li><a href="#" class="hover:text-red-400 transition-colors">Vision & Mission</a></li>
            <li><a href="#" class="hover:text-red-400 transition-colors">Admission Policy</a></li>
            <li><a href="#" class="hover:text-red-400 transition-colors">Academic Calendar</a></li>
          </ul>
        </div>

        <div>
          <h4 class="font-bold text-white mb-6 uppercase tracking-widest text-sm">Portals</h4>
          <ul class="space-y-4 text-sm text-slate-400">
            <li><a href="#" class="hover:text-red-400 transition-colors">Student Portal</a></li>
            <li><a href="#" class="hover:text-red-400 transition-colors">Faculty Login</a></li>
            <li><a href="#" class="hover:text-red-400 transition-colors">Parent Connect</a></li>
            <li><a href="#" class="hover:text-red-400 transition-colors">E-Library</a></li>
          </ul>
        </div>

        <div>
          <h4 class="font-bold text-white mb-6 uppercase tracking-widest text-sm">Contact Us</h4>
          <ul class="space-y-4 text-sm text-slate-400">
            <li class="flex items-start gap-3">
              <MapPin size="18" class="text-red-500 mt-1 shrink-0" />
              <span>Signal Village, Taguig City, Philippines</span>
            </li>
            <li class="flex items-center gap-3">
              <Phone size="18" class="text-red-500 shrink-0" />
              <span>+63 (2) 8837 0000</span>
            </li>
            <li class="flex items-center gap-3">
              <Mail size="18" class="text-red-500 shrink-0" />
              <span>info@stonino.edu.ph</span>
            </li>
          </ul>
        </div>
      </div>

      <div class="pt-8 border-t border-slate-800 flex flex-col md:flex-row justify-between items-center gap-4">
        <p class="text-slate-500 text-xs text-center md:text-left">
          © 2026 Sto. Niño Catholic School, Inc. All rights reserved.
        </p>
        <div class="flex gap-8 text-[10px] uppercase font-bold tracking-widest text-slate-500">
          <a href="#" class="hover:text-white transition-colors">Privacy Policy</a>
          <a href="#" class="hover:text-white transition-colors">Terms of Service</a>
          <a href="#" class="hover:text-white transition-colors">Cookie Policy</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { MapPin, Phone, Mail, Facebook, Youtube, Instagram } from 'lucide-vue-next'
</script>