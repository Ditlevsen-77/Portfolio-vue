<script setup>
import { ref } from 'vue'

const educacion = ref([
  {
    nivel: "Primario",
    institucion: "Escuela Nº 1665 - Padre Juan Pastor",
    periodo: "2005 - 2012",
    descripcion: "Educación primaria completa"
  },
  {
    nivel: "Secundario",
    institucion: "Escuela Nº 4050 - Roberto Azzoni",
    periodo: "2013 - 2018",
    descripcion: "Bachiller con orientación Económica"
  },
  {
    nivel: "Estudios Independientes",
    institucion: "Autodidacta",
    periodo: "2019 - 2023",
    descripcion: "Estudios de programación por cuenta propia"
  },
  {
    nivel: "Universitario",
    institucion: "Universidad Tecnológica Nacional (UTN) - Facultad Regional San Rafael",
    periodo: "2025 - Actualidad",
    descripcion: "Carrera de Programación - Segundo año",
  }
])
</script>

<template>
  <section id="educacion" class="section">
    <h2>Educación</h2>
    <div class="educacion-list">
      <div v-for="edu in educacion" :key="edu.nivel" class="educacion-item">
        <div class="educacion-header">
          <h3>{{ edu.nivel }}</h3>
          <img v-if="edu.logo" :src="edu.logo" :alt="edu.institucion" class="institucion-logo" />
        </div>
        <p class="institucion">{{ edu.institucion }}</p>
        <p class="periodo">{{ edu.periodo }}</p>
        <p class="descripcion">{{ edu.descripcion }}</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.section {
  margin-bottom: 3rem;
  padding: 2rem;
  background-color: #2d2d2d;
  border-radius: 8px;
  border: 1px solid #444;
}

.section h2 {
  color: #42b883;
  font-size: 2rem;
  margin-bottom: 1.5rem;
  border-bottom: 2px solid #555;
  padding-bottom: 0.5rem;
}

.section h3 {
  color: #42b883;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
}

.educacion-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.educacion-item {
  padding: 1.5rem;
  background-color: #3d3d3d;
  border-radius: 8px;
  border-left: 4px solid #666;
}

.educacion-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.institucion-logo {
  width: 60px;
  height: 60px;
  object-fit: contain;
  border-radius: 8px;
  background-color: #4d4d4d;
  padding: 8px;
}

.institucion {
  color: #ffffff;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.periodo {
  color: #999;
  font-style: italic;
  margin-bottom: 1rem;
}

.descripcion {
  line-height: 1.6;
}

@media (max-width: 768px) {
  .section {
    padding: 1rem;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .section {
    padding: 1.5rem;
  }
  
  .section h2 {
    font-size: 1.8rem;
  }
  
  .section h3 {
    font-size: 1.15rem;
  }
}
</style>
