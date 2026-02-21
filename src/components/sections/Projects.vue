<script setup lang="ts">
import { Card, CardHeader, CardTitle, CardDescription, CardContent, CardFooter } from '@/components/ui/card'
import { Badge } from '@/components/ui/badge'
import { Button } from '@/components/ui/button'
import { ExternalLink, Github } from 'lucide-vue-next'

const projects = [
  {
    title: "E-Commerce Platform",
    date: "Jan 2024 - Present",
    description: "A modern, high-performance e-commerce platform built with Vue 3, Nuxt, and Tailwind CSS. Features an intuitive admin dashboard and seamless checkout experience.",
    tech: ["Vue 3", "Nuxt", "Tailwind CSS", "Pinia"],
    link: "https://example.com",
    github: "https://github.com",
    image: "https://images.unsplash.com/photo-1557821552-17105176677c?q=80&w=1000&auto=format&fit=crop"
  },
  {
    title: "Task Management App",
    date: "Sep 2023 - Dec 2023",
    description: "A collaborative task management tool with real-time updates. Designed with a focus on minimalism and productivity.",
    tech: ["Vue 3", "TypeScript", "Firebase", "shadcn-vue"],
    link: "https://example.com",
    github: "https://github.com",
    image: "https://images.unsplash.com/photo-1517849845537-4d257902454a?q=80&w=1000&auto=format&fit=crop"
  },
  {
    title: "Portfolio Template",
    date: "Jul 2023 - Aug 2023",
    description: "An elegant, customizable portfolio template for developers and designers. Features dark mode, responsive design, and smooth animations.",
    tech: ["Vue 3", "Vite", "Tailwind CSS"],
    link: "https://example.com",
    github: "https://github.com",
    image: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=1000&auto=format&fit=crop"
  }
]
</script>

<template>
  <section id="projects" class="w-full flex flex-col gap-6" v-motion :initial="{ opacity: 0, y: 20 }" :visibleOnce="{ opacity: 1, y: 0, transition: { duration: 800 } }">
    <div class="flex flex-col space-y-1.5" v-motion :initial="{ opacity: 0, x: -20 }" :visibleOnce="{ opacity: 1, x: 0, transition: { delay: 100, duration: 600 } }">
      <h2 class="text-xl font-bold tracking-tighter">Projects</h2>
      <p class="text-sm text-muted-foreground">A selection of my recent work.</p>
    </div>
    
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
      <Card 
        v-for="(project, i) in projects" 
        :key="project.title" 
        class="flex flex-col h-full overflow-hidden border bg-card transition-colors hover:bg-accent/50"
        v-motion
        :initial="{ opacity: 0, y: 30, scale: 0.95 }"
        :visibleOnce="{ opacity: 1, y: 0, scale: 1, transition: { delay: 300 + (i * 150), duration: 600, type: 'spring', stiffness: 50 } }"
      >
        <div class="w-full h-40 overflow-hidden bg-muted">
          <img 
            :src="project.image" 
            :alt="project.title" 
            class="w-full h-full object-cover transition-transform duration-500 hover:scale-105"
          />
        </div>

        <CardHeader class="p-4 pb-2">
          <div class="flex items-center justify-between gap-2">
            <CardTitle class="text-base font-semibold">{{ project.title }}</CardTitle>
            <span class="text-xs text-muted-foreground whitespace-nowrap">{{ project.date }}</span>
          </div>
          <CardDescription class="text-xs mt-1">{{ project.description }}</CardDescription>
        </CardHeader>

        <CardContent class="p-4 pt-0 flex-1">
          <div class="flex flex-wrap gap-1 mt-2">
            <Badge v-for="t in project.tech" :key="t" variant="secondary" class="text-[10px] py-0 px-2 h-5 font-normal bg-muted">{{ t }}</Badge>
          </div>
        </CardContent>

        <CardFooter class="p-4 pt-0 flex gap-2">
          <Button variant="outline" size="sm" as-child class="h-8 text-xs font-normal">
            <a :href="project.github" target="_blank"><Github class="w-3 h-3 mr-1.5"/> Source</a>
          </Button>
          <Button variant="default" size="sm" as-child class="h-8 text-xs font-normal">
            <a :href="project.link" target="_blank"><ExternalLink class="w-3 h-3 mr-1.5"/> Website</a>
          </Button>
        </CardFooter>
      </Card>
    </div>
  </section>
</template>
