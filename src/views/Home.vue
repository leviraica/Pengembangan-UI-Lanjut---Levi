<script setup>
const features = [
  { title: 'Acara Seru', desc: 'Konser, workshop, sampai bazar kuliner.', color: 'var(--pink)' },
  { title: 'Mudah Dicari', desc: 'Ketik kata kunci, acara langsung muncul.', color: 'var(--blue)' },
  { title: 'Gratis Gabung', desc: 'Tidak perlu akun untuk melihat acara.', color: 'var(--yellow)' },
]
</script>

<template>
  <div class="home-page">
    <section class="hero">
      <h1>Cari acara,<br />ketemu teman baru.</h1>
      <p>Kumpul membantu kamu menemukan acara komunitas yang paling cocok.</p>
      <div class="hero-actions">
        <router-link to="/browse/events" class="btn btn-dark">Lihat Acara</router-link>
        <router-link to="/about" class="btn btn-light">Tentang Kami</router-link>
      </div>
    </section>

    <section class="features">
      <div class="feature-card" v-for="f in features" :key="f.title" :style="{ background: f.color }">
        <h3>{{ f.title }}</h3>
        <p>{{ f.desc }}</p>
      </div>
    </section>

    <section class="sitemap-visual">
      <h2>Site Map</h2>
      <ul class="tree">
        <li>
          <router-link to="/">Home</router-link>
          <ul>
            <li><router-link to="/about">About</router-link></li>
            <li>
              <router-link to="/browse">Browse</router-link>
              <ul>
                <li>
                  <router-link to="/browse/events">Event List</router-link>
                  <ul>
                    <li><router-link to="/browse/events/1">Event Detail (Contoh)</router-link></li>
                  </ul>
                </li>
                <li><router-link to="/browse/category">Category</router-link></li>
              </ul>
            </li>
            <li><router-link to="/contact">Contact</router-link></li>
          </ul>
        </li>
      </ul>
    </section>
  </div>
</template>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
  animation: fadeIn 0.4s ease;
}
.hero {
  padding: 3.5rem 2.5rem;
  background: var(--yellow);
  border: 3px solid var(--ink);
  border-radius: 16px;
  box-shadow: 8px 8px 0 var(--ink);
}
.hero h1 {
  font-size: 3.2rem;
  line-height: 1.1;
  margin-bottom: 1rem;
}
.hero p {
  max-width: 480px;
  font-size: 1.15rem;
  margin-bottom: 1.8rem;
}
.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}
.btn {
  padding: 0.75rem 1.6rem;
  border: 2px solid var(--ink);
  border-radius: 10px;
  font-weight: 700;
  text-decoration: none;
  box-shadow: var(--shadow);
  transition: all 0.1s;
}
.btn:hover {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0 var(--ink);
}
.btn-dark {
  background: var(--ink);
  color: #fff;
}
.btn-light {
  background: #fff;
  color: var(--ink);
}
.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.5rem;
}
.feature-card {
  padding: 1.6rem;
  border: 3px solid var(--ink);
  border-radius: 14px;
  box-shadow: var(--shadow);
}
.feature-card h3 {
  margin-bottom: 0.3rem;
}
.sitemap-visual {
  padding: 2rem;
  background: var(--card);
  border: 3px solid var(--ink);
  border-radius: 14px;
  box-shadow: var(--shadow);
}
.sitemap-visual h2 {
  margin-bottom: 1rem;
}
.tree,
.tree ul {
  list-style: none;
  padding-left: 1.4rem;
  border-left: 3px solid var(--ink);
}
.tree {
  border-left: none;
  padding-left: 0;
}
.tree li {
  margin: 0.5rem 0;
}
.tree a {
  display: inline-block;
  padding: 0.25rem 0.8rem;
  border: 2px solid var(--ink);
  border-radius: 6px;
  background: var(--bg);
  color: var(--ink);
  text-decoration: none;
  font-weight: 500;
}
.tree a:hover {
  background: var(--blue);
}
@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.2rem;
  }
}
</style>