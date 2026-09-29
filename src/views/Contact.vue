<template>
  <div class="contact-page">
    <header class="contact-header">
      <h1>Hubungi Kami</h1>
      <p>Punya pertanyaan? Tulis saja pesanmu di bawah.</p>
    </header>

    <div class="contact-content">
      <div class="contact-info">
        <div class="info-item">
          <h3>📍 Kantor</h3>
          <p>Jl. Gatot Subroto No. 06, Jakarta Selatan</p>
        </div>
        <div class="info-item">
          <h3>📞 Telepon</h3>
          <p>+62 812 2406 7890</p>
        </div>
        <div class="info-item">
          <h3>✉️ Email</h3>
          <p>halo@kumpul.id</p>
        </div>
      </div>

      <div class="contact-form">
        <form @submit.prevent>
          <div class="form-group">
            <label>Nama</label>
            <input type="text" placeholder="Nama lengkap" class="form-control" />
          </div>
          <div class="form-group">
            <label>Email</label>
            <input type="email" placeholder="nama@email.com" class="form-control" />
          </div>
          <div class="form-group">
            <label>Pesan</label>
            <textarea placeholder="Tulis pesanmu..." rows="5" class="form-control"></textarea>
          </div>
          <button class="btn-submit">Kirim Pesan</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact-page {
  animation: fadeIn 0.4s ease;
}
.contact-header {
  margin-bottom: 2rem;
}
.contact-header h1 {
  font-size: 2.3rem;
}
.contact-header p {
  color: var(--muted);
}
.contact-content {
  display: flex;
  gap: 2rem;
}
.contact-info {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.info-item {
  padding: 1.2rem;
  background: var(--blue);
  border: 2px solid var(--ink);
  border-radius: 12px;
  box-shadow: var(--shadow);
}
.contact-form {
  flex: 1.5;
  padding: 1.8rem;
  background: var(--card);
  border: 3px solid var(--ink);
  border-radius: 14px;
  box-shadow: 6px 6px 0 var(--ink);
}
.form-group {
  margin-bottom: 1.1rem;
}
.form-group label {
  display: block;
  margin-bottom: 0.3rem;
  font-weight: 700;
}
.form-control {
  width: 100%;
  padding: 0.7rem 0.9rem;
  border: 2px solid var(--ink);
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  outline: none;
}
.form-control:focus {
  background: #fffbe0;
}
.btn-submit {
  width: 100%;
  padding: 0.85rem;
  background: var(--yellow);
  border: 2px solid var(--ink);
  border-radius: 10px;
  box-shadow: var(--shadow);
  font-size: 1rem;
  font-weight: 700;
  font-family: inherit;
  cursor: pointer;
}
.btn-submit:hover {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0 var(--ink);
}
@media (max-width: 768px) {
  .contact-content {
    flex-direction: column;
  }
}
</style>