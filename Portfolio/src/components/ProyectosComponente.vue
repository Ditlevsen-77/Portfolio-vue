<script setup>
import { ref } from 'vue'

const proyectos = ref([
  {
    nombre: "Ad Astra",
    tipo: "Videojuego",
    descripcion: "Videojuego de aventura espacial desarrollado con mi equipo de programadores. Combina elementos de exploración y estrategia en un universo futurista.",
    tecnologias: ["Unity", "C#", "JavaScript"],
    estado: "En desarrollo"
  },
  {
    nombre: "Sistema de Gestión Comercial",
    tipo: "Aplicación Web",
    descripcion: "Sistema completo para gestión de inventario y ventas desarrollado para carnicería local. Incluye módulos de stock, facturación y reportes.",
    tecnologias: ["Vue.js", "Node.js", "MongoDB"],
    estado: "Completado"
  },
  {
    nombre: "Herramientas Contables",
    tipo: "Software de Escritorio",
    descripcion: "Suite de herramientas personalizadas para facilitar el trabajo contable. Incluye calculadora de impuestos y gestor de clientes.",
    tecnologias: ["Python", "Tkinter", "SQLite"],
    estado: "En mantenimiento"
  }
])
</script>

<template>
  <section id="proyectos" class="section">
    <h2>Proyectos</h2>
    <div class="proyectos-grid">
      <div v-for="proyecto in proyectos" :key="proyecto.nombre" class="proyecto-item">
        <div class="proyecto-header">
          <h3>{{ proyecto.nombre }}</h3>
          <span class="proyecto-tipo">{{ proyecto.tipo }}</span>
        </div>
        <p class="proyecto-descripcion">{{ proyecto.descripcion }}</p>
        <div class="proyecto-tecnologias">
          <span v-for="tech in proyecto.tecnologias" :key="tech" class="tech-tag">
            {{ tech }}
          </span>
        </div>
        <div class="proyecto-estado">
          <span class="estado-badge" :class="proyecto.estado.toLowerCase().replace(' ', '-')">
            {{ proyecto.estado }}
          </span>
        </div>
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

.proyectos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.proyecto-item {
  padding: 2rem;
  background-color: #3d3d3d;
  border-radius: 12px;
  border-left: 4px solid #42b883;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.proyecto-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(66, 184, 131, 0.2);
  background-color: #4d4d4d;
}

.proyecto-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.proyecto-header h3 {
  color: #42b883;
  font-size: 1.4rem;
  margin: 0;
}

.proyecto-tipo {
  background-color: #42b883;
  color: #1a1a1a;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: bold;
}

.proyecto-descripcion {
  color: #cccccc;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.proyecto-tecnologias {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.tech-tag {
  background-color: #555;
  color: #ffffff;
  padding: 0.3rem 0.8rem;
  border-radius: 12px;
  font-size: 0.8rem;
  border: 1px solid #666;
}

.proyecto-estado {
  display: flex;
  justify-content: flex-end;
}

.estado-badge {
  padding: 0.4rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: bold;
  text-transform: uppercase;
}

.en-desarrollo {
  background-color: #ffa726;
  color: #1a1a1a;
}

.completado {
  background-color: #4caf50;
  color: #ffffff;
}

.en-mantenimiento {
  background-color: #2196f3;
  color: #ffffff;
}

@media (max-width: 768px) {
  .section {
    padding: 1rem;
  }
  
  .proyectos-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .proyecto-item {
    padding: 1.5rem;
  }
  
  .proyecto-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .section {
    padding: 1.5rem;
  }
  
  .section h2 {
    font-size: 1.8rem;
  }
  
  .proyectos-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}


.proyecto-item {
  animation: slideInUp 0.6s ease-out;
}

.proyecto-item:nth-child(1) { animation-delay: 0.1s; }
.proyecto-item:nth-child(2) { animation-delay: 0.2s; }
.proyecto-item:nth-child(3) { animation-delay: 0.3s; }

@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>


