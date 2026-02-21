<script setup lang="ts">
import { Badge } from '@/components/ui/badge'
import { Server } from 'lucide-vue-next'

const skills = [
  { name: "Vue.js", icon: "https://cdn.simpleicons.org/vuedotjs/4FC08D", isImage: true },
  { name: "Nuxt", icon: "https://cdn.simpleicons.org/nuxtdotjs/00C58E", isImage: true },
  { name: "TypeScript", icon: "https://cdn.simpleicons.org/typescript/3178C6", isImage: true },
  { name: "JavaScript", icon: "https://cdn.simpleicons.org/javascript/F7DF1E", isImage: true },
  { name: "Tailwind CSS", icon: "https://cdn.simpleicons.org/tailwindcss/06B6D4", isImage: true },
  { name: "HTML5", icon: "https://cdn.simpleicons.org/html5/E34F26", isImage: true },
  { name: "CSS3", icon: "https://cdn.simpleicons.org/css3/1572B6", isImage: true },
  { name: "Git", icon: "https://cdn.simpleicons.org/git/F05032", isImage: true },
  { name: "Figma", icon: "https://cdn.simpleicons.org/figma/F24E1E", isImage: true },
  { name: "REST APIs", icon: Server, isImage: false },
  { name: "GraphQL", icon: "https://cdn.simpleicons.org/graphql/E10098", isImage: true }
]
</script>

<template>
  <section id="about" class="w-full flex flex-col gap-6" v-motion :initial="{ opacity: 0, y: 20 }" :visibleOnce="{ opacity: 1, y: 0, transition: { duration: 800 } }">
    <h2 class="text-xl font-bold tracking-tighter">About</h2>
    
    <div class="space-y-4 text-muted-foreground leading-relaxed text-base">
      <p>
        Hello! I'm a passionate frontend developer with a keen eye for minimalist design and a commitment to creating elegant, accessible user interfaces. I specialize in the Vue.js ecosystem.
      </p>
      <p>
        With a background in computer science and years of hands-on experience, I bridge the gap between design and engineering. I build software that not only looks beautiful but performs exceptionally well.
      </p>
    </div>

    <h2 class="text-xl font-bold tracking-tighter mt-4" v-motion :initial="{ opacity: 0 }" :visibleOnce="{ opacity: 1, transition: { delay: 200, duration: 800 } }">Skills</h2>
    <div class="flex flex-wrap gap-2">
      <Badge 
        v-for="(skill, i) in skills" 
        :key="skill.name" 
        variant="secondary" 
        class="text-xs font-normal py-1 pr-3 pl-2.5 bg-muted text-foreground hover:bg-muted/80 border-transparent rounded-md flex items-center gap-1.5"
        v-motion
        :initial="{ opacity: 0, scale: 0.8, y: 10 }"
        :visibleOnce="{ opacity: 1, scale: 1, y: 0, transition: { delay: 300 + (i * 50), duration: 400, type: 'spring', stiffness: 100 } }"
      >
        <img v-if="skill.isImage" :src="skill.icon as string" class="w-3.5 h-3.5" :alt="skill.name" />
        <component v-else :is="skill.icon" class="w-3.5 h-3.5 text-muted-foreground" />
        {{ skill.name }}
      </Badge>
    </div>
  </section>
</template>
