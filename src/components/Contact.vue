<template>
  <section id="contact" class="py-5">
    <div class="container">
      <div class="row">
        <div class="col-lg-8 mx-auto text-center">
          <h2 class="section-heading">Let's Get In Touch!</h2>
          <hr class="my-4">
          <p class="mb-5">Ready to start your next project? That's great! Send me an email and I'll get back to you!</p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-3 mx-auto text-center">
          <a href="resume/Chad_Petersen_Resume.pdf" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-file fa-3x mb-3"></i>
            <p>View/download resume</p>
          </a>
        </div>
        <div class="col-lg-3 mx-auto text-center">
          <a href="mailto:chadptrsn@gmail.com">
            <i class="fas fa-envelope fa-3x mb-3"></i>
            <p>Email</p>
          </a>
        </div>
        <div class="col-lg-3 mx-auto text-center">
          <a href="https://www.linkedin.com/in/chad-petersen-7ba8b630/" target="_blank" rel="noopener noreferrer">
            <i class="fab fa-linkedin fa-3x mb-3"></i>
            <p>LinkedIn</p>
          </a>
        </div>
        <div class="col-lg-3 mx-auto text-center">
          <a href="https://github.com/chad-ptrsn" target="_blank" rel="noopener noreferrer">
            <i class="fab fa-github-square fa-3x mb-3"></i>
            <p>GitHub</p>
          </a>
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

a {
  color: #CD853F;
  text-decoration: none;
  transition: color 0.3s ease;
}

a:hover {
  color: #c77a2d;
}

a i {
  color: #CD853F;
  transition: color 0.3s ease;
}

a:hover i {
  color: #c77a2d;
}

p {
  margin-top: 1rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .section-heading {
    font-size: 1.75rem;
  }
  
  .col-lg-3 {
    margin-bottom: 2rem;
  }
}
</style>
