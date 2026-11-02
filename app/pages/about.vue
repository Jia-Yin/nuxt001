<script setup>
// 原 Vue 作品內容：完整簡介與興趣清單
const bio = ref({
  story: '你好！我是一名對網頁前端充滿熱忱的學習者。在先前的 Vue 學習單元中，掌握了元件拆分、響應式資料與事件互動。目前正運用 Nuxt 4 擴充實務架構能力，學習如何組織乾淨、好維護的多頁面應用程式。',
  interests: ['前端介面設計', '開源技術探索', '攝影與城市散步', '咖啡與音樂']
})

// 我提供的新內容：技術技能清單
const skills = ref([
  'Vue 3 (Composition API)',
  'Nuxt 4',
  'JavaScript (ES6+)',
  'HTML5 / CSS3',
  'Git 版本控制'
])

// 待新增內容：聯絡與社群示範資料
const contactInfo = ref({
  email: 'demo-user@example.com',
  github: 'https://github.com/demo-user'
})
</script>

<template>
  <div class="about-page">
    <h1 class="page-title">關於我</h1>

    <section class="section-block">
      <h2>個人簡介</h2>
      <p class="bio-text">{{ bio.story }}</p>
    </section>

    <section class="section-block">
      <h2>技術與學習標籤</h2>
      <div class="tag-list">
        <span v-for="skill in skills" :key="skill" class="tag skill-tag">
          {{ skill }}
        </span>
      </div>
    </section>

    <section class="section-block">
      <h2>興趣愛好</h2>
      <ul class="interest-list">
        <li v-for="interest in bio.interests" :key="interest">
          {{ interest }}
        </li>
      </ul>
    </section>

    <section class="section-block">
      <h2>聯絡方式</h2>
      <div class="contact-card">
        <p><strong>Email：</strong>{{ contactInfo.email }}</p>
        <p><strong>GitHub：</strong><a :href="contactInfo.github" target="_blank" rel="noopener">{{ contactInfo.github }}</a></p>
      </div>
    </section>
  </div>
</template>

<style scoped>
.page-title {
  font-size: 2rem;
  color: #0f172a;
  margin-bottom: 2rem;
}

.section-block {
  background-color: #ffffff;
  padding: 1.75rem;
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  margin-bottom: 1.5rem;
}

.section-block h2 {
  font-size: 1.3rem;
  color: #1e293b;
  margin-bottom: 1rem;
  border-bottom: 2px solid #f1f5f9;
  padding-bottom: 0.5rem;
}

.bio-text {
  color: #475569;
  font-size: 1.05rem;
  line-height: 1.8;
}

.tag-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.tag {
  padding: 0.4rem 0.8rem;
  border-radius: 6px;
  font-size: 0.9rem;
  font-weight: 500;
}

.skill-tag {
  background-color: #ecfdf5;
  color: #059669;
  border: 1px solid #a7f3d0;
}

.interest-list {
  list-style-type: disc;
  padding-left: 1.5rem;
  color: #475569;
}

.interest-list li {
  margin-bottom: 0.4rem;
}

.contact-card p {
  color: #475569;
  margin-bottom: 0.5rem;
}

.contact-card a {
  color: #00dc82;
  text-decoration: none;
}

.contact-card a:hover {
  text-decoration: underline;
}
</style>

