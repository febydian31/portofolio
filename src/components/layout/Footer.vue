<script setup lang="ts">
import { Github, Mail } from 'lucide-vue-next'
</script>

<template>
  <footer class="border-t bg-muted/40 py-8 md:py-12 mt-20">
    <div class="container mx-auto px-4 flex flex-col md:flex-row items-center justify-between gap-4 text-center md:text-left text-sm text-muted-foreground">
      <p>&copy; {{ new Date().getFullYear() }} Feby Dian Maulana. All rights reserved.</p>
      
      <div class="flex items-center gap-4">
        <a href="https://github.com/febydian" target="_blank" class="hover:text-foreground transition-colors">
          <Github class="w-5 h-5"/>
        </a>
        <a href="mailto:contact@febydian.com" class="hover:text-foreground transition-colors">
          <Mail class="w-5 h-5"/>
        </a>
      </div>
    </div>
  </footer>
</template>
