<script setup lang="ts">
import { ref } from 'vue'

const isDark = ref(true)

function toggleTheme() {
  isDark.value = !isDark.value
  document.documentElement.setAttribute('data-theme', isDark.value ? 'dark' : 'light')
}

const links = [
  { label: 'Website', url: 'https://keithtatum.com', icon: '🌐' },
  { label: 'LinkedIn', url: 'https://linkedin.com/in/keithtatum', icon: '💼' },
  { label: 'Email', url: 'mailto:hello@keithtatum.com', icon: '✉️' },
]
</script>

<template>
  <div class="container">
    <button class="theme-toggle" @click="toggleTheme" :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'">
      {{ isDark ? '☀️' : '🌙' }}
    </button>

    <div class="card">
      <div class="avatar">
        <span class="avatar-placeholder">KT</span>
      </div>

      <h1 class="name">Keith Tatum</h1>
      <p class="tagline">Developer · Creator · Lifelong Learner</p>

      <div class="links">
        <a
          v-for="link in links"
          :key="link.label"
          :href="link.url"
          class="link-btn"
          target="_blank"
          rel="noopener noreferrer"
        >
          <span class="link-icon">{{ link.icon }}</span>
          {{ link.label }}
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 2rem 1rem;
  position: relative;
}

.theme-toggle {
  position: absolute;
  top: 1.5rem;
  right: 1.5rem;
  background: var(--color-background-soft);
  border: 1px solid var(--color-border);
  border-radius: 50%;
  width: 44px;
  height: 44px;
  font-size: 1.25rem;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
  display: flex;
  align-items: center;
  justify-content: center;
}

.theme-toggle:hover {
  transform: scale(1.1);
  background: var(--color-background-mute);
}

.card {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: var(--color-background-mute);
  border: 3px solid var(--color-border-hover);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  margin-bottom: 0.5rem;
}

.avatar-placeholder {
  font-size: 2.5rem;
  font-weight: 600;
  color: var(--color-heading);
  letter-spacing: 0.05em;
}

.name {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--color-heading);
  margin: 0;
}

.tagline {
  font-size: 0.95rem;
  color: var(--color-text);
  opacity: 0.8;
  margin: 0 0 1rem;
}

.links {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.link-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  width: 100%;
  padding: 1rem;
  border-radius: 12px;
  background: var(--color-background-soft);
  border: 1px solid var(--color-border);
  color: var(--color-heading);
  font-size: 1rem;
  font-weight: 500;
  text-decoration: none;
  transition: transform 0.2s ease, background-color 0.2s ease, box-shadow 0.2s ease;
}

.link-btn:hover {
  transform: translateY(-3px);
  background: var(--color-background-mute);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.link-btn:active {
  transform: translateY(0);
}

.link-icon {
  font-size: 1.2rem;
}
</style>
