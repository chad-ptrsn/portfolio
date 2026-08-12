<template>
  <section v-if="project" class="project-detail">
    <div class="detail-header">
      <div>
        <p class="eyebrow">{{ project.technologies.join(' / ') }}</p>
        <h3>{{ project.title }}</h3>
        <p v-if="project.subtitle" class="subtitle">{{ project.subtitle }}</p>
      </div>
      <button type="button" class="close-btn" @click="$emit('close')">Close</button>
    </div>

    <div class="detail-shell">
      <div class="panel intro">
        <p class="panel-label">PROJECT</p>
        <h4>{{ project.overview }}</h4>
      </div>

      <div class="panel">
        <p class="panel-label">THE CHALLENGE</p>
        <p>{{ project.challenge }}</p>
      </div>

      <div class="panel">
        <p class="panel-label">THE APPROACH</p>
        <div class="architecture-box">Architecture / workflow</div>
        <p>{{ project.approach }}</p>
      </div>

      <div class="panel">
        <p class="panel-label">ENGINEERING DECISIONS</p>
        <div class="decision-grid">
          <span v-for="decision in project.decisions" :key="decision">{{ decision }}</span>
        </div>
      </div>

      <div class="panel">
        <p class="panel-label">THE RESULT</p>
        <div class="result-placeholder">Screenshots / outcome</div>
        <p>{{ project.result }}</p>
      </div>

      <div class="panel">
        <p class="panel-label">WHAT I LEARNED</p>
        <p>{{ project.learned }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  project: {
    type: Object,
    default: null
  }
})

defineEmits(['close'])
</script>

<style scoped>
.project-detail {
  margin-top: 2rem;
  border: 1px solid rgba(33, 37, 41, 0.15);
  background: #fff;
  border-radius: 0.75rem;
  overflow: hidden;
  color: #212529;
}

.detail-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  padding: 1.25rem 1.5rem;
  border-bottom: 1px solid rgba(33, 37, 41, 0.15);
  background: #f8f9fa;
}

.eyebrow {
  margin: 0 0 0.35rem;
  font-size: 0.72rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #868e96;
}

.detail-header h3 {
  margin: 0;
  font-size: clamp(1.4rem, 2vw, 2rem);
}

.subtitle {
  margin: 0.35rem 0 0;
  color: #495057;
  font-size: 0.9rem;
  font-weight: 600;
}

.close-btn {
  border: 1px solid #212529;
  background: transparent;
  padding: 0.5rem 0.9rem;
  border-radius: 999px;
  cursor: pointer;
}

.detail-shell {
  display: grid;
  gap: 1rem;
  padding: 1.25rem;
}

.panel {
  border: 1px solid rgba(33, 37, 41, 0.12);
  border-radius: 0.5rem;
  padding: 1.25rem;
  background: #fff;
}

.panel-label {
  margin: 0 0 0.9rem;
  font-size: 0.76rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #868e96;
  font-weight: 700;
}

.intro h4 {
  margin: 0;
  font-size: 1.5rem;
  line-height: 1.4;
}

.panel p {
  margin: 0;
  line-height: 1.7;
}

.architecture-box,
.result-placeholder {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 120px;
  margin-bottom: 1rem;
  background: #f1f3f5;
  border: 1px dashed rgba(33, 37, 41, 0.2);
  border-radius: 0.5rem;
  font-weight: 600;
  color: #495057;
}

.decision-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 0.75rem;
}

.decision-grid span {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 68px;
  padding: 0.5rem;
  border: 1px solid rgba(33, 37, 41, 0.2);
  border-radius: 0.5rem;
  background: #f8f9fa;
  font-weight: 700;
  text-align: center;
}
</style>
