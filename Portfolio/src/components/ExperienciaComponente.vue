<script setup>
import { ref } from 'vue'

const experiencia = ref([
  {
    empresa: "Carnicería El Buen Corte",
    puesto: "Desarrollador de Software",
    periodo: "2024",
    descripcion: "Desarrollo de sistema de gestión de inventario y ventas para carnicería local. Implementé funcionalidades para control de stock y facturación básica."
  },
  {
    empresa: "Tienda de Ropa Moda Joven",
    puesto: "Programador Junior",
    periodo: "2024",
    descripcion: "Creación de aplicación web para gestión de productos y clientes. Sistema simple para control de ventas y seguimiento de inventario de ropa."
  },
  {
    empresa: "Contador Independiente",
    puesto: "Desarrollador Freelance",
    periodo: "2024 - Actualidad",
    descripcion: "Desarrollo de herramientas personalizadas para facilitar el trabajo contable. Programas para cálculo de impuestos y gestión de clientes."
  }
])

const organizacion = ref([
  {
    rol: "Líder de Equipo",
    organizacion: "Equipo de Desarrollo Ad Astra",
    periodo: "2023 - Actualidad",
    descripcion: "Actualmente lidero un equipo de programadores en el desarrollo de software y videojuegos. Estamos creando nuestro propio videojuego llamado 'Ad Astra'."
  }
])
</script>

<template>
  <section id="experiencia" class="section">
    <h2>Experiencia Laboral</h2>
    <div class="experiencia-list">
      <div v-for="exp in experiencia" :key="exp.empresa" class="experiencia-item">
        <h3>{{ exp.puesto }}</h3>
        <p class="empresa">{{ exp.empresa }}</p>
        <p class="periodo">{{ exp.periodo }}</p>
        <p class="descripcion">{{ exp.descripcion }}</p>
      </div>
    </div>
    <div class="experiencia-total">
      <p><strong>Experiencia Total:</strong> 1 año (2024-2025)</p>
    </div>
  </section>

  <section id="organizacion" class="section">
    <h2>Organización, Liderazgo y Actividades</h2>
    <div class="organizacion-list">
      <div v-for="org in organizacion" :key="org.rol" class="organizacion-item">
        <h3>{{ org.rol }}</h3>
        <p class="organizacion-nombre">{{ org.organizacion }}</p>
        <p class="periodo">{{ org.periodo }}</p>
        <p class="descripcion">{{ org.descripcion }}</p>
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

.experiencia-list, .organizacion-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.experiencia-item, .organizacion-item {
  padding: 1.5rem;
  background-color: #3d3d3d;
  border-radius: 8px;
  border-left: 4px solid #666;
}

.empresa, .organizacion-nombre {
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

.experiencia-total {
  margin-top: 2rem;
  padding: 1rem;
  background-color: #3d3d3d;
  border-radius: 5px;
  text-align: center;
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

