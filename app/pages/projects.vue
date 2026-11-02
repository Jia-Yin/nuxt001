<script setup>
// 我提供的新內容與待新增展示作品列表
const projects = ref([
  {
    id: 1,
    title: 'Vue 3 基礎練習：互動計數與待辦事項',
    category: 'Vue 練習',
    description: '使用 Vue Composition API、ref/reactive 以及元件傳值 (props/emit) 所完成的互動介面練習。',
    tags: ['Vue 3', 'Composition API', 'CSS'],
    demoUrl: 'https://example.com/demo-vue-todo',
    sourceType: '原 Vue 作品基礎'
  },
  {
    id: 2,
    title: 'Nuxt 4 三頁式個人首頁',
    category: 'Nuxt 練習',
    description: '運用 Nuxt 4 檔案即路由（File-based routing）架構，建立首頁、關於我與作品集的個人網站。',
    tags: ['Nuxt 4', 'Vue Router', 'SSR/SSG ready'],
    demoUrl: 'https://example.com/demo-nuxt-portfolio',
    sourceType: '新內容'
  },
  {
    id: 3,
    title: '未來專案：動態資料與 API 串接作品',
    category: '待開發',
    description: '規劃中的練習作品，預計學習利用 useFetch 串接第三方 API 並呈現資料卡片。',
    tags: ['Nuxt 4', 'RESTful API', 'useFetch'],
    demoUrl: '#',
    sourceType: '待新增'
  }
])
</script>

<template>
  <div class="projects-page">
    <div class="header-intro">
      <h1 class="page-title">作品展示</h1>
      <p class="subtitle">這裡彙整了我的前端學習練習專案與作品成果。</p>
    </div>

    <div class="projects-grid">
      <!-- 使用 Nuxt 自動引入的 ProjectCard 元件 -->
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        :project="project"
      />
    </div>
  </div>
</template>

<style scoped>
.header-intro {
  margin-bottom: 2rem;
}

.page-title {
  font-size: 2rem;
  color: #0f172a;
  margin-bottom: 0.5rem;
}

.subtitle {
  color: #64748b;
  font-size: 1.05rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}
</style>
