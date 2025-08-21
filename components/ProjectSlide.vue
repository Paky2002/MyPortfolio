<template>
  <div class="relative w-full bg-black overflow-hidden">
    <!-- Grid di sfondo -->
    <div class="absolute inset-0">
      <svg class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern :id="`projectGrid-${slideId}`" width="30" height="30" patternUnits="userSpaceOnUse">
            <line x1="0" y1="0" x2="0" y2="30" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.1"/>
            <line x1="0" y1="0" x2="30" y2="0" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.1"/>
          </pattern>
          <pattern :id="`headerHatch-${slideId}`" patternUnits="userSpaceOnUse" width="6" height="6">
            <path d="M0,6 L6,0" stroke="rgb(107 114 128)" stroke-width="0.4" opacity="0.2"/>
          </pattern>
          <marker :id="`projectArrow-${slideId}`" markerWidth="6" markerHeight="4" refX="5" refY="2" orient="auto" fill="rgb(107 114 128)">
            <polygon points="0 0, 6 2, 0 4" opacity="0.6"/>
          </marker>
        </defs>
        <rect width="100%" height="100%" :fill="`url(#projectGrid-${slideId})`"/>
        
        <!-- Elementi tecnici -->
        <line x1="0" y1="60" x2="100%" y2="60" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.4"/>
        <line x1="0" y1="calc(100% - 60px)" x2="100%" y2="calc(100% - 60px)" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.4"/>
        <line x1="55%" y1="60" x2="55%" y2="calc(100% - 60px)" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.4"/>
        
        <!-- Pattern hatch -->
        <rect x="0" y="0" width="100%" height="60" :fill="`url(#headerHatch-${slideId})`"/>
        <rect x="0" y="calc(100% - 60px)" width="100%" height="60" :fill="`url(#headerHatch-${slideId})`"/>
        
        <!-- Annotazioni tecniche -->
        <text x="20" y="45" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7">
          PROJECT.{{ String(projectIndex + 1).padStart(2, '0') }}
        </text>
        <text x="calc(55% + 10px)" y="45" fill="rgb(107 114 128)" font-size="6" font-family="monospace" opacity="0.6">
          PREVIEW
        </text>
        
        <!-- Freccia di connessione -->
        <line 
          x1="calc(55% - 30px)" y1="50%" x2="calc(55% - 10px)" y2="50%" 
          stroke="rgb(107 114 128)" stroke-width="0.8" 
          :marker-end="`url(#projectArrow-${slideId})`" 
          opacity="0.5"
        />
      </svg>
    </div>

    <div class="relative z-10 grid grid-cols-12 min-h-[600px]">
      
      <!-- Colonna sinistra - Contenuto -->
      <div class="col-span-7 flex items-center px-12 py-16">
        <div class="space-y-8 w-full">
          
          <!-- Header del progetto -->
          <div class="space-y-4">
            <div class="flex items-center gap-3">
              <div class="flex items-center gap-1">
                <div class="w-1.5 h-1.5 bg-green-500 rounded-full"></div>
                <div class="w-1.5 h-1.5 bg-yellow-500 rounded-full"></div>
                <div class="w-1.5 h-1.5 bg-red-500 rounded-full"></div>
              </div>
              <span class="text-gray-500 text-xs font-mono tracking-wider">
                {{ project.category.toUpperCase() }}_PROJECT
              </span>
            </div>
            
            <h3 class="text-4xl font-light text-white leading-tight">
              {{ project.title.main }}
              <span class="block text-red-500 font-normal">{{ project.title.accent }}</span>
            </h3>
            
            <p class="text-gray-400 text-lg font-mono">
              {{ project.subtitle }}
            </p>
          </div>

          <!-- Descrizione -->
          <div class="space-y-3">
            <div class="flex items-center gap-3">
              <span class="text-gray-500 text-sm font-mono tracking-wide">OVERVIEW:</span>
              <div class="flex-1 h-px bg-gray-700/50"></div>
            </div>
            <p class="text-gray-300 leading-relaxed text-lg" v-html="project.description"></p>
          </div>

          <!-- Tech Stack -->
          <div class="space-y-3">
            <div class="flex items-center gap-3">
              <span class="text-gray-500 text-sm font-mono tracking-wide">TECH_STACK:</span>
              <div class="flex-1 h-px bg-gray-700/50"></div>
            </div>
            <div class="flex flex-wrap gap-2">
              <span 
                v-for="(tech, index) in project.techStack" 
                :key="tech"
                class="px-3 py-1.5 text-xs font-mono bg-gray-800/60 border border-gray-700/50 text-gray-300 rounded"
              >
                {{ String(index + 1).padStart(2, '0') }}.{{ tech }}
              </span>
            </div>
          </div>

          <!-- Links e status -->
          <div class="flex items-center justify-between pt-4">
            <div class="flex items-center gap-6">
              <a 
                v-for="link in project.links" 
                :key="link.label"
                :href="link.url" 
                target="_blank"
                class="flex items-center gap-2 text-sm font-mono text-gray-400 hover:text-white transition-colors"
              >
                <div 
                  class="w-2 h-2 rounded-full"
                  :class="getLinkColorClass(link.type)"
                ></div>
                <span>{{ link.label.toUpperCase() }}</span>
              </a>
            </div>
            
            <div class="text-gray-600 text-xs font-mono">
              COMPLETED: {{ project.completedDate }}
            </div>
          </div>

        </div>
      </div>

      <!-- Colonna destra - Screenshot -->
      <div class="col-span-5 flex items-center justify-center px-8 py-16">
        <div class="relative w-full max-w-lg">
          
          <!-- Cornice tecnica -->
          <div class="relative bg-gray-900/50 border border-gray-600/30 rounded-lg overflow-hidden">
            <!-- Tacche angolari -->
            <div class="absolute -top-1 -left-1 w-4 h-4 border-l-2 border-t-2 border-gray-400/60 pointer-events-none z-20"></div>
            <div class="absolute -top-1 -right-1 w-4 h-4 border-r-2 border-t-2 border-gray-400/60 pointer-events-none z-20"></div>
            <div class="absolute -bottom-1 -left-1 w-4 h-4 border-l-2 border-b-2 border-gray-400/60 pointer-events-none z-20"></div>
            <div class="absolute -bottom-1 -right-1 w-4 h-4 border-r-2 border-b-2 border-gray-400/60 pointer-events-none z-20"></div>
            
            <!-- Immagine del progetto -->
            <div class="aspect-[4/3] bg-gradient-to-br from-gray-800 to-gray-900 flex items-center justify-center">
              <img 
                v-if="project.image" 
                :src="project.image" 
                :alt="project.title.main"
                class="w-full h-full object-cover"
              />
              <!-- Placeholder se non c'è immagine -->
              <div v-else class="text-center space-y-4">
                <div class="w-20 h-20 mx-auto bg-gray-700 rounded-xl flex items-center justify-center">
                  <component :is="getIconComponent(project.category)" class="w-10 h-10 text-gray-500" />
                </div>
                <div class="space-y-1">
                  <p class="text-gray-500 text-sm font-mono">{{ project.imagePlaceholder || 'PROJECT_PREVIEW.PNG' }}</p>
                  <p class="text-gray-600 text-xs font-mono">{{ project.imageSpecs || '1920x1440px' }}</p>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Etichetta tecnica -->
          <div class="absolute -bottom-6 left-0 flex items-center gap-2">
            <div class="w-2 h-2 border border-gray-500/60 bg-gray-500/20"></div>
            <span class="text-gray-500 text-xs font-mono">
              IMG_{{ String(projectIndex + 1).padStart(3, '0') }} • {{ project.imageSpecs || '4:3 RATIO' }}
            </span>
          </div>
          
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

// Props
const props = defineProps({
  project: {
    type: Object,
    required: true
  },
  projectIndex: {
    type: Number,
    required: true
  }
})

// ID unico per evitare conflitti SVG
const slideId = computed(() => `slide-${props.projectIndex}`)

// Helper per i colori dei link
const getLinkColorClass = (type) => {
  const colors = {
    demo: 'bg-green-500 animate-ping',
    github: 'bg-blue-500',
    docs: 'bg-orange-500',
    website: 'bg-purple-500'
  }
  return colors[type] || 'bg-gray-500'
}

// Helper per le icone
const getIconComponent = (category) => {
  // Qui puoi importare e restituire diverse icone SVG in base alla categoria
  // Per ora uso una generica
  return 'svg'
}
</script>

<style scoped>
/* Stili specifici del componente se necessari */
</style>