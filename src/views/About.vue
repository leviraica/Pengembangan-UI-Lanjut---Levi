<template>
  <div class="about-page">
    <div class="about-header">
      <h1>About Gatherly</h1>
      <p>Building the future of event experiences, one community at a time.</p>
    </div>

    <div class="about-content">
      <div class="text-block">
        <h2>Our Mission</h2>
        <p>
          Gatherly exists to make event discovery simple and meaningful. We connect communities through
          technology that puts people first — from intimate meetups to large conferences.
        </p>
      </div>

      <div class="text-block">
        <h2>Our Vision</h2>
        <p>
          A world where every idea, big or small, has a place to be shared. We're building the tools that
          help organizers and attendees meet in the middle.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  animation: fadeIn 0.5s ease;
  max-width: 800px;
  margin: 0 auto;
}
.about-header {
  text-align: center;
  margin-bottom: 4rem;
  padding: 4rem 2rem;
  background: #fdfdfd;
  border-radius: 20px;
  border: 1px solid #f0f0f0;
}
.about-header h1 {
  font-size: 3rem;
  color: #1c1948;
  margin-bottom: 1rem;
}
.about-header p {
  font-size: 1.2rem;
  color: #666;
}
.about-content {
  display: flex;
  flex-direction: column;
  gap: 3rem;
  padding: 0 1rem;
}
.text-block h2 {
  color: #1c1948;
  font-size: 1.8rem;
  margin-bottom: 1.2rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}
.text-block h2::before {
  content: '';
  display: block;
  width: 24px;
  height: 4px;
  background: #6644ff;
  border-radius: 2px;
}
.text-block p {
  color: #555;
  line-height: 1.8;
  font-size: 1.1rem;
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>