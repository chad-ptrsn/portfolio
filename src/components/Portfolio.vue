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
          <!-- <a :href="project.url" target="_blank" rel="noopener noreferrer"> -->
            <div class="card mb-4 box-shadow">
              <!-- <img class="card-img-top" :src="project.image" :alt="project.title"> -->
              <div class="card-body">
                <p><strong>{{ project.title }}</strong></p>
                <p v-if="project.technologies" class="tech-stack text-muted mb-2">
                  {{ project.technologies.join(' / ') }}
                </p>
                <p v-if="project.overview" class="project-overview mb-3">
                  {{ project.overview }}
                </p>
                <ul v-if="project.details" class="project-details mt-3 mb-0">
                  <li v-for="detail in project.details" :key="detail">{{ detail }}</li>
                </ul>
                <p v-if="project.experience" class="project-experience mt-3 mb-0">
                  {{ project.experience }}
                </p>
              </div>
            </div>
          <!-- </a> -->
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
    title: 'Patient Scheduling Experience - HealthPartners',
    technologies: ['Nuxt', 'Vue', 'TypeScript', 'REST APIs'],
    overview: 'The Patient Experience Platform was a collection of patient-facing healthcare applications designed to guide users through personalized workflows and online scheduling experiences.',
    details: [
      'Developed patient-facing experiences using Nuxt, Vue, and TypeScript.',
      'Built reusable Vue components to support dynamic questions, forms, and workflow steps.',
      'Implemented a JSON-driven decision flow where API responses and configuration flags determined the next step in the patient journey.',
      'Built personalized authenticated experiences by retrieving patient profile information and using it to pre-populate relevant form data and personalize questions.',
      'Created reusable Vue composables to standardize API communication, loading and posting states, and error handling.',
      'Established consistent parent-child component patterns using props to pass dynamic content, questions, and available answers between components.',
      'Integrated frontend applications with REST APIs and collaborated with backend developers, QA, designers, and product stakeholders.',
      'Built accessible patient workflows following web accessibility (A11y) standards, ensuring dynamic forms, questions, and interactive components remained usable with assistive technologies.'
    ],
    experience: 'This work provided experience building complex, data-driven patient experiences where reusable frontend architecture and predictable workflows were essential to maintaining multiple healthcare applications.'
  },
  {
    id: 2,
    title: 'Registration experiences - HealthPartners',
    image: '/img/portfolio/wb-registration.jpg',
    technologies: ['React', 'Redux', 'Node.js', 'Webpack', 'Bootstrap'],
    overview: 'I contributed to the development of two patient-facing registration applications that provided users with a streamlined way to create accounts and gain access to healthcare and wellbeing platforms.',
    details: [
      'Developed patient-facing registration experiences using React and Redux.',
      'Built reusable React components to support registration workflows and user input.',
      'Managed application and registration state using Redux.',
      'Integrated frontend experiences with backend services through Node.js.',
      'Worked within a Webpack-based frontend architecture.',
      'Used Bootstrap to create responsive and consistent user interfaces.',
      'Collaborated with designers, backend developers, QA, and product stakeholders to deliver patient-facing experiences.',
      'Developed accessible, responsive patient-facing experiences following web accessibility (A11y) standards to support an inclusive experience across devices and assistive technologies.'
    ],
    experience: 'These projects provided experience developing production React applications within a healthcare environment, including working with shared frontend patterns, application state, backend integrations, and cross-functional development teams.'
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

.tech-stack {
  font-size: 0.9rem;
  line-height: 1.5;
}

.project-overview,
.project-experience {
  font-size: 0.8rem;
  line-height: 1.5;
  color: #212529;
}

.project-details {
  padding-left: 1.25rem;
  color: #212529;
  font-size: 0.85rem;
  line-height: 1.6;
}

.project-details li {
  margin-bottom: 0.5rem;
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
