<template>
  <nav class="navbar navbar-expand-lg navbar-light fixed-top" id="mainNav">
    <div class="container">
      <a class="navbar-brand scroll-trigger" href="#page-top">Chad Petersen</a>
      <button class="navbar-toggler navbar-toggler-right" type="button" @click="toggleMenu" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" :class="{ show: menuOpen }" id="navbarResponsive">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link scroll-trigger" href="#about" @click="scrollTo('#about')">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link scroll-trigger" href="#services" @click="scrollTo('#services')">Things I like</a>
          </li>
          <li class="nav-item">
            <a class="nav-link scroll-trigger" href="#portfolio" @click="scrollTo('#portfolio')">Recent work</a>
          </li>
          <li class="nav-item">
            <a class="nav-link scroll-trigger" href="#contact" @click="scrollTo('#contact')">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen = ref(false)

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}

const scrollTo = (selector) => {
  menuOpen.value = false
  const element = document.querySelector(selector)
  if (element) {
    const offsetTop = element.offsetTop - 56
    window.scrollTo({ top: offsetTop, behavior: 'smooth' })
  }
}

const handleScroll = () => {
  const navbar = document.getElementById('mainNav')
  if (window.scrollY > 100) {
    navbar?.classList.add('navbar-shrink')
  } else {
    navbar?.classList.remove('navbar-shrink')
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.navbar-brand {
  font-size: 1.5rem;
  font-weight: 700;
  text-decoration: none;
}

#mainNav {
  background-color: #fff;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  transition: background-color 0.3s ease-in-out;
}

#mainNav.navbar-shrink {
  background-color: #fff;
  padding: 0.5rem 0;
}

.navbar-light .navbar-brand {
  color: #212529;
  font-weight: 700;
  text-transform: uppercase;
}

.navbar-light .navbar-nav .nav-link {
  color: #212529;
  font-size: 0.9rem;
  font-weight: 500;
  margin-left: 0.5rem;
  transition: color 0.3s ease-in-out;
}

.navbar-light .navbar-nav .nav-link:hover {
  color: #0066cc;
}

.navbar-light .navbar-nav .nav-link.active {
  color: #0066cc;
  font-weight: 700;
}
</style>
