<script setup>
import { ref } from 'vue'

const datosPersonales = ref({
  nombre: "Ian Ditlevsen",
  edad: "26 años",
  direccion: "Cuadro Benegas, San Rafael, Mendoza",
  telefono: "+54 9 2604 30-5119",
  codigoPostal: "M5603",
  github: "https://github.com/Ditlevsen-77"
})
</script>

<template>
  <section id="datos-personales" class="section">
    <h2>Datos Personales</h2>
    <div class="datos-grid">
      <div class="dato-item">
        <strong>Nombre:</strong> {{ datosPersonales.nombre }}
      </div>
      <div class="dato-item">
        <strong>Edad:</strong> {{ datosPersonales.edad }}
      </div>
      <div class="dato-item">
        <strong>Dirección:</strong> {{ datosPersonales.direccion }}
      </div>
      <div class="dato-item">
        <strong>Teléfono:</strong> {{ datosPersonales.telefono }}
      </div>
      <div class="dato-item">
        <strong>Código Postal:</strong> {{ datosPersonales.codigoPostal }}
      </div>
      <div class="dato-item github-item">
        <strong>GitHub:</strong> 
        <a :href="datosPersonales.github" target="_blank" class="github-link">
          <span class="github-icon">🐙</span>
          Ditlevsen-77
        </a>
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

.datos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
}

.dato-item {
  padding: 1rem;
  background-color: #3d3d3d;
  border-radius: 5px;
  border-left: 4px solid #666;
}

.github-item {
  background-color: #1a1a1a;
  border-left: 4px solid #333;
  transition: all 0.3s ease;
}

.github-item:hover {
  background-color: #24292e;
  border-left-color: #58a6ff;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.github-link {
  color: #58a6ff;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: 500;
  transition: all 0.3s ease;
}

.github-link:hover {
  color: #79c0ff;
  text-decoration: none;
}

.github-icon {
  font-size: 1.2rem;
}

@media (max-width: 768px) {
  .section {
    padding: 1rem;
  }
  
  .datos-grid {
    grid-template-columns: 1fr;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .section {
    padding: 1.5rem;
  }
  
  .section h2 {
    font-size: 1.8rem;
  }
  
  .datos-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
