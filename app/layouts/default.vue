<template>
  <div class="site-container">
    <header class="navbar">
      <div class="nav-brand">
        <NuxtLink to="/">個人網站</NuxtLink>
      </div>
      <nav class="nav-links">
        <NuxtLink to="/" class="nav-item">首頁</NuxtLink>
        <NuxtLink to="/about" class="nav-item">關於我</NuxtLink>
        <NuxtLink to="/projects" class="nav-item">作品</NuxtLink>
      </nav>
    </header>

    <main class="page-content">
      <slot />
    </main>

    <footer class="site-footer">
      <p>© 2026 個人網站練習專案 ｜ Nuxt 4 & Vue 示範</p>
    </footer>
  </div>
</template>

<style>
/* 全站基礎重設 */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  color: #333;
  background-color: #f8fafc;
  line-height: 1.6;
}
</style>

<style scoped>
.site-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #ffffff;
  border-bottom: 1px solid #e2e8f0;
}

.nav-brand a {
  font-size: 1.25rem;
  font-weight: bold;
  color: #0f172a;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 1.5rem;
}

.nav-item {
  color: #475569;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.2s;
}

.nav-item:hover,
.nav-item.router-link-active {
  color: #00dc82; /* Nuxt Green */
}

.page-content {
  flex: 1;
  max-width: 900px;
  width: 100%;
  margin: 0 auto;
  padding: 2.5rem 1.5rem;
}

.site-footer {
  text-align: center;
  padding: 1.5rem;
  background-color: #ffffff;
  border-top: 1px solid #e2e8f0;
  color: #64748b;
  font-size: 0.9rem;
}
</style>

