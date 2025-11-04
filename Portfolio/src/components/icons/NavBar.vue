<script setup>
import { ref } from 'vue'
import profileImage from '../../assets/images/Perfil.png'

const datosPersonales = ref({
  nombre: "Ian Ditlevsen"
})

const isOpen = ref(false)

const menuItems = ref([
  { id: 'datos-personales', label: 'Datos Personales' },
  { id: 'educacion', label: 'Educación' },
  { id: 'experiencia', label: 'Experiencia' },
  { id: 'proyectos', label: 'Proyectos' },
  { id: 'habilidades', label: 'Habilidades' },
  { id: 'intereses', label: 'Intereses' },
  { id: 'contacto', label: 'Contacto' }
])

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <nav class="navbar">
    <div class="navbar-row">
      <div class="navbar-brand">
        <img :src="profileImage" alt="Foto de perfil" class="profile-img" />
        <h1>{{ datosPersonales.nombre }}</h1>
      </div>
      <button
        class="navbar-toggle"
        aria-label="Abrir menú"
        aria-expanded="false"
        @click="isOpen = !isOpen"
      >
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </button>
    </div>
    <div class="navbar-menu" :class="{ open: isOpen }">
      <ul>
        <li v-for="item in menuItems" :key="item.id">
          <a 
            :href="`#${item.id}`" 
            class="navbar-item"
            @click.prevent="(isOpen = false, scrollToSection(item.id))"
          >
            {{ item.label }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background-color: #2d2d2d;
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 1px solid #444;
  width: 100%;
  box-sizing: border-box;
}

.navbar-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

.navbar-brand {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.profile-img {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #42b883;
}

.navbar-brand h1 {
  color: #42b883;
  font-size: 1.5rem;
  margin: 0;
}

.navbar-menu ul {
  list-style: none;
  display: flex;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.navbar-item {
  color: #cccccc;
  text-decoration: none;
  transition: color 0.3s ease;
  cursor: pointer;
}

.navbar-item:hover {
  color: #ffffff;
}


.navbar-toggle {
  display: none;
  background: transparent;
  border: none;
  cursor: pointer;
}

.navbar-toggle .bar {
  display: block;
  width: 24px;
  height: 2px;
  background: #fff;
  margin: 5px 0;
}

@media (max-width: 768px) {
  .navbar {
    padding: 1rem;
  }

  .navbar-toggle { display: inline-block; }

  .navbar-menu { display: none; }
  .navbar-menu.open { display: block; }

  .navbar-menu ul {
    flex-direction: column;
    gap: 1rem;
    margin-top: 0.5rem;
  }
}
</style>
