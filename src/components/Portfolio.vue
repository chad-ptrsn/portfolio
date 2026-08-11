<template>
  <section class="bg-dark text-white" id="portfolio">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading">Recent work</h2>
          <hr class="my-4">
        </div>
      </div>
      <div class="row">
        <div class="col-lg-6 col-sm-6" v-for="project in projects" :key="project.id">
          <a :href="project.url" target="_blank" rel="noopener noreferrer">
            <div class="card mb-4 box-shadow">
              <img class="card-img-top" :src="project.image" :alt="project.title">
              <div class="card-body">
                <p><strong>{{ project.title }}</strong></p>
                <ul class="text-muted mb-0">
                  <li v-for="tech in project.technologies" :key="tech">{{ tech }}</li>
                </ul>
              </div>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const projects = ref([
  {
    id: 1,
    title: 'Healthpartners Wellbeing registration',
    url: 'https://www.healthpartners.com/wellbeing-registration/wellbeing/company-info',
    image: '/img/portfolio/wb-registration.jpg',
    technologies: ['React', 'Redux', 'NodeJS', 'Webpack', 'Bootstrap', 'HP brand']
  },
  {
    id: 2,
    title: 'Healthpartners registration',
    url: 'https://www.healthpartners.com/public/register/signUpLanding.html',
    image: '/img/portfolio/hp-registration.jpg',
    technologies: ['NodeJS', 'Webpack', 'Bootstrap', 'HP brand']
  }
])
</script>

<style scoped>
.bg-dark {
  background-color: #868e96 !important;
}

.section-heading {
  font-size: 2.5rem;
  font-weight: 700;
  color: white;
}

hr.light {
  border-color: rgba(255, 255, 255, 0.3);
}

hr {
  border-color: rgba(255, 255, 255, 0.5);
  border-width: 3px;
  max-width: 80px;
  margin-left: auto;
  margin-right: auto;
}

.card {
  border: none;
  border-radius: 0.5rem;
  overflow: hidden;
  transition: all 0.3s ease;
  background-color: #fff;
}

.card:hover {
  box-shadow: 0 1rem 3rem rgba(0, 0, 0, 0.5);
  transform: translateY(-10px);
}

.card-img-top {
  height: 250px;
  object-fit: cover;
}

.card-body {
  color: #212529;
}

.card-body p {
  margin-bottom: 1rem;
  font-weight: 600;
}

.text-muted {
  color: #adb5bd !important;
}

.list-unstyled li {
  padding: 0.25rem 0;
  font-size: 0.9rem;
}

a {
  text-decoration: none;
  color: inherit;
}

@media (max-width: 768px) {
  .section-heading {
    font-size: 1.75rem;
  }
}
</style>
