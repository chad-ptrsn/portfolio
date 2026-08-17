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
          <div class="card mb-4 box-shadow">
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

              <button class="project-cta" @click="openProject(project)">
                View project
              </button>
            </div>
          </div>
        </div>
      </div>

      <ProjectDetail
        v-if="selectedProject"
        :project="selectedProject"
        @close="selectedProject = null"
      />
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ProjectDetail from './ProjectDetail.vue'

const selectedProject = ref(null)

const openProject = (project) => {
  selectedProject.value = project
}

const projects = ref([
  {
    id: 1,
    title: 'Patient Scheduling Experience - HealthPartners',
    subtitle: 'Online Appointment Scheduling Suite',
    technologies: ['Vue', 'Nuxt', 'TypeScript', 'Spring Boot', 'REST APIs'],
    overview: 'Creating a personalized, accessible digital experience for patients navigating healthcare workflows.',
    challenge: 'The patient experience needed to support a variety of healthcare workflows while remaining simple and approachable for patients. Different answers could change which questions appeared next, while authenticated patients could have information from their existing profile used to personalize the experience. The challenge was creating a flexible experience without building a separate, hard-coded interface for every possible workflow. The scheduling experience needed to support a full end-to-end patient journey: selecting the correct appointment type, choosing a doctor, location, and time slot, collecting demographic and insurance information, scheduling the appointment, and presenting a final confirmation screen. Each step had its own complexity, but the overall experience needed to feel like a single, cohesive flow. The challenge was building a system that could support multiple distinct domains (search, scheduling, patient intake, confirmation) without becoming a tightly coupled monolith that was difficult to scale or maintain.',
    approach: 'I helped build a configuration-driven experience where a JSON decision tree defined the flow of the application. Rather than embedding every possible path directly into Vue components, the application interpreted the configuration and dynamically rendered the appropriate questions and UI components. This allowed the same underlying application architecture to support different workflows while keeping the interface focused on presenting the right information at the right time. For authenticated experiences, existing patient information could be incorporated into the flow, allowing questions to be personalized and reducing the amount of information patients needed to provide themselves. I worked on a micro-frontend architecture where each major part of the scheduling journey was implemented as an independent application, composed together into a unified patient experience. Each micro frontend owned a specific domain of the workflow—for example appointment selection, patient intake, or confirmation—while sharing a consistent design system and communication patterns. A shared orchestration layer managed navigation between micro frontends, ensuring state could be passed reliably between steps in the scheduling flow without tightly coupling the applications together.',
    decisions: [
      'Configuration over hard-coded workflows',
      'Reusable UI components',
      'Personalized experiences',
      'Accessibility as part of the experience',
      'Micro-frontend architecture',
      'Orchestrated navigation and shared state',
      'Consistent UI through a shared component system',
      'API-driven workflow integration',
      'Accessibility and form-heavy interaction design'
    ],
    result: 'The resulting architecture created a flexible patient-facing experience capable of supporting multiple workflows while maintaining a consistent UI. The configuration-driven approach also reduced the amount of workflow-specific logic embedded within individual components, making the application easier to evolve and maintain. The final system delivered a seamless appointment scheduling experience while maintaining a modular architecture behind the scenes. By splitting the application into micro frontends aligned to business domains, the platform was able to scale more effectively and reduce coupling between complex parts of the scheduling workflow. The orchestration layer ensured the user still experienced a single continuous journey, despite the underlying system being composed of multiple independent applications.',
    learned: 'One of the biggest lessons from this project was recognizing that complex workflows don\'t necessarily need complex interfaces. By separating what the application needs to ask from how the application presents it, the UI could remain relatively simple while the underlying experience supported significantly more complex decision paths. That approach has influenced how I think about building interfaces for any product where the user\'s journey changes based on context or previous decisions. This project reinforced the value of aligning architecture with business domains rather than technical convenience. Micro frontends introduced additional complexity in orchestration and state management, but that cost was offset by the ability to scale different parts of the scheduling journey independently. It also highlighted an important distinction: a user should experience a single cohesive product, even if the system behind it is highly distributed. Designing for that separation—between user experience continuity and system modularity—was one of the most important takeaways from this work.',
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
    title: 'Registration Experience - HealthPartners',
    subtitle: 'Enabling members and patients to register for wellbeing incentives and access their healthcare accounts through a guided digital experience.',
    technologies: ['Vue', 'Nuxt', 'TypeScript', 'Spring Boot', 'REST APIs'],
    overview: 'Enabling members and patients to register for wellbeing incentives and access their healthcare accounts through a guided digital experience.',
    challenge: 'The platform supported two closely related but distinct journeys: wellbeing incentive registration for members and patient account registration and access. Each journey required users to answer a series of questions that determined eligibility, next steps, and the type of account or programme they would be enrolled into. The experience needed to adapt dynamically based on user input while remaining simple and easy to follow. The challenge was building a single system that could support multiple registration flows without creating separate, hard-coded applications for each journey.',
    approach: 'The application was built around a JSON-driven decision tree that defined the structure of each registration journey, including questions, possible responses, and resulting paths. Instead of implementing each registration flow as a separate Vue application, the front-end interpreted the configuration at runtime and rendered the appropriate screens and components based on the current state of the journey. This allowed both member incentive registration and patient account registration to be supported within a shared architecture, while still allowing each flow to behave differently where required.',
    decisions: [
      'Configuration-driven registration flows',
      'Shared component system',
      'Separation of concerns',
      'Accessibility and usability'
    ],
    result: 'The platform provided a unified system for handling both member wellbeing incentive registration and patient account access journeys. The configuration-driven approach allowed new registration flows to be introduced or existing ones modified without requiring significant changes to the underlying application structure. The result was a flexible, maintainable system that supported multiple healthcare registration use cases while keeping the user experience consistent and straightforward.',
    learned: 'This project reinforced how powerful it is to treat registration and onboarding as configurable journeys rather than fixed forms. By separating the rules of the journey from the interface itself, the system could evolve alongside changing healthcare requirements without becoming tightly coupled or difficult to extend.',
    details: [
      'Designed and implemented registration flows using a JSON-driven decision tree.',
      'Built reusable Vue components for common registration steps, inputs, and confirmation screens.',
      'Supported multiple member and patient registration journeys within a shared architecture.',
      'Separated registration rules, orchestration, and UI presentation to improve maintainability.',
      'Created accessible, easy-to-follow forms and step flows to reduce user friction and cognitive load.',
      'Integrated the front-end with backend services and Spring Boot APIs to support end-to-end registration experiences.'
    ],
    experience: 'This project reinforced the value of configurable onboarding journeys for healthcare applications and the importance of keeping the user experience clear, accessible, and adaptable.'
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

.row > .col-lg-6,
.row > .col-sm-6 {
  display: flex;
}

.row {
  gap: 1rem 0;
}

.card {
  display: flex;
  width: 100%;
  height: 100%;
  border: none;
  border-radius: 0.5rem;
  overflow: hidden;
  transition: all 0.3s ease;
  background-color: #fff;
}

.card:hover {
  box-shadow: none;
  transform: none;
}

.card-img-top {
  height: 250px;
  object-fit: cover;
}

.card-body {
  display: flex;
  flex-direction: column;
  flex: 1;
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

.project-cta {
  margin-top: auto;
  border: none;
  background: #CD853F;
  color: white;
  font-weight: 700;
  padding: 0.75rem 1rem;
  border-radius: 0.5rem;
  cursor: pointer;
  transition: background 0.2s ease;
}

.project-cta:hover {
  background: #c77a2d;
}

a {
  text-decoration: none;
  color: inherit;
}

@media (max-width: 768px) {
  .row {
    gap: 1rem 0;
  }

  .section-heading {
    font-size: 1.75rem;
  }
}
</style>
