<template>
  <section class="relative w-full bg-black">
    
    <!-- Linea di separazione superiore -->
    <div class="relative w-full h-20 bg-black">
      <svg class="absolute inset-0 w-full h-full pointer-events-none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <!-- Pattern per la linea di separazione -->
          <pattern id="separatorHatch" patternUnits="userSpaceOnUse" width="10" height="10">
            <path d="M0,10 L10,0" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.3"/>
          </pattern>
          <marker id="separatorArrow" markerWidth="8" markerHeight="6" refX="7" refY="3" orient="auto" fill="rgb(107 114 128)">
            <polygon points="0 0, 8 3, 0 6" opacity="0.5"/>
          </marker>
        </defs>
        
        <!-- Linea principale di separazione -->
        <line x1="0" y1="50%" x2="100%" y2="50%" stroke="rgb(107 114 128)" stroke-width="2" stroke-dasharray="8,8" opacity="0.6"/>
        
        <!-- Area hatch sopra e sotto la linea -->
        <rect x="0" y="0" width="100%" height="30%" fill="url(#separatorHatch)" opacity="0.4"/>
        <rect x="0" y="70%" width="100%" height="30%" fill="url(#separatorHatch)" opacity="0.4"/>
        
        <!-- Annotazioni tecniche -->
        <text x="40" y="30" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7">SECTION_BREAK</text>
        <text x="calc(100% - 120px)" y="30" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7">LINE_02</text>
        
        <!-- Piccole frecce direzionali -->
        <line x1="20" y1="50%" x2="35" y2="50%" stroke="rgb(107 114 128)" stroke-width="1" marker-end="url(#separatorArrow)" opacity="0.4"/>
        <line x1="calc(100% - 35px)" y1="50%" x2="calc(100% - 20px)" y2="50%" stroke="rgb(107 114 128)" stroke-width="1" marker-end="url(#separatorArrow)" opacity="0.4"/>
        
        <!-- Coordinate di riferimento -->
        <circle cx="50%" cy="50%" r="2" fill="rgb(107 114 128)" opacity="0.4"/>
        <text x="calc(50% + 8px)" y="calc(50% + 4px)" fill="rgb(107 114 128)" font-size="6" font-family="monospace" opacity="0.6">CENTER</text>
      </svg>
    </div>

    <!-- Header della sezione elevato -->
    <div class="relative px-8 py-16 bg-gradient-to-b from-gray-900/20 to-black">
      <!-- Grid di sfondo per header -->
      <div class="absolute inset-0">
        <svg class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
          <defs>
            <pattern id="headerGrid" width="50" height="50" patternUnits="userSpaceOnUse">
              <line x1="0" y1="0" x2="0" y2="50" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.15"/>
              <line x1="0" y1="0" x2="50" y2="0" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.15"/>
              <!-- Punti di intersezione -->
              <circle cx="0" cy="0" r="0.5" fill="rgb(107 114 128)" opacity="0.2"/>
            </pattern>
            <pattern id="sectionHatch" patternUnits="userSpaceOnUse" width="12" height="12">
              <path d="M0,12 L12,0" stroke="rgb(107 114 128)" stroke-width="0.4" opacity="0.15"/>
            </pattern>
          </defs>
          <rect width="100%" height="100%" fill="url(#headerGrid)"/>
          <rect x="0" y="0" width="100%" height="80" fill="url(#sectionHatch)"/>
          <rect x="0" y="calc(100% - 40px)" width="100%" height="40" fill="url(#sectionHatch)"/>
          
          <!-- Bordi superiore e inferiore -->
          <line x1="0" y1="1" x2="100%" y2="1" stroke="rgb(107 114 128)" stroke-width="1" opacity="0.3"/>
          <line x1="0" y1="calc(100% - 1px)" x2="100%" y2="calc(100% - 1px)" stroke="rgb(107 114 128)" stroke-width="1" opacity="0.3"/>
        </svg>
      </div>

      <div class="relative z-10 max-w-7xl mx-auto">
        <div class="flex items-center justify-between">
          <div class="space-y-4">
            <div class="flex items-center gap-4">
              <div class="flex items-center gap-1">
                <div class="w-1.5 h-1.5 bg-green-500 rounded-full"></div>
                <div class="w-1.5 h-1.5 bg-yellow-500 rounded-full"></div>
                <div class="w-1.5 h-1.5 bg-red-500 rounded-full"></div>
              </div>
              <span class="text-gray-500 text-xs font-mono tracking-wider">PORTFOLIO.PROJECTS</span>
              <div class="w-8 h-px bg-gray-600/50"></div>
              <span class="text-gray-600 text-xs font-mono">SECTION_02</span>
            </div>
            <h2 class="text-5xl font-light text-white">
              Engineering 
              <span class="text-red-500 font-normal">Solutions</span>
            </h2>
            <p class="text-gray-400 text-lg font-mono">
              Selected works and technical implementations
            </p>
          </div>
          
          <!-- Navigation custom con design più elaborato -->
          <div class="flex items-center gap-4">
            <div class="flex items-center gap-2 text-gray-500 text-xs font-mono">
              <span>NAVIGATE:</span>
            </div>
            <button 
              @click="slidePrev"
              class="w-12 h-12 border border-gray-600/50 bg-gray-800/30 hover:bg-gray-700/50 transition-all duration-300 flex items-center justify-center group relative overflow-hidden"
            >
              <!-- Effetto tech background -->
              <div class="absolute inset-0 bg-gradient-to-r from-transparent via-gray-600/10 to-transparent transform -skew-x-12 group-hover:translate-x-full transition-transform duration-700"></div>
              <svg class="w-5 h-5 text-gray-400 group-hover:text-white transition-colors relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/>
              </svg>
            </button>
            
            <div class="text-gray-500 text-sm font-mono flex items-center gap-2">
              <span>{{ String(currentSlide + 1).padStart(2, '0') }}</span>
              <div class="w-6 h-px bg-gray-600"></div>
              <span>{{ String(projects.length).padStart(2, '0') }}</span>
            </div>
            
            <button 
              @click="slideNext"
              class="w-12 h-12 border border-gray-600/50 bg-gray-800/30 hover:bg-gray-700/50 transition-all duration-300 flex items-center justify-center group relative overflow-hidden"
            >
              <!-- Effetto tech background -->
              <div class="absolute inset-0 bg-gradient-to-r from-transparent via-gray-600/10 to-transparent transform -skew-x-12 group-hover:translate-x-full transition-transform duration-700"></div>
              <svg class="w-5 h-5 text-gray-400 group-hover:text-white transition-colors relative z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Swiper Carousel -->
    <div class="relative">
      <Swiper
        ref="swiperRef"
        :modules="modules"
        :slides-per-view="1"
        :space-between="0"
        :loop="true"
        :speed="800"
        :autoplay="{
          delay: autoplayDelay,
          disableOnInteraction: false,
        }"
        :navigation="{
          nextEl: '.swiper-button-next-custom',
          prevEl: '.swiper-button-prev-custom',
        }"
        :pagination="{
          el: '.swiper-pagination-custom',
          clickable: true,
        }"
        @slideChange="onSlideChange"
        class="w-full"
      >
        <SwiperSlide v-for="(project, index) in projects" :key="project.id || index">
          <ProjectSlide :project="project" :project-index="index" />
        </SwiperSlide>
      </Swiper>

      <!-- Custom Navigation Buttons -->
      <button class="swiper-button-prev-custom absolute left-8 top-1/2 transform -translate-y-1/2 z-20 w-12 h-12 border-2 border-gray-600/50 bg-gray-900/80 hover:bg-gray-800/90 hover:border-gray-500/70 transition-all duration-300 flex items-center justify-center group backdrop-blur-sm">
        <svg class="w-6 h-6 text-gray-400 group-hover:text-white transition-colors" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/>
        </svg>
      </button>
      
      <button class="swiper-button-next-custom absolute right-8 top-1/2 transform -translate-y-1/2 z-20 w-12 h-12 border-2 border-gray-600/50 bg-gray-900/80 hover:bg-gray-800/90 hover:border-gray-500/70 transition-all duration-300 flex items-center justify-center group backdrop-blur-sm">
        <svg class="w-6 h-6 text-gray-400 group-hover:text-white transition-colors" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
        </svg>
      </button>

      <!-- Custom Pagination Bullets -->
      <div class="swiper-pagination-custom absolute bottom-8 left-1/2 transform -translate-x-1/2 flex items-center gap-3"></div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation, Pagination, Autoplay } from 'swiper/modules'
