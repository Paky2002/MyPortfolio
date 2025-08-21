<template>
  <section class="min-h-screen bg-black flex items-center justify-center px-4 relative overflow-hidden pt-20">
    <!-- Grid Background -->
    <div class="absolute inset-0">
      <svg class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="grid" width="70" height="70" patternUnits="userSpaceOnUse">
            <line x1="0" y1="0" x2="0" y2="70" stroke="rgb(107 114 128)" stroke-width="1" opacity="0.4"/>
            <line x1="35" y1="0" x2="35" y2="70" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="2,4" opacity="0.2"/>
            <line x1="0" y1="0" x2="70" y2="0" stroke="rgb(107 114 128)" stroke-width="1" opacity="0.4"/>
            <line x1="0" y1="35" x2="70" y2="35" stroke="rgb(107 114 128)" stroke-width="1" stroke-dasharray="2,4" opacity="0.2"/>
            <text x="5" y="67" fill="rgb(107 114 128)" font-size="6" opacity="0.6" font-family="monospace">01</text>
            <text x="40" y="67" fill="rgb(107 114 128)" font-size="6" opacity="0.4" font-family="monospace">02</text>
            <text x="2" y="30" fill="rgb(107 114 128)" font-size="6" opacity="0.5" font-family="monospace">A</text>
            <path d="M 65 65 L 68 65 M 66 63 L 68 65 L 66 67" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.3" fill="none"/>
            <path d="M 30 5 L 30 8 M 28 6 L 30 8 L 32 6" stroke="rgb(107 114 128)" stroke-width="0.5" opacity="0.3" fill="none"/>
            <circle cx="70" cy="0" r="0.8" fill="rgb(107 114 128)" opacity="0.4"/>
            <circle cx="35" cy="35" r="0.5" fill="rgb(107 114 128)" opacity="0.3"/>
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#grid)"/>
      </svg>
    </div>
    
    <div class="max-w-7xl mx-auto w-full relative z-10">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        
        <!-- Sezione Testo -->
        <div class="text-white space-y-6">
          <div class="inline-flex items-center bg-green-500/10 border border-green-500/20 rounded-full px-4 py-2">
            <div class="w-2 h-2 bg-green-500 rounded-full mr-3">
              <div class="w-2 h-2 bg-green-500 rounded-full animate-ping"></div>
            </div>
            <span class="text-green-400 text-base font-medium">Available for collaborations</span>
          </div>
          
          <h1 class="text-4xl lg:text-6xl font-bold text-white leading-tight">
            Engineering 
            <span class="text-red-500">software solutions</span> 
            with 
            <span class="text-red-500">clean code</span> 
            and 
            <span class="text-red-500">solid architecture</span>.
          </h1>
        </div>

        <!-- Sezione Terminale "Tagliato" -->
        <div class="relative lg:pl-8 flex items-center justify-center">
          <!-- Container che si estende oltre i bordi -->
          <div class="relative w-[140%] -mr-[40%] overflow-hidden">
            <!-- Terminale principale -->
            <div class="bg-white/10  border border-white/30 rounded-xl shadow-2xl h-[500px] backdrop-saturate-200 backdrop-brightness-110">
              <!-- Header del terminale -->
              <div class="flex items-center justify-between px-4 py-3 border-b border-white/15 bg-white/5">
                <div class="flex items-center gap-2">
                  <div class="w-3 h-3 bg-red-500 rounded-full"></div>
                  <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
                  <div class="w-3 h-3 bg-green-500 rounded-full"></div>
                </div>
                <span class="text-white/80 text-sm font-mono">portfolio-architecture.js</span>
                <div class="w-6"></div>
              </div>
              
              <div class="p-6 font-mono text-sm leading-relaxed h-full overflow-hidden">
                <div class="mb-4">
                  <span class="text-green-400">user@portfolio</span>
                  <span class="text-gray-400">:</span>
                  <span class="text-blue-400">~/projects</span>
                  <span class="text-gray-400">$</span>
                  <span class="text-white ml-2">npm run dev</span>
                </div>
                
                <div class="space-y-2 mb-6 text-gray-300">
                  <div class="text-green-400">✓ Nuxt ready in 1.2s</div>
                  <div class="text-blue-400">➜ Local: http://localhost:3000</div>
                  <div class="text-gray-400">➜ Network: use --host to expose</div>
                </div>
                
                <!-- Codice JavaScript più semplice -->
                <div class="space-y-1">
                  <div class="text-purple-400">export default <span class="text-gray-400">{</span></div>
                  <div class="pl-4">
                    <span class="text-cyan-400">name</span><span class="text-gray-400">:</span> <span class="text-green-400">'Portfolio'</span><span class="text-gray-400">,</span>
                  </div>
                  <div class="pl-4">
                    <span class="text-cyan-400">skills</span><span class="text-gray-400">:</span> <span class="text-gray-400">[</span>
                  </div>
                  <div class="pl-8">
                    <span class="text-green-400">'Vue.js'</span><span class="text-gray-400">,</span> <span class="text-green-400">'Nuxt.js'</span><span class="text-gray-400">,</span>
                  </div>
                  <div class="pl-8">
                    <span class="text-green-400">'TypeScript'</span><span class="text-gray-400">,</span> <span class="text-green-400">'Node.js'</span>
                  </div>
                  <div class="pl-4 text-gray-400">],</div>
                  <div class="pl-4">
                    <span class="text-yellow-400">mounted</span><span class="text-gray-400">() {</span>
                  </div>
                  <div class="pl-8">
                    <span class="text-blue-400">this</span><span class="text-gray-400">.</span><span class="text-yellow-400">buildAwesomeStuff</span><span class="text-gray-400">();</span>
                  </div>
                  <div class="pl-4 text-gray-400">},</div>
                  <div class="pl-4">
                    <span class="text-yellow-400">methods</span><span class="text-gray-400">: {</span>
                  </div>
                  <div class="pl-8">
                    <span class="text-blue-400">buildAwesomeStuff</span><span class="text-gray-400">() {</span>
                  </div>
                  <div class="pl-12">
                    <span class="text-blue-400">console</span><span class="text-gray-400">.</span><span class="text-yellow-400">log</span><span class="text-gray-400">(</span><span class="text-green-400">'🚀 Creating magic...'</span><span class="text-gray-400">);</span>
                  </div>
                  <div class="pl-8 text-gray-400">}</div>
                  <div class="pl-4 text-gray-400">}</div>
                  <div class="text-gray-400">}</div>
                </div>
                
                <!-- Prompt attivo -->
                <div class="mt-6 flex items-center">
                  <span class="text-green-400">user@portfolio</span>
                  <span class="text-gray-400">:</span>
                  <span class="text-blue-400">~/projects</span>
                  <span class="text-gray-400">$</span>
                  <span class="text-green-400 animate-pulse ml-2">_</span>
                </div>
              </div>
            </div>
            
            <!-- Gradiente per l'effetto "fade out" sui bordi -->
            <div class="absolute right-0 top-0 bottom-0 w-20 bg-gradient-to-l from-black to-transparent pointer-events-none"></div>
          </div>
        </div>
      </div>
    </div>
    </section>

    
</template>
