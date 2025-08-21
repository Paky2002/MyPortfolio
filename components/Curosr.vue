<template>
  <div v-if="isVisible">
    <!-- Cursore principale -->
    <div 
      class="fixed w-4 h-4 bg-white rounded-full pointer-events-none z-[9999] transition-transform duration-75 ease-out"
      :style="cursorStyle"
    ></div>
    
    <!-- Pallino che segue -->
    <div 
      class="fixed w-10 h-10 border border-white/60 rounded-full pointer-events-none z-[9998] transition-all duration-200 ease-out"
      :style="followerStyle"
    ></div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const mouseX = ref(0)
const mouseY = ref(0)
const followerX = ref(0)
const followerY = ref(0)
const isVisible = ref(false)

// Stili computati
const cursorStyle = computed(() => ({
  left: `${mouseX.value}px`,
  top: `${mouseY.value}px`,
  transform: 'translate(-50%, -50%)'
}))

const followerStyle = computed(() => ({
  left: `${followerX.value}px`,
  top: `${followerY.value}px`,
  transform: 'translate(-50%, -50%)'
}))

// Aggiorna posizione mouse
const updateMouse = (e) => {
  mouseX.value = e.clientX
  mouseY.value = e.clientY
}

// Aggiorna follower con ritardo
const updateFollower = () => {
  followerX.value += (mouseX.value - followerX.value) * 0.1
  followerY.value += (mouseY.value - followerY.value) * 0.1
  requestAnimationFrame(updateFollower)
}

onMounted(() => {
  // Inizializza posizioni al centro
  mouseX.value = window.innerWidth / 2
  mouseY.value = window.innerHeight / 2
  followerX.value = mouseX.value
  followerY.value = mouseY.value
  
  isVisible.value = true
  
  // Nasconde cursore default su tutto
  document.body.style.cursor = 'none'
  document.documentElement.style.cursor = 'none'
  
  // Aggiunge CSS globale per nascondere tutti i cursori
  const style = document.createElement('style')
  style.textContent = `
    *, *::before, *::after {
      cursor: none !important;
    }
  `
  document.head.appendChild(style)
  
  // Event listeners
  document.addEventListener('mousemove', updateMouse)
  
  // Avvia animazione follower
  updateFollower()
})

onUnmounted(() => {
  // Ripristina cursore
  document.documentElement.style.cursor = 'auto'
  document.removeEventListener('mousemove', updateMouse)
  isVisible.value = false
})
</script>