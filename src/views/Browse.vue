<template>
  <div class="browse-page">
    <div class="browse-header">
      <h1>Jelajahi</h1>
      <p>Temukan acara dan kategori yang kamu suka.</p>
    </div>
    <div class="browse-content">
      <router-view></router-view>
    </div>
  </div>
</template>

<style scoped>
.browse-page {
  animation: fadeIn 0.4s ease;
}
.browse-header {
  margin-bottom: 1.8rem;
  padding-bottom: 1rem;
  border-bottom: 3px solid var(--ink);
}
.browse-header h1 {
  font-size: 2.3rem;
}
.browse-header p {
  color: var(--muted);
}
</style>