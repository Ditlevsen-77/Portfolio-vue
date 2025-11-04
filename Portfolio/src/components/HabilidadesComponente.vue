<script setup>
import { ref } from 'vue'

const habilidades = ref([
  "JavaScript",
  "Vue.js",
  "HTML/CSS",
  "Python",
  "Git",
  "Desarrollo Web"
])
</script>

<template>
  <section id="habilidades" class="section">
    <h2>Habilidades Técnicas</h2>
    <div class="habilidades-grid">
      <div v-for="habilidad in habilidades" :key="habilidad" class="habilidad-item">
        {{ habilidad }}
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

.habilidades-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1rem;
}

.habilidad-item {
  padding: 1rem;
  background-color: #3d3d3d;
  border-radius: 5px;
  text-align: center;
  border: 1px solid #555;
  transition: background-color 0.3s ease;
}

.habilidad-item:hover {
  background-color: #4d4d4d;
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
  
  .habilidades-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>

