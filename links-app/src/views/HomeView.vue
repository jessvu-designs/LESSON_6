<script setup lang="ts">
const links = [
  { label: 'Portfolio', href: 'https://example.com', icon: '🌐' },
  { label: 'LinkedIn', href: 'https://www.linkedin.com/', icon: '💼' },
  { label: 'Email', href: 'mailto:hello@example.com', icon: '✉️' },
]
</script>

<template>
  <main class="page">
    <section class="card">
      <div class="avatar" aria-hidden="true">
        <span class="avatar__initials">JV</span>
      </div>
      <h1 class="name">Jess Vu</h1>
      <p class="tagline">Builder of things on the web ✨</p>

      <nav class="links" aria-label="Profile links">
        <a
          v-for="link in links"
          :key="link.label"
          :href="link.href"
          class="link-button"
          target="_blank"
          rel="noopener noreferrer"
        >
          <span class="link-button__icon" aria-hidden="true">{{ link.icon }}</span>
          <span class="link-button__label">{{ link.label }}</span>
        </a>
      </nav>
    </section>
  </main>
</template>

<style scoped>
.page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 1rem;
}

.card {
  width: 100%;
  max-width: 480px;
  background: rgba(255, 255, 255, 0.78);
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  border-radius: 24px;
  padding: 2.5rem 1.75rem;
  text-align: center;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.15);
  border: 1px solid rgba(255, 255, 255, 0.6);
}

.avatar {
  width: 112px;
  height: 112px;
  border-radius: 50%;
  margin: 0 auto 1.25rem;
  background: linear-gradient(135deg, #ff6a88, #ffb86c);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  box-shadow: 0 10px 25px rgba(255, 106, 136, 0.4);
  border: 4px solid #fff;
}

.avatar__initials {
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: 0.05em;
}

.name {
  font-size: 1.6rem;
  font-weight: 700;
  letter-spacing: -0.01em;
  color: #1f2937;
}

.tagline {
  margin-top: 0.4rem;
  font-size: 0.95rem;
  color: #4b5563;
}

.links {
  margin-top: 1.75rem;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.link-button {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.6rem;
  padding: 0.95rem 1rem;
  background: #ffffff;
  color: #1f2937;
  font-weight: 600;
  font-size: 1rem;
  border-radius: 14px;
  border: 1px solid rgba(0, 0, 0, 0.06);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  transition:
    transform 220ms ease,
    box-shadow 220ms ease,
    background-color 220ms ease,
    color 220ms ease;
}

.link-button:hover,
.link-button:focus-visible {
  transform: translateY(-3px);
  background: linear-gradient(135deg, #ff6a88, #ffb86c);
  color: #fff;
  box-shadow: 0 12px 24px rgba(255, 106, 136, 0.35);
  outline: none;
}

.link-button:active {
  transform: translateY(-1px);
}

.link-button__icon {
  font-size: 1.1rem;
}

@media (min-width: 640px) {
  .card {
    padding: 3rem 2.25rem;
  }

  .name {
    font-size: 1.85rem;
  }
}
</style>
