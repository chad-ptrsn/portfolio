<template>
  <NavBar />
  <Masthead />
  <About />
  <Services />
  <Portfolio />
  <Contact />
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import Masthead from './components/Masthead.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
import Portfolio from './components/Portfolio.vue'
import Contact from './components/Contact.vue'
</script>

<style>
body {
  font-family: 'Open Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}
</style>
