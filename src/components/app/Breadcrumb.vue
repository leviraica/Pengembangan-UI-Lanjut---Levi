<script setup>
import { computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()

const breadcrumbs = computed(() => {
  const crumbs = route.matched
    .filter((m) => m.meta && m.meta.breadcrumb)
    .map((m) => ({
      label: m.meta.breadcrumb,
      path: m.path.includes(':') ? route.path : m.path || '/',
    }))

  // Halaman detail: sisipkan "Event List" sebelum crumb terakhir
  if (route.name === 'event-detail') {
    crumbs.splice(crumbs.length - 1, 0, { label: 'Event List', path: '/browse/events' })
  }

  // Pastikan selalu diawali Home
  if (crumbs.length === 0 || crumbs[0].label !== 'Home') {
    crumbs.unshift({ label: 'Home', path: '/' })
  }

  return crumbs
})
</script>

<template>
  <nav class="breadcrumb">
    <ul>
      <li v-for="(crumb, index) in breadcrumbs" :key="index">
        <span v-if="index > 0" class="separator">/</span>
        <router-link v-if="index < breadcrumbs.length - 1" :to="crumb.path">
          {{ crumb.label }}
        </router-link>
        <span v-else class="active-crumb">{{ crumb.label }}</span>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.breadcrumb {
  display: inline-block;
  margin-bottom: 1.5rem;
  padding: 0.5rem 1rem;
  background: var(--card);
  border: 2px solid var(--ink);
  border-radius: 8px;
  box-shadow: 3px 3px 0 var(--ink);
}
.breadcrumb ul {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  list-style: none;
  flex-wrap: wrap;
}
.breadcrumb a {
  color: var(--ink);
  font-weight: 500;
}
.breadcrumb a:hover {
  background: var(--yellow);
}
.separator {
  margin-right: 0.5rem;
  font-weight: 700;
}
.active-crumb {
  font-weight: 700;
  background: var(--pink);
  padding: 0 0.4rem;
}
</style>