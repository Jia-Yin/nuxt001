<script setup>
// 原 Vue 作品內容：暱稱與一句話自介
const profile = ref({
  name: '小明 (Alex)',
  role: '前端學習者 / 網頁開發探索者',
  headline: '熱衷於用程式碼打造簡潔、友善的使用者介面。目前正在深入探索 Nuxt 與現代前端生態圈。'
})

// 待新增內容：精選作品亮點預覽
const featuredHighlights = ref([
  {
    id: 1,
    title: 'Vue 互動計數器與待辦清單',
    summary: '上一單元的成果，練習了 Vue 元件拆分與響應式資料綁定。'
  },
  {
    id: 2,
    title: 'Nuxt 4 個人網站架構',
    summary: '運用 Nuxt 的檔案即路由機制，建構乾淨的三頁式網站。'
  }
])
</script>

<template>
  <div class="home-page">
    <section class="hero-section">
      <p class="tagline">{{ profile.role }}</p>
      <h1 class="title">嗨，我是 {{ profile.name }} 👋</h1>
      <p class="headline">{{ profile.headline }}</p>
      
      <div class="action-buttons">
        <NuxtLink to="/projects" class="btn btn-primary">瀏覽作品</NuxtLink>
        <NuxtLink to="/about" class="btn btn-secondary">關於我</NuxtLink>
      </div>
    </section>

    <section class="featured-section">
      <h2>精選亮點</h2>
      <div class="card-grid">
        <div v-for="item in featuredHighlights" :key="item.id" class="card">
          <h3>{{ item.title }}</h3>
          <p>{{ item.summary }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.hero-section {
  text-align: center;
  padding: 3rem 1rem;
  background-color: #ffffff;
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  margin-bottom: 2.5rem;
}

.tagline {
  color: #00dc82;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 0.5rem;
}

.title {
  font-size: 2.25rem;
  color: #0f172a;
  margin-bottom: 1rem;
}

.headline {
  max-width: 600px;
  margin: 0 auto 2rem;
  color: #475569;
  font-size: 1.1rem;
}

.action-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.btn {
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.2s;
}

.btn-primary {
  background-color: #00dc82;
  color: #ffffff;
}

.btn-primary:hover {
  background-color: #00b86c;
}

.btn-secondary {
  background-color: #f1f5f9;
  color: #334155;
  border: 1px solid #cbd5e1;
}

.btn-secondary:hover {
  background-color: #e2e8f0;
}

.featured-section h2 {
  font-size: 1.5rem;
  color: #0f172a;
  margin-bottom: 1.25rem;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.25rem;
}

.card {
  background-color: #ffffff;
  padding: 1.5rem;
  border-radius: 10px;
  border: 1px solid #e2e8f0;
}

.card h3 {
  font-size: 1.15rem;
  color: #1e293b;
  margin-bottom: 0.5rem;
}

.card p {
  color: #64748b;
  font-size: 0.95rem;
}
</style>

