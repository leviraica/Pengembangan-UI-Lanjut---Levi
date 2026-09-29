<template>
  <div class="about-page">
    <header class="about-header">
      <h1>Tentang Kumpul</h1>
      <p>Tempat berkumpulnya orang-orang yang suka bertemu dan belajar bersama.</p>
    </header>

    <div class="text-block">
      <h2>Misi Kami</h2>
      <p>
        Mempermudah siapa pun menemukan, mengikuti, dan menyelenggarakan acara yang bermakna, dengan
        informasi yang jelas dan akses yang mudah.
      </p>
    </div>

    <div class="text-block">
      <h2>Visi Kami</h2>
      <p>
        Menjadi ruang temu digital yang menghubungkan komunitas di seluruh Indonesia lewat acara yang
        terbuka dan menyenangkan.
      </p>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  max-width: 760px;
  margin: 0 auto;
  animation: fadeIn 0.4s ease;
}
.about-header {
  padding: 2.5rem;
  margin-bottom: 2rem;
  background: var(--pink);
  border: 3px solid var(--ink);
  border-radius: 16px;
  box-shadow: 6px 6px 0 var(--ink);
}
.about-header h1 {
  font-size: 2.4rem;
  margin-bottom: 0.4rem;
}
.text-block {
  padding: 1.5rem;
  margin-bottom: 1.5rem;
  background: var(--card);
  border: 2px solid var(--ink);
  border-radius: 12px;
  box-shadow: var(--shadow);
}
.text-block h2 {
  margin-bottom: 0.5rem;
}
.text-block p {
  color: var(--muted);
}
</style>