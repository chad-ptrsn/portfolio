<template>
  <section class="bg-dark text-white" id="about">
    <div class="container">
      <div class="row">
        <div class="col-lg-8 mx-auto text-center">
          <h2 class="section-heading mb-4">A little bit about me</h2>
          <hr class="light my-4">
            <p class="text-white-75 mb-4">
              I'm a frontend software engineer with 15 years of experience building web applications that balance clean architecture, thoughtful user experiences, and maintainable code.
              Throughout my career I've worked across legacy platforms and modern JavaScript frameworks, helping teams deliver new features, improve existing applications, and modernize frontend experiences.
            </p>
            <hr class="light my-4">
            <p class="text-white-75 mb-4">
              Most recently I've been building applications with TypeScript, Nuxt, and Vue while working in collaborative Agile environments alongside designers, QA engineers, and backend developers.
              I enjoy solving complex problems, simplifying user workflows, and writing code that's easy to understand and maintain. Whether I'm implementing new features, improving performance, or refactoring existing applications, I care about building software that provides real value to the people using it.
          </p>
          <hr class="light my-4"/>
          <p class="text-white-75 mb-4">Outside of work I'm passionate about the outdoors. Trail running, mountain biking, hiking, snowboarding, fly fishing, and exploring remote places have become a major influence on where I want to take my career next. I'm actively expanding my skills in mapping technologies and location-based applications while building personal projects that combine software development with outdoor adventure.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.bg-dark {
  background-color: #868e96 !important;
}

.section-heading {
  font-size: 2.5rem;
  font-weight: 700;
}

.text-white-75 {
  color: rgba(255, 255, 255, 0.75);
  font-size: 1.125rem;
  line-height: 1.8;
}

hr.light {
  border-color: rgba(255, 255, 255, 0.3);
  border-width: 3px;
  max-width: 80px;
  margin-left: auto;
  margin-right: auto;
}
</style>
