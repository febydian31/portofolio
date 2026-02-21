<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { FileText } from 'lucide-vue-next'
</script>

<template>
  <section id="hero" class="w-full flex items-center pt-8 md:pt-12">
    <div class="w-full flex flex-col md:flex-row gap-6 md:gap-8 items-start md:items-center justify-between">
      
      <!-- Text Content (Left Side) -->
      <div class="space-y-4 flex-1 order-2 md:order-1">
        <h1 
          class="text-3xl md:text-5xl font-bold tracking-tighter"
          v-motion
          :initial="{ opacity: 0, y: 20 }"
          :enter="{ opacity: 1, y: 0, transition: { duration: 800, type: 'spring', stiffness: 50 } }"
        >
          Hi, I'm Feby 👋
        </h1>
        
        <p 
          class="max-w-[450px] text-base text-muted-foreground leading-relaxed"
          v-motion
          :initial="{ opacity: 0, y: 20 }"
          :enter="{ opacity: 1, y: 0, transition: { delay: 150, duration: 800, type: 'spring', stiffness: 50 } }"
        >
          Frontend Developer crafting accessible, performant, and beautiful digital experiences with modern web technologies.
        </p>
        
        <div 
          class="pt-2"
          v-motion
          :initial="{ opacity: 0, y: 20 }"
          :enter="{ opacity: 1, y: 0, transition: { delay: 300, duration: 800, type: 'spring', stiffness: 50 } }"
        >
          <Button variant="outline" size="sm" class="rounded-full shadow-none font-medium text-xs" as-child>
            <a href="https://drive.google.com/file/d/1AgWcsDiKKAgjYotelPDy11RfNKLO3R1k/view?usp=drive_link" target="_blank" rel="noopener noreferrer">
              <FileText class="w-3.5 h-3.5 mr-2" /> Resume
            </a>
          </Button>
        </div>
      </div>

      <!-- Small Circular Avatar (Right Side) -->
      <div 
        class="order-1 md:order-2 shrink-0"
        v-motion
        :initial="{ opacity: 0, scale: 0.8, rotate: -10 }"
        :enter="{ opacity: 1, scale: 1, rotate: 0, transition: { delay: 450, duration: 1000, type: 'spring', stiffness: 50 } }"
      >
        <div class="relative w-24 h-24 md:w-32 md:h-32">
          <img 
            src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=250&auto=format&fit=crop" 
            alt="Profile" 
            class="w-full h-full object-cover rounded-full border border-border bg-muted shadow-sm"
          />
        </div>
      </div>

    </div>
  </section>
</template>
