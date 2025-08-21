<template>
  <section class="relative h-[520px] w-full bg-black overflow-hidden">
    <!-- Grid di sfondo sottile per continuità con l'hero -->
    <div class="absolute inset-0">
      <svg class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="aboutGrid" width="40" height="40" patternUnits="userSpaceOnUse">
            <line x1="0" y1="0" x2="0" y2="40" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.15"/>
            <line x1="0" y1="0" x2="40" y2="0" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.15"/>
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#aboutGrid)"/>
      </svg>
    </div>

    <!-- Linee tecniche principali -->
    <svg class="absolute inset-0 w-full h-[520px] pointer-events-none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <!-- Definizione per le frecce -->
        <marker id="arrowhead" markerWidth="8" markerHeight="6" refX="7" refY="3" orient="auto" fill="rgb(107 114 128)">
          <polygon points="0 0, 8 3, 0 6" opacity="0.6"/>
        </marker>
        
        <!-- Pattern per linee tratteggiate più sottili -->
        <pattern id="dashedPattern" patternUnits="userSpaceOnUse" width="12" height="2">
          <rect width="6" height="2" fill="rgb(107 114 128)" opacity="0.4"/>
          <rect x="6" width="6" height="2" fill="transparent"/>
        </pattern>

        <!-- Pattern hatch per area sopra l'immagine (stile disegno tecnico) -->
        <pattern id="hatchPattern" patternUnits="userSpaceOnUse" width="8" height="8">
          <path d="M0,8 L8,0" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.4"/>
        </pattern>

        <!-- Pattern hatch per area sotto l'immagine -->
        <pattern id="hatchPatternBottom" patternUnits="userSpaceOnUse" width="8" height="8">
          <path d="M0,8 L8,0" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.3"/>
        </pattern>
      </defs>

      <!-- Aree hatch sopra e sotto l'immagine -->
      <g>
        <!-- Area sopra l'immagine (60px di altezza) -->
        <rect x="60" y="80" width="380" height="60" fill="url(#hatchPattern)"/>
        
        <!-- Area sotto l'immagine (70px di altezza) -->
        <rect x="60" y="530" width="380" height="70" fill="url(#hatchPatternBottom)"/>
      </g>

      <!-- Linea orizzontale superiore con dettagli tecnici -->
      <g>
        <line x1="0" y1="140" x2="100%" y2="140" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.6"/>
        <!-- Misure tecniche superiori -->
        <text x="20" y="125" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7">60px</text>
        <line x1="60" y1="130" x2="60" y2="135" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.5"/>
        <line x1="60" y1="145" x2="60" y2="150" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.5"/>
      </g>

      <!-- Linea orizzontale inferiore -->
      <g>
        <line x1="0" y1="530" x2="100%" y2="530" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.6"/>
        <text x="20" y="550" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7">390px</text>
      </g>

      <!-- Linea verticale sinistra con annotazioni -->
      <g>
        <line x1="60" y1="80" x2="60" y2="100%" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.6"/>
        <!-- Annotazione laterale -->
        <text x="10" y="340" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7" transform="rotate(-90 10 340)">SECTION.01</text>
        <!-- Piccoli segni di misura -->
        <line x1="50" y1="140" x2="55" y2="140" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.5"/>
        <line x1="65" y1="140" x2="70" y2="140" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.5"/>
      </g>

      <!-- Linea verticale destra -->
      <g>
        <line x1="440" y1="80" x2="440" y2="100%" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="4,4" opacity="0.6"/>
        <text x="445" y="180" fill="rgb(107 114 128)" font-size="8" font-family="monospace" opacity="0.7">380px</text>
        <line x1="430" y1="530" x2="435" y2="530" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.5"/>
        <line x1="445" y1="530" x2="450" y2="530" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.5"/>
      </g>

      <!-- Dettagli angolari tecnici -->
      <g opacity="0.4">
        <!-- Angolo superiore sinistro -->
        <path d="M 55 135 L 65 135 M 60 130 L 60 140" stroke="rgb(107 114 128)" stroke-width="0.5" fill="none"/>
        <circle cx="60" cy="140" r="1.5" fill="none" stroke="rgb(107 114 128)" stroke-width="0.5"/>
        
        <!-- Angolo superiore destro -->
        <path d="M 435 135 L 445 135 M 440 130 L 440 140" stroke="rgb(107 114 128)" stroke-width="0.5" fill="none"/>
        <circle cx="440" cy="140" r="1.5" fill="none" stroke="rgb(107 114 128)" stroke-width="0.5"/>
        
        <!-- Angolo inferiore sinistro -->
        <path d="M 55 525 L 65 525 M 60 520 L 60 530" stroke="rgb(107 114 128)" stroke-width="0.5" fill="none"/>
        <circle cx="60" cy="530" r="1.5" fill="none" stroke="rgb(107 114 128)" stroke-width="0.5"/>
        
        <!-- Angolo inferiore destro -->
        <path d="M 435 525 L 445 525 M 440 520 L 440 530" stroke="rgb(107 114 128)" stroke-width="0.5" fill="none"/>
        <circle cx="440" cy="530" r="1.5" fill="none" stroke="rgb(107 114 128)" stroke-width="0.5"/>
      </g>

      <!-- Freccia di connessione verso l'area testo -->
      <g opacity="0.5">
        <line x1="460" y1="335" x2="500" y2="335" stroke="rgb(107 114 128)" stroke-width="0.8" marker-end="url(#arrowhead)"/>
        <text x="465" y="325" fill="rgb(107 114 128)" font-size="7" font-family="monospace" opacity="0.8">ABOUT</text>
      </g>

      <!-- Coordinate tecniche -->
      <text x="65" y="155" fill="rgb(107 114 128)" font-size="6" font-family="monospace" opacity="0.6">A1</text>
      <text x="435" y="155" fill="rgb(107 114 128)" font-size="6" font-family="monospace" opacity="0.6">B1</text>
      <text x="65" y="520" fill="rgb(107 114 128)" font-size="6" font-family="monospace" opacity="0.6">A2</text>
      <text x="435" y="520" fill="rgb(107 114 128)" font-size="6" font-family="monospace" opacity="0.6">B2</text>
    </svg>

    <!-- Contenuto principale -->
    <div class="relative z-10 flex h-full">
      <!-- Container immagine con bordo tecnico -->
      <div class="relative mt-[140px] ml-[60px]" style="width: 380px; height: 390px;">
        <!-- Cornice sottile interna -->
        <div class="absolute inset-0 border border-gray-500/30 pointer-events-none z-20"></div>
        
        <!-- Tacche angolari sulla cornice -->
        <div class="absolute -top-1 -left-1 w-3 h-3 border-l border-t border-gray-400/50 pointer-events-none z-20"></div>
        <div class="absolute -top-1 -right-1 w-3 h-3 border-r border-t border-gray-400/50 pointer-events-none z-20"></div>
        <div class="absolute -bottom-1 -left-1 w-3 h-3 border-l border-b border-gray-400/50 pointer-events-none z-20"></div>
        <div class="absolute -bottom-1 -right-1 w-3 h-3 border-r border-b border-gray-400/50 pointer-events-none z-20"></div>
        
        <!-- Immagine con padding per la cornice -->
        <div class="p-1 w-full h-full">
          <img 
            src="/me.jpg" 
            alt="Profile" 
            class="w-full h-full object-cover grayscale-[0.2] contrast-110" 
          />
        </div>

        <!-- Etichetta tecnica per l'immagine -->
        <div class="absolute -bottom-8 left-0 flex items-center gap-2">
          <div class="w-2 h-2 border border-gray-500/60 bg-gray-500/20"></div>
          <span class="text-gray-400 text-xs font-mono">IMG_PROFILE.JPG</span>
          <span class="text-gray-500 text-xs font-mono">• 380x390px</span>
        </div>
      </div>

      <!-- Area destra per il testo con layout tecnico -->
      <div class="flex-1 flex items-center px-16 relative">
        <!-- Linea di connessione sottile -->
        <div class="absolute left-8 top-1/2 w-8 h-px bg-gray-500/40"></div>
        
        <div class="space-y-6">
          <!-- Header con stile tecnico -->
          <div class="space-y-2">
            <div class="flex items-center gap-3 mb-4">
              <div class="flex items-center gap-1">
                <div class="w-1 h-1 bg-green-500 rounded-full"></div>
                <div class="w-1 h-1 bg-yellow-500 rounded-full"></div>
                <div class="w-1 h-1 bg-red-500 rounded-full"></div>
              </div>
              <span class="text-gray-500 text-xs font-mono tracking-wider">DEVELOPER.BIO</span>
            </div>
            
            <h2 class="text-4xl font-light text-white leading-tight">
              Ciao, sono un
              <span class="block text-red-500 font-normal">Software Engineer</span>
            </h2>
          </div>

          <!-- Descrizione con stile monospace -->
          <div class="space-y-4 text-gray-300">
            <p class="text-lg leading-relaxed">
              Specializzo nello sviluppo di applicazioni web moderne 
              con particolare attenzione all'<span class="text-white font-medium">architettura software</span> 
              e alle <span class="text-white font-medium">performance</span>.
            </p>
            
            <!-- Stack tecnico -->
            <div class="space-y-2">
              <div class="text-sm text-gray-500 font-mono tracking-wide">TECH_STACK:</div>
              <div class="flex flex-wrap gap-2">
                <span class="px-2 py-1 text-xs font-mono bg-gray-800/50 border border-gray-700/50 text-gray-300 rounded">01.Vue.js</span>
                <span class="px-2 py-1 text-xs font-mono bg-gray-800/50 border border-gray-700/50 text-gray-300 rounded">02.Nuxt.js</span>
                <span class="px-2 py-1 text-xs font-mono bg-gray-800/50 border border-gray-700/50 text-gray-300 rounded">03.TypeScript</span>
                <span class="px-2 py-1 text-xs font-mono bg-gray-800/50 border border-gray-700/50 text-gray-300 rounded">04.Node.js</span>
                <span class="px-2 py-1 text-xs font-mono bg-gray-800/50 border border-gray-700/50 text-gray-300 rounded">05.Docker</span>
              </div>
            </div>
          </div>

          <!-- Status indicator -->
          <div class="flex items-center gap-3 pt-4">
            <div class="flex items-center gap-2">
              <div class="w-2 h-2 bg-green-500 rounded-full">
                <div class="w-2 h-2 bg-green-500 rounded-full animate-ping"></div>
              </div>
              <span class="text-green-400 text-sm font-mono">STATUS: AVAILABLE</span>
            </div>
            <div class="text-gray-600 text-xs font-mono">
              LAST_UPDATE: {{ currentDate }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Data corrente per il timestamp
const currentDate = new Date().toISOString().split('T')[0]
</script>

<style scoped>
/* Eventuali stili aggiuntivi specifici del componente */
</style>