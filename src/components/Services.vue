<template>
  <section id="services" class="py-5">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading">What I like about web development</h2>
          <hr class="my-4">
        </div>
      </div>
      <div class="row">
        <div class="col-lg-4 col-md-6 text-center">
          <div class="service-box mt-5 mx-auto">
            <i class="fas fa-4x fa-code text-primary mb-3"></i>
            <h3 class="mb-3">Code</h3>
            <ul class="list-unstyled text-muted mb-0">
              <li>HTML</li>
              <li>CSS/SCSS</li>
              <li>VueJS</li>
              <li>React</li>
              <li>JavaScript</li>
              <li>NodeJS</li>
              <li>Typescript</li>
            </ul>
          </div>
        </div>
        <div class="col-lg-4 col-md-6 text-center">
          <div class="service-box mt-5 mx-auto">
            <i class="fas fa-4x fa-wrench text-primary mb-3"></i>
            <h3 class="mb-3">Tools</h3>
            <ul class="list-unstyled text-muted mb-0">
              <li>VS Code</li>
              <li>Git</li>
              <li>Vite</li>
              <li>Postman</li>
              <li>Chrome dev tools</li>
              <li>Docker</li>
            </ul>
          </div>
        </div>
        <div class="col-lg-4 col-md-6 text-center">
          <div class="service-box mt-5 mx-auto">
            <i class="fas fa-4x fa-tablet text-primary mb-3"></i>
            <h3 class="mb-3">UI</h3>
            <ul class="list-unstyled text-muted mb-0">
              <li>Responsive design</li>
              <li>Web components</li>
              <li>Rapid prototyping</li>
              <li>Reusable components</li>
              <li>UI patterns</li>
              <li>Accessibility</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.section-heading {
  font-size: 2.5rem;
  font-weight: 700;
  color: #212529;
}

hr {
  border-color: #CD853F;
  border-width: 3px;
  max-width: 80px;
  margin-left: auto;
  margin-right: auto;
}

.service-box {
  max-width: 400px;
  padding: 2rem;
  border-radius: 0.5rem;
  transition: all 0.3s ease;
}

.service-box:hover {
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  transform: translateY(-5px);
}

.service-box i {
  color: #CD853F;
}

.text-primary {
  color: #CD853F !important;
}

.service-box h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #212529;
}

.text-muted {
  color: #6c757d !important;
}

.list-unstyled li {
  padding: 0.25rem 0;
}

@media (max-width: 768px) {
  .section-heading {
    font-size: 1.75rem;
  }
}
</style>
