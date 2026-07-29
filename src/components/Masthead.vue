<template>
  <header class="masthead text-center text-white d-flex" id="page-top">
    <div class="container my-auto">
      <div class="row">
        <div class="col-lg-8 mx-auto">
          <h1 class="text-uppercase">
            <strong>My name is Chad</strong><br/>
          </h1>
          <h3>I'm a web developer</h3>
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
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
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
