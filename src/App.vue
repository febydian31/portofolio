<script setup lang="ts">
import Navbar from './components/layout/Navbar.vue'
import Hero from './components/sections/Hero.vue'
import About from './components/sections/About.vue'
import Projects from './components/sections/Projects.vue'
import Contact from './components/sections/Contact.vue'
</script>

<template>
  <div class="min-h-screen bg-background text-foreground font-sans selection:bg-primary selection:text-primary-foreground">
    <main class="max-w-2xl mx-auto px-6 py-12 md:py-24 flex flex-col gap-16 md:gap-24 relative">
      <Hero />
      <About />
      <Projects />
      <Contact />
      
      <!-- Placeholder for Floating Dock -->
      <Navbar /> 
    </main>
  </div>
</template>

<style>
html {
  scroll-behavior: smooth;
}
</style>
