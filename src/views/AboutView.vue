<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="container">
    <div class="card">
      <RouterLink to="/" class="back-link">← Back</RouterLink>

      <h1 class="title">About</h1>

      <p class="text">
        Keith leads experience strategy &amp; design for the Slalom Collective Intelligence team,
        turning research, knowledge, and insights into intuitive, AI-driven tool experiences,
        document generators, and custom apps for sales, delivery, and everyday productivity.
      </p>

      <p class="text">
        When he's not designing experiences, you'll find him hiking trails, experimenting with
        new creative tools, and exploring ways to make technology more human.
      </p>
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
}

.card {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.back-link {
  font-size: 0.9rem;
  color: var(--color-text);
  text-decoration: none;
  opacity: 0.7;
  transition: opacity 0.2s ease;
}

.back-link:hover {
  opacity: 1;
}

.title {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--color-heading);
  margin: 0;
}

.text {
  font-size: 0.95rem;
  line-height: 1.7;
  color: var(--color-text);
  margin: 0;
}
</style>
