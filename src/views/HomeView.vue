<script setup lang="ts">
import { useTheme } from 'vuetify'
import { RouterLink } from 'vue-router'

const theme = useTheme()

function toggleTheme() {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}

const links = [
  { label: 'Website', url: 'https://visibilityexp.com', icon: 'mdi-web' },
  { label: 'LinkedIn', url: 'https://linkedin.com/in/keithtatum', icon: 'mdi-linkedin' },
  { label: 'Email', url: 'mailto:visibilityexperiments.com', icon: 'mdi-email-outline' },
]
</script>

<template>
  <v-main>
    <v-container class="fill-height" fluid>
      <v-row justify="center" align="center">
        <v-col cols="12" sm="8" md="6" lg="5" style="max-width: 480px">

          <v-btn
            icon
            variant="tonal"
            size="small"
            style="position: absolute; top: 1.5rem; right: 1.5rem;"
            :aria-label="theme.global.current.value.dark ? 'Switch to light mode' : 'Switch to dark mode'"
            @click="toggleTheme"
          >
            <v-icon>{{ theme.global.current.value.dark ? 'mdi-weather-sunny' : 'mdi-weather-night' }}</v-icon>
          </v-btn>

          <!-- Header -->
          <div class="d-flex align-center ga-4 mb-6">
            <v-avatar size="104">
              <v-img src="/keithphoto.jpg" alt="Keith Tatum" cover />
            </v-avatar>
            <div>
              <h1 class="text-h5 font-weight-bold">Keith Tatum</h1>
              <p class="text-body-2 text-medium-emphasis">Experience Strategist · Trail Hiker · Visual Thinker</p>
            </div>
          </div>

          <v-divider class="mb-6" />

          <!-- Link buttons -->
          <div class="d-flex flex-column ga-3">
            <v-btn
              :to="'/about'"
              variant="tonal"
              size="large"
              block
              rounded="lg"
              class="text-none"
            >
              <v-icon start>mdi-account-outline</v-icon>
              About Keith
            </v-btn>

            <v-btn
              v-for="link in links"
              :key="link.label"
              :href="link.url"
              target="_blank"
              rel="noopener noreferrer"
              variant="tonal"
              size="large"
              block
              rounded="lg"
              class="text-none"
            >
              <v-icon start>{{ link.icon }}</v-icon>
              {{ link.label }}
            </v-btn>
          </div>

        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.nav-link:hover {
  opacity: 1;
}
</style>
