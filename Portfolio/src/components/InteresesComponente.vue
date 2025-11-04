<script setup>
import { ref } from 'vue'
import FondoLava from './FondoLava.vue'

const intereses = ref([
  "Desarrollo de videojuegos de calidad",
  "Entretenimiento digital",
  "Programación creativa",
  "Tecnología emergente"
])
</script>

<template>
  <section id="intereses" class="section">
    <h2>Intereses Personales</h2>
    <div class="intereses-container">
      <FondoLava />
      <div class="intereses-content">
        <div v-for="interes in intereses" :key="interes" class="interes-item">
          {{ interes }}
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

.intereses-container {
  position: relative;
  min-height: 350px;
  border-radius: 20px;
  overflow: hidden;
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 50%, #2d2d2d 100%);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.intereses-content {
  position: relative;
  z-index: 2;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  height: 100%;
  min-height: 300px;
}

.interes-item {
  padding: 1.5rem;
  background-color: rgba(30, 30, 30, 0.9);
  border-radius: 15px;
  border-left: 4px solid #42b883;
  color: #ffffff;
  font-size: 1.1rem;
  font-weight: 500;
  backdrop-filter: blur(15px);
  transition: all 0.3s ease;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(66, 184, 131, 0.2);
}

.interes-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(66, 184, 131, 0.3);
  background-color: rgba(66, 184, 131, 0.1);
}

@media (max-width: 768px) {
  .section {
    padding: 1rem;
  }
  
  .intereses-container {
    min-height: 250px;
  }
  
  .intereses-content {
    padding: 1.5rem;
    gap: 1rem;
  }
  
  .interes-item {
    padding: 1rem;
    font-size: 1rem;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .section {
    padding: 1.5rem;
  }
  
  .section h2 {
    font-size: 1.8rem;
  }
  
  .intereses-container {
    min-height: 280px;
  }
}


.interes-item {
  animation: slideInUp 0.6s ease-out;
}

.interes-item:nth-child(1) { animation-delay: 0.1s; }
.interes-item:nth-child(2) { animation-delay: 0.2s; }
.interes-item:nth-child(3) { animation-delay: 0.3s; }
.interes-item:nth-child(4) { animation-delay: 0.4s; }

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
