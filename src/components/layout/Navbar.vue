<script setup lang="ts">
import { Home, User, Briefcase, Mail } from 'lucide-vue-next'
import { Tooltip, TooltipContent, TooltipProvider, TooltipTrigger } from '@/components/ui/tooltip'
import { Button } from '@/components/ui/button'

const dockItems = [
  { name: 'Home', href: '#hero', icon: Home },
  { name: 'About', href: '#about', icon: User },
  { name: 'Projects', href: '#projects', icon: Briefcase },
  { name: 'Contact', href: '#contact', icon: Mail },
]
</script>

<template>
  <div class="fixed inset-x-0 bottom-6 z-50 flex justify-center pointer-events-none">
    <div class="flex items-center gap-2 rounded-full border bg-background/80 px-2 py-2 shadow-lg backdrop-blur supports-[backdrop-filter]:bg-background/60 pointer-events-auto">
      <TooltipProvider v-for="item in dockItems" :key="item.name">
        <Tooltip :delayDuration="0">
          <TooltipTrigger as-child>
            <Button variant="ghost" size="icon" as-child class="rounded-full w-10 h-10 md:w-12 md:h-12 hover:bg-muted text-muted-foreground hover:text-foreground transition-all">
              <a :href="item.href" :aria-label="item.name">
                <component :is="item.icon" class="w-5 h-5 md:w-6 md:h-6" />
              </a>
            </Button>
          </TooltipTrigger>
          <TooltipContent side="top" class="mb-2 text-[10px] px-2 py-1 font-semibold rounded-md">
            {{ item.name }}
          </TooltipContent>
        </Tooltip>
      </TooltipProvider>
    </div>
  </div>
</template>
