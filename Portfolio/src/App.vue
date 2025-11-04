<script setup>
import NavBar from './components/icons/NavBar.vue'
import DatosPersonales from './components/DatosPersonales.vue'
import EducacionComponente from './components/EducacionComponente.vue'
import ExperienciaComponente from './components/ExperienciaComponente.vue'
import ProyectosComponente from './components/ProyectosComponente.vue'
import HabilidadesComponente from './components/HabilidadesComponente.vue'
import InteresesComponente from './components/InteresesComponente.vue'
import ContactoComponente from './components/ContactoComponente.vue'
</script>

<template>
  <div class="portfolio">
    <!-- Barra de Navegación -->
    <NavBar />

    <main class="main-content">
      <!-- Datos Personales -->
      <DatosPersonales />

      <!-- Educación -->
      <EducacionComponente />

      <!-- Experiencia y Organización -->
      <ExperienciaComponente />

      <!-- Proyectos -->
      <ProyectosComponente />

      <!-- Habilidades -->
      <HabilidadesComponente />

      <!-- Intereses con fondo lava -->
      <InteresesComponente />

      <!-- Contacto -->
      <ContactoComponente />
    </main>
  </div>
</template>

<style scoped>
.portfolio {
  width: 100vw;
  min-height: 100vh;
  background-color: #1a1a1a;
  color: #cccccc;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  overflow-x: hidden;
  position: absolute;
  top: 0;
  left: 0;
}

.main-content {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  .main-content {
    padding: 1rem;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .main-content { 
    padding: 1.5rem; 
  }
}

@media (min-width: 1280px) {
  .main-content { 
    max-width: 1200px; 
  }
}
</style>
