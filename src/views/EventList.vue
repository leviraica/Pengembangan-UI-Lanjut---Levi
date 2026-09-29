<script setup>
import { ref, computed } from 'vue'

const keyword = ref('')

const events = [
  { id: 1, title: 'Jakarta Tech Meetup', date: '12 Okt 2026', location: 'Sudirman' },
  { id: 2, title: 'Festival Musik Senja', date: '18 Okt 2026', location: 'Senayan' },
  { id: 3, title: 'Workshop UI/UX Pemula', date: '25 Okt 2026', location: 'Kemang' },
  { id: 4, title: 'Bazar Kuliner Nusantara', date: '1 Nov 2026', location: 'Menteng' },
  { id: 5, title: 'Seminar Startup', date: '8 Nov 2026', location: 'Jakarta Selatan' },
  { id: 6, title: 'Yoga Pagi di Taman', date: '15 Nov 2026', location: 'Menteng' },
]

const filtered = computed(() =>
  events.filter((e) => e.title.toLowerCase().includes(keyword.value.toLowerCase())),
)
</script>

<template>
  <div class="event-list-page">
    <h2 class="section-title">Acara Mendatang</h2>

    <input v-model="keyword" type="text" placeholder="🔍 Cari acara..." class="search" />
    <p class="count">{{ filtered.length }} acara ditemukan</p>

    <div v-if="filtered.length" class="event-grid">
      <div class="event-card" v-for="e in filtered" :key="e.id">
        <span class="event-date">{{ e.date }}</span>
        <h3>{{ e.title }}</h3>
        <p class="event-loc">📍 {{ e.location }}</p>
        <router-link :to="`/browse/events/${e.id}`" class="btn-link">Lihat Detail →</router-link>
      </div>
    </div>

    <p v-else class="empty">Acara tidak ditemukan. Coba kata kunci lain.</p>
  </div>
</template>

<style scoped>
.section-title {
  font-size: 1.7rem;
  margin-bottom: 1rem;
}
.search {
  width: 100%;
  max-width: 420px;
  padding: 0.75rem 1rem;
  border: 3px solid var(--ink);
  border-radius: 10px;
  box-shadow: var(--shadow);
  font-size: 1rem;
  font-family: inherit;
  outline: none;
}
.search:focus {
  background: #fffbe0;
}
.count {
  margin: 1rem 0 1.5rem;
  color: var(--muted);
}
.event-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.5rem;
}
.event-card {
  padding: 1.4rem;
  background: var(--card);
  border: 3px solid var(--ink);
  border-radius: 14px;
  box-shadow: var(--shadow);
  transition: all 0.1s;
}
.event-card:hover {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0 var(--ink);
}
.event-date {
  display: inline-block;
  padding: 0.15rem 0.6rem;
  background: var(--yellow);
  border: 2px solid var(--ink);
  border-radius: 6px;
  font-size: 0.85rem;
  font-weight: 700;
}
.event-card h3 {
  margin: 0.8rem 0 0.3rem;
}
.event-loc {
  color: var(--muted);
  margin-bottom: 1rem;
}
.btn-link {
  color: var(--ink);
  font-weight: 700;
}
.btn-link:hover {
  background: var(--pink);
}
.empty {
  padding: 2rem;
  text-align: center;
  background: var(--card);
  border: 2px dashed var(--ink);
  border-radius: 12px;
}
</style>