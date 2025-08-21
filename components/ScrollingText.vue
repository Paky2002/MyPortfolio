<template>
  <section class="relative w-full h-20 bg-white overflow-hidden border-y-2 border-black" style="height: 80px;">
    <!-- Grid background -->
    <div class="absolute inset-0">
      <svg class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="scrollGrid" width="40" height="40" patternUnits="userSpaceOnUse">
            <line x1="0" y1="0" x2="0" y2="40" stroke="rgb(0 0 0)" stroke-width="0.3" opacity="0.1"/>
            <line x1="0" y1="0" x2="40" y2="0" stroke="rgb(0 0 0)" stroke-width="0.3" opacity="0.1"/>
          </pattern>
          
          <!-- Pattern hatch per le lettere su sfondo bianco -->
          <pattern id="letterHatchBlack1" patternUnits="userSpaceOnUse" width="4" height="4">
            <path d="M0,4 L4,0" stroke="currentColor" stroke-width="0.5" opacity="0.4"/>
          </pattern>
          
          <pattern id="letterHatchBlack2" patternUnits="userSpaceOnUse" width="6" height="6">
            <path d="M0,6 L6,0" stroke="currentColor" stroke-width="0.4" opacity="0.3"/>
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#scrollGrid)"/>
      </svg>
    </div>

    <!-- Linee di separazione tecniche -->
    <svg class="absolute inset-0 w-full h-full pointer-events-none" xmlns="http://www.w3.org/2000/svg">
      <!-- Annotazioni tecniche laterali -->
      <text x="20" y="10" fill="rgb(0 0 0)" font-size="7" font-family="monospace" opacity="0.6">INVERTED_SECTION</text>
      <text x="calc(100% - 100px)" y="10" fill="rgb(0 0 0)" font-size="7" font-family="monospace" opacity="0.6">WHITE_BG</text>
      
      <!-- Indicatori di direzione -->
      <g opacity="0.4">
        <line x1="30" y1="50%" x2="45" y2="50%" stroke="rgb(0 0 0)" stroke-width="1.5"/>
        <line x1="40" y1="calc(50% - 4px)" x2="45" y2="50%" stroke="rgb(0 0 0)" stroke-width="1.5"/>
        <line x1="40" y1="calc(50% + 4px)" x2="45" y2="50%" stroke="rgb(0 0 0)" stroke-width="1.5"/>
      </g>
    </svg>

    <!-- Container del testo scrolling -->
    <div class="relative h-full flex items-center">
      <!-- Fade masks sui bordi -->
      <div class="absolute left-0 top-0 bottom-0 w-16 bg-gradient-to-r from-white to-transparent z-10"></div>
      <div class="absolute right-0 top-0 bottom-0 w-16 bg-gradient-to-l from-white to-transparent z-10"></div>
      
      <!-- Testo scrolling -->
      <div class="flex items-center whitespace-nowrap animate-scroll">
        <!-- Primo set -->
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">ENGINEERING</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">SOLUTIONS</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">DEVELOPMENT</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">INNOVATION</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">PORTFOLIO</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        
        <!-- Duplicato per loop seamless -->
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">ENGINEERING</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">SOLUTIONS</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">DEVELOPMENT</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">INNOVATION</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
        <span class="text-5xl font-black text-black mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">PORTFOLIO</span>
        <span class="text-5xl font-black text-red-600 mr-6 tracking-wide" style="font-family: 'Arial Black', 'Helvetica', sans-serif;">•</span>
      </div>
    </div>

    <!-- Coordinate tecniche angolari -->
    <div class="absolute top-2 left-2 text-black text-xs font-mono opacity-60">W1</div>
    <div class="absolute top-2 right-2 text-black text-xs font-mono opacity-60">W2</div>
    <div class="absolute bottom-2 left-2 text-black text-xs font-mono opacity-60">W3</div>
    <div class="absolute bottom-2 right-2 text-black text-xs font-mono opacity-60">W4</div>
  </section>
</template>

<script setup>
// Nessuna logica necessaria, tutto CSS
</script>

<style scoped>
/* Animazione scrolling infinita */
@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

.animate-scroll {
  animation: scroll 25s linear infinite;
}

/* Pause on hover per debugging/UX */
.animate-scroll:hover {
  animation-play-state: paused;
}

/* Effetto glow sui bullet rossi */
span:nth-child(even) {
  text-shadow: 0 0 8px rgba(220, 38, 38, 0.4);
}

/* Performance optimization */
.animate-scroll {
  will-change: transform;
}
</style>