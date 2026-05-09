<!-- App.vue -->
<template>
  <div class="min-h-screen">
    <Navbar />
    <Hero />
    <MissionVision />
    <DailyReflection />
    <NewsSection />
    <AnnouncementAndCalendar />
    <Footer /> 
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import MissionVision from './components/MissionVision.vue'
import DailyReflection from './components/DailyReflection.vue'
import NewsSection from './components/NewsSection.vue'
import AnnouncementAndCalendar from './components/AnnouncementAndCalendar.vue'
import Footer from './components/Footer.vue'
</script>