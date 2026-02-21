<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Mail } from 'lucide-vue-next'
</script>

<template>
  <section id="contact" class="w-full flex flex-col items-center justify-center gap-6 py-12 mb-20 text-center">
    <div class="space-y-3">
      <h2 
        class="text-3xl md:text-5xl font-bold tracking-tighter"
        v-motion :initial="{ opacity: 0, y: 20 }" :visibleOnce="{ opacity: 1, y: 0, transition: { duration: 600 } }"
      >
        Get in Touch
      </h2>
      <p 
        class="text-base text-muted-foreground leading-relaxed max-w-md mx-auto"
        v-motion :initial="{ opacity: 0, y: 20 }" :visibleOnce="{ opacity: 1, y: 0, transition: { delay: 150, duration: 600 } }"
      >
        Want to chat? Just shoot me an dm with a direct question on email and I'll respond whenever I can.
      </p>
    </div>
    
    <Button 
      class="rounded-full shadow-none bg-primary text-primary-foreground hover:bg-primary/90 mt-2" 
      as-child
      v-motion :initial="{ opacity: 0, scale: 0.9 }" :visibleOnce="{ opacity: 1, scale: 1, transition: { delay: 300, duration: 600, type: 'spring', stiffness: 100 } }"
    >
      <a href="mailto:contact@febydian.com">
        <Mail class="w-4 h-4 mr-2" /> Contact Me
      </a>
    </Button>
  </section>
</template>
