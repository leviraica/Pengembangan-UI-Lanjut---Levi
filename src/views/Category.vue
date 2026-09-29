<script setup>
const categories = [
  { name: 'Musik', icon: '🎵', count: 24, color: 'var(--pink)' },
  { name: 'Teknologi', icon: '💻', count: 18, color: 'var(--blue)' },
  { name: 'Seni & Desain', icon: '🎨', count: 12, color: 'var(--yellow)' },
  { name: 'Bisnis', icon: '💼', count: 30, color: 'var(--blue)' },
  { name: 'Kesehatan', icon: '🧘', count: 15, color: 'var(--yellow)' },
  { name: 'Kuliner', icon: '🍜', count: 22, color: 'var(--pink)' },
]
</script>

<template>
  <div class="category-page">
    <h2 class="section-title">Kategori Acara</h2>
    <div class="category-grid">
      <div
        class="category-card"
        v-for="cat in categories"
        :key="cat.name"
        :style="{ background: cat.color }"
      >
        <div class="cat-icon">{{ cat.icon }}</div>
        <h3>{{ cat.name }}</h3>
        <p>{{ cat.count }} Acara</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.section-title {
  font-size: 1.7rem;
  margin-bottom: 1.5rem;
}
.category-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
  gap: 1.3rem;
}
.category-card {
  padding: 1.6rem;
  text-align: center;
  border: 3px solid var(--ink);
  border-radius: 14px;
  box-shadow: var(--shadow);
  transition: all 0.1s;
}
.category-card:hover {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0 var(--ink);
}
.cat-icon {
  font-size: 2.5rem;
}
</style>