<template>
  <header class="w-full border-b border-gray-800 fixed top-0 z-50 bg-black">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-22">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <span class="text-xl font-semibold text-white">Logo</span>
        </div>
        
        <!-- Navigation Links -->
        <nav class="hidden md:flex space-x-8">
          <NuxtLink to="/" class="text-gray-300">Link1</NuxtLink>
          <NuxtLink to="/about" class="text-gray-300">Link2</NuxtLink>
          <NuxtLink to="/services" class="text-gray-300">Link3</NuxtLink>
          <NuxtLink to="/contact" class="text-gray-300">Link4</NuxtLink>
        </nav>
        
        <!-- CTA Button -->
        <div class="flex-shrink-0">
          <button class="bg-red-600 text-white px-4 py-2 text-sm">
            CTA
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
// Nessuna logica necessaria per questo header minimal
</script>