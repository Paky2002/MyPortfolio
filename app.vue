<template>
  <div>
    <Navbar/>
    <Hero/>
    <AboutMe/>
    <ProjectsCarousel :projects="projectsData" />
    <Curosr/>
  </div>
</template>

<script setup lang="ts">

const projectsData = [
  {
    id: 1,
    category: 'frontend',
    title: {
      main: 'E-commerce',
      accent: 'Dashboard'
    },
    subtitle: 'Modern admin panel for e-commerce management',
    description: 'Dashboard completa per la gestione di un e-commerce con <span class="text-white font-medium">analytics in tempo reale</span>, gestione prodotti, ordini e clienti.',
    techStack: ['Vue.js', 'Tailwind', 'Chart.js', 'API Rest'],
    links: [
      { label: 'Live Demo', url: 'https://demo.com', type: 'demo' },
      { label: 'GitHub', url: 'https://github.com', type: 'github' }
    ],
    completedDate: '2024.Q1',
    image: '/projects/ecommerce-dashboard.png', // opzionale
    imagePlaceholder: 'DASHBOARD_UI.PNG',
    imageSpecs: '1920x1440px'
  },
  {
    id: 2,
    category: 'backend',
    title: {
      main: 'REST API',
      accent: 'Server'
    },
    subtitle: 'Scalable microservices architecture',
    description: 'API server con architettura a microservizi, <span class="text-white font-medium">autenticazione JWT</span>, caching Redis e database PostgreSQL.',
    techStack: ['Node.js', 'Express', 'PostgreSQL', 'Redis'],
    links: [
      { label: 'GitHub', url: 'https://github.com', type: 'github' },
      { label: 'API Docs', url: 'https://docs.com', type: 'docs' }
    ],
    completedDate: '2024.Q2',
    imagePlaceholder: 'API_ARCH.PNG',
    imageSpecs: 'Architecture Diagram'
  }
  // Aggiungi altri progetti...
]
</script>