import ProjectSlide from './ProjectSlide.vue'

// Import Swiper styles
import 'swiper/css'
import 'swiper/css/navigation'
import 'swiper/css/pagination'

// Props
const props = defineProps({
  projects: {
    type: Array,
    required: true
  },
  autoplayDelay: {
    type: Number,
    default: 5000
  }
})

// Reactive data
const swiperRef = ref(null)
const currentSlide = ref(0)

// Swiper modules
const modules = [Navigation, Pagination, Autoplay]

// Metodi per controllare Swiper
const slideNext = () => {
  if (swiperRef.value) {
    swiperRef.value.$el.swiper.slideNext()
  }
}

const slidePrev = () => {
  if (swiperRef.value) {
    swiperRef.value.$el.swiper.slidePrev()
  }
}

const goToSlide = (index) => {
  if (swiperRef.value) {
    swiperRef.value.$el.swiper.slideTo(index)
  }
}

// Event handlers
const onSlideChange = (swiper) => {
  currentSlide.value = swiper.realIndex
}

// Lifecycle
onMounted(() => {
  // Inizializzazione aggiuntiva se necessaria
})
</script>

<style scoped>
/* Custom Swiper Styles */
:deep(.swiper-pagination-bullet) {
  width: 12px;
  height: 4px;
  border-radius: 2px;
  background: rgb(75 85 99);
  opacity: 1;
  transition: all 0.3s ease;
  margin: 0 4px;
}

:deep(.swiper-pagination-bullet-active) {
  width: 32px;
  background: rgb(239 68 68);
}

:deep(.swiper-pagination-bullet:hover) {
  background: rgb(107 114 128);
}

/* Hide default Swiper buttons since we use custom ones */
:deep(.swiper-button-next),
:deep(.swiper-button-prev) {
  display: none;
}

/* Ensure proper z-index for navigation */
.swiper-button-prev-custom,
.swiper-button-next-custom {
  z-index: 30;
}

/* Custom button hover effects */
.swiper-button-prev-custom:hover,
.swiper-button-next-custom:hover {
  transform: translateY(-50%) scale(1.05);
}

/* Technical styling for buttons */
.swiper-button-prev-custom::before,
.swiper-button-next-custom::before {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, transparent, rgba(107, 114, 128, 0.1), transparent);
  border-radius: inherit;
  z-index: -1;
}
</style>