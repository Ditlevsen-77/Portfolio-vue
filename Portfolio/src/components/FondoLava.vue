<template>
  <div class="lava-container">
    <div class="lava-blob blob-1"></div>
    <div class="lava-blob blob-2"></div>
    <div class="lava-blob blob-3"></div>
    <div class="lava-blob blob-4"></div>
    <div class="lava-blob blob-5"></div>
  </div>
</template>

<style scoped>
.lava-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 20px;
  z-index: 1;
}

.lava-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(35px);
  animation: lava-flow 8s ease-in-out infinite;
  opacity: 0.9;
  mix-blend-mode: screen;
}

.blob-1 {
  width: 250px;
  height: 250px;
  background: linear-gradient(45deg, #ff6b6b, #ff8e8e, #ffa8a8);
  top: -60px;
  left: -60px;
  animation-delay: 0s;
}

.blob-2 {
  width: 180px;
  height: 180px;
  background: linear-gradient(45deg, #4ecdc4, #44a08d, #26d0ce);
  top: 40px;
  right: -40px;
  animation-delay: 2s;
}

.blob-3 {
  width: 220px;
  height: 220px;
  background: linear-gradient(45deg, #a8edea, #fed6e3, #d299c2);
  bottom: -50px;
  left: 15%;
  animation-delay: 4s;
}

.blob-4 {
  width: 150px;
  height: 150px;
  background: linear-gradient(45deg, #ff9a9e, #fecfef, #ffb3ba);
  top: 25%;
  left: 65%;
  animation-delay: 6s;
}

.blob-5 {
  width: 200px;
  height: 200px;
  background: linear-gradient(45deg, #667eea, #764ba2, #9c27b0);
  bottom: 15%;
  right: 15%;
  animation-delay: 1s;
}

@keyframes lava-flow {
  0%, 100% {
    transform: translate(0, 0) scale(1) rotate(0deg);
  }
  25% {
    transform: translate(30px, -40px) scale(1.2) rotate(90deg);
  }
  50% {
    transform: translate(-20px, 30px) scale(0.8) rotate(180deg);
  }
  75% {
    transform: translate(40px, 15px) scale(1.1) rotate(270deg);
  }
}

/* Animación adicional para movimiento más fluido */
.blob-1 {
  animation: lava-flow 12s ease-in-out infinite;
}

.blob-2 {
  animation: lava-flow 10s ease-in-out infinite reverse;
}

.blob-3 {
  animation: lava-flow 14s ease-in-out infinite;
}

.blob-4 {
  animation: lava-flow 9s ease-in-out infinite reverse;
}

.blob-5 {
  animation: lava-flow 11s ease-in-out infinite;
}

/* Efecto de pulsación */
@keyframes pulse {
  0%, 100% {
    opacity: 0.6;
  }
  50% {
    opacity: 0.9;
  }
}

.lava-blob {
  animation: lava-flow 8s ease-in-out infinite, pulse 4s ease-in-out infinite;
}

/* Responsive */
@media (max-width: 768px) {
  .lava-blob {
    filter: blur(30px);
  }
  
  .blob-1, .blob-3 {
    width: 120px;
    height: 120px;
  }
  
  .blob-2, .blob-4, .blob-5 {
    width: 80px;
    height: 80px;
  }
}
</style>
