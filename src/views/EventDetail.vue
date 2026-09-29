<template>
  <div class="event-detail-page">
    <button @click="$router.push('/browse/events')" class="btn-back">← Kembali ke Acara</button>

    <div class="detail-header">
      <span class="event-tag">Acara Komunitas</span>
      <h1>Detail Acara #{{ $route.params.id }}</h1>
      <div class="meta-info">
        <span>📅 15 Oktober 2026</span>
        <span>📍 Auditorium Utama</span>
        <span>👥 500+ Peserta</span>
      </div>
    </div>

    <div class="detail-content">
      <div class="main-desc">
        <h2>Tentang Acara</h2>
        <p>
          Acara ini mempertemukan anggota komunitas untuk berbagi pengalaman, membangun jaringan, dan
          menemukan peluang kolaborasi baru. Terbuka untuk umum.
        </p>

        <h2>Agenda</h2>
        <ul class="agenda-list">
          <li><strong>09:00</strong> Registrasi & sambutan</li>
          <li><strong>10:00</strong> Sesi utama</li>
          <li><strong>11:30</strong> Networking</li>
          <li><strong>13:00</strong> Penutupan</li>
        </ul>
      </div>

      <aside class="ticket-card">
        <h3>Pendaftaran</h3>
        <p class="price">Gratis</p>
        <button class="btn-register">Daftar Sekarang</button>
        <p class="spots">Sisa 45 tempat!</p>
      </aside>
    </div>
  </div>
</template>

<style scoped>
.event-detail-page {
  animation: fadeIn 0.4s ease;
}
.btn-back {
  padding: 0.4rem 1rem;
  margin-bottom: 1.5rem;
  background: var(--card);
  border: 2px solid var(--ink);
  border-radius: 8px;
  box-shadow: 3px 3px 0 var(--ink);
  font-weight: 700;
  font-family: inherit;
  cursor: pointer;
}
.btn-back:hover {
  background: var(--yellow);
}
.detail-header {
  padding: 2.2rem;
  margin-bottom: 2rem;
  background: var(--blue);
  border: 3px solid var(--ink);
  border-radius: 16px;
  box-shadow: 6px 6px 0 var(--ink);
}
.event-tag {
  display: inline-block;
  padding: 0.15rem 0.8rem;
  background: var(--card);
  border: 2px solid var(--ink);
  border-radius: 999px;
  font-weight: 700;
  font-size: 0.85rem;
}
.detail-header h1 {
  margin: 0.8rem 0;
  font-size: 2.2rem;
}
.meta-info {
  display: flex;
  flex-wrap: wrap;
  gap: 1.3rem;
  font-weight: 500;
}
.detail-content {
  display: flex;
  gap: 2rem;
}
.main-desc {
  flex: 2;
}
.main-desc h2 {
  margin: 0 0 0.6rem;
}
.main-desc p {
  margin-bottom: 1.5rem;
  color: var(--muted);
}
.agenda-list {
  list-style: none;
}
.agenda-list li {
  padding: 0.7rem 0;
  border-bottom: 2px solid var(--ink);
}
.ticket-card {
  flex: 1;
  align-self: flex-start;
  position: sticky;
  top: 100px;
  padding: 1.6rem;
  text-align: center;
  background: var(--yellow);
  border: 3px solid var(--ink);
  border-radius: 14px;
  box-shadow: var(--shadow);
}
.price {
  margin: 0.5rem 0 1rem;
  font-size: 2.2rem;
  font-weight: 700;
}
.btn-register {
  width: 100%;
  padding: 0.8rem;
  background: var(--ink);
  color: #fff;
  border: 2px solid var(--ink);
  border-radius: 10px;
  font-size: 1rem;
  font-weight: 700;
  font-family: inherit;
  cursor: pointer;
}
.btn-register:hover {
  background: var(--pink);
  color: var(--ink);
}
.spots {
  margin-top: 1rem;
  font-weight: 700;
}
@media (max-width: 900px) {
  .detail-content {
    flex-direction: column;
  }
}
</style>