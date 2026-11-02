<script setup>
defineProps({
  project: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <article class="project-card">
    <div class="card-meta">
      <span class="category-badge">{{ project.category }}</span>
      <span class="source-tag">{{ project.sourceType }}</span>
    </div>

    <h2 class="project-title">{{ project.title }}</h2>
    <p class="project-desc">{{ project.description }}</p>

    <div class="tag-group">
      <span v-for="tag in project.tags" :key="tag" class="tag">
        #{{ tag }}
      </span>
    </div>

    <div class="card-action">
      <a :href="project.demoUrl" target="_blank" rel="noopener" class="demo-link">
        查看示範連結 →
      </a>
    </div>
  </article>
</template>

<style scoped>
.project-card {
  background-color: #ffffff;
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  transition: transform 0.2s, box-shadow 0.2s;
}

.project-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05);
}

.card-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.75rem;
}

.category-badge {
  font-size: 0.8rem;
  font-weight: 600;
  color: #0284c7;
  background-color: #e0f2fe;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
}

.source-tag {
  font-size: 0.75rem;
  color: #94a3b8;
}

.project-title {
  font-size: 1.25rem;
  color: #0f172a;
  margin-bottom: 0.75rem;
}

.project-desc {
  color: #475569;
  font-size: 0.95rem;
  line-height: 1.6;
  flex: 1;
  margin-bottom: 1.25rem;
}

.tag-group {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-bottom: 1.25rem;
}

.tag {
  font-size: 0.8rem;
  background-color: #f1f5f9;
  color: #475569;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
}

.card-action {
  border-top: 1px solid #f1f5f9;
  padding-top: 1rem;
}

.demo-link {
  color: #00dc82;
  font-weight: 600;
  text-decoration: none;
  font-size: 0.95rem;
}

.demo-link:hover {
  text-decoration: underline;
}
</style>

