<script setup>
import { ref } from 'vue'

const contactos = ref([
  {
    tipo: "GitHub",
    valor: "Ditlevsen-77",
    url: "https://github.com/Ditlevsen-77",
    icono: "🐙",
    color: "#58a6ff"
  },
  {
    tipo: "Email",
    valor: "ian.ditlevsen.2011@gmail.com",
    url: "mailto:ian.ditlevsen.2011@gmail.com",
    icono: "📧",
    color: "#ff6b6b"
  },
  {
    tipo: "LinkedIn",
    valor: "Ian Ditlevsen",
    url: "https://linkedin.com/in/ian-ditlevsen",
    icono: "💼",
    color: "#0077b5"
  },
  {
    tipo: "Portfolio",
    valor: "Dirección al Perfil del Tutor Dante Martinez",
    url: "https://github.com/mzadante",
    icono: "🌐",
    color: "#42b883"
  }
])
</script>

<template>
  <section id="contacto" class="section">
    <h2>Contacto</h2>
    <div class="contactos-grid">
      <div v-for="contacto in contactos" :key="contacto.tipo" class="contacto-item" :style="{ '--accent-color': contacto.color }">
        <div class="contacto-header">
          <span class="contacto-icon">{{ contacto.icono }}</span>
          <h3>{{ contacto.tipo }}</h3>
        </div>
        <a :href="contacto.url" target="_blank" class="contacto-link" v-if="contacto.url !== '#'">
          {{ contacto.valor }}
        </a>
        <span class="contacto-text" v-else>
          {{ contacto.valor }}
        </span>
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

.contactos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.contacto-item {
  padding: 1.5rem;
  background-color: #1a1a1a;
  border-radius: 12px;
  border-left: 4px solid var(--accent-color);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.contacto-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, var(--accent-color) 0%, transparent 100%);
  opacity: 0.05;
  transition: opacity 0.3s ease;
}

.contacto-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
  background-color: #24292e;
}

.contacto-item:hover::before {
  opacity: 0.1;
}

.contacto-header {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin-bottom: 1rem;
}

.contacto-icon {
  font-size: 1.5rem;
  filter: drop-shadow(0 0 5px var(--accent-color));
}

.contacto-header h3 {
  color: var(--accent-color);
  font-size: 1.2rem;
  margin: 0;
  font-weight: 600;
}

.contacto-link, .contacto-text {
  color: #ffffff;
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  display: block;
  transition: all 0.3s ease;
  position: relative;
  z-index: 1;
}

.contacto-link:hover {
  color: var(--accent-color);
  text-decoration: none;
  transform: translateX(5px);
}

.contacto-text {
  color: #cccccc;
}

@media (max-width: 768px) {
  .section {
    padding: 1rem;
  }
  
  .contactos-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .contacto-item {
    padding: 1.2rem;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .section {
    padding: 1.5rem;
  }
  
  .section h2 {
    font-size: 1.8rem;
  }
  
  .contactos-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Animación de entrada */
.contacto-item {
  animation: slideInUp 0.6s ease-out;
}

.contacto-item:nth-child(1) { animation-delay: 0.1s; }
.contacto-item:nth-child(2) { animation-delay: 0.2s; }
.contacto-item:nth-child(3) { animation-delay: 0.3s; }
.contacto-item:nth-child(4) { animation-delay: 0.4s; }

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
