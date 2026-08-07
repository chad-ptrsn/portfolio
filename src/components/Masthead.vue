<template>
  <header class="masthead text-center text-white d-flex" id="page-top">
    <div class="container my-auto">
      <div class="row">
        <div class="col-lg-8 mx-auto">
          <h1 class="text-uppercase">
            <strong>Chad Petersen</strong><br/>
          </h1>
          <h2>Front-End Engineer</h2>
          <p class="text-white-75 mb-4">Building thoughtful digital experiences that turn complex problems into simple, intuitive products. With 15 years of experience creating performant, accessible web applications across healthcare, outdoor adventure, and the web.</p>
          <a class="btn btn-primary btn-xl scroll-trigger" href="#about" @click="scrollTo('#about')">About me</a>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
const scrollTo = (selector) => {
  const element = document.querySelector(selector)
  if (element) {
    const offsetTop = element.offsetTop - 56
    window.scrollTo({ top: offsetTop, behavior: 'smooth' })
  }
}
</script>

<style scoped>
.masthead {
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.65) 0%, rgba(118, 75, 162, 0.65) 100%),
    url('/img/banner.jpg');
  background-position: center center;
  background-size: cover;
  min-height: 100vh;
}

.masthead h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.masthead h3 {
  font-size: 1.5rem;
  font-weight: 300;
  margin-bottom: 2rem;
}

.btn-xl {
  padding: 1.25rem 2.5rem;
  font-size: 1.125rem;
  font-weight: 700;
}
</style>
