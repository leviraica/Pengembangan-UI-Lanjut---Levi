<script setup>
import Navbar from '@/components/app/Navbar.vue'
import Breadcrumb from '@/components/app/Breadcrumb.vue'
</script>

<template>
  <div class="app-layout">
    <Navbar />
    <main class="main-content">
      <Breadcrumb />
      <router-view />
    </main>
    <footer class="footer">Kumpul © 2026 — Praktikum Pengembangan UI Lanjut - Levi</footer>
  </div>
</template>

<style scoped>
.app-layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
.main-content {
  flex: 1;
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
  padding: 2rem;
}
.footer {
  text-align: center;
  padding: 1.2rem;
  background: var(--ink);
  color: var(--yellow);
  font-weight: 500;
}
</style>