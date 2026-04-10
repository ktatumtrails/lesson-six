<script setup lang="ts">
import { useTheme } from 'vuetify'
import { RouterLink } from 'vue-router'
import LinkButton from '@/components/LinkButton.vue'

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

          <div style="padding: 40px 0;">
            <v-divider />
          </div>

          <!-- Link buttons -->
          <div class="d-flex flex-column ga-3" style="padding-top: 15px;">
            <LinkButton
              label="About Keith"
              icon="mdi-account-outline"
              to="/about"
            />

            <LinkButton
              v-for="link in links"
              :key="link.label"
              :label="link.label"
              :icon="link.icon"
              :url="link.url"
            />
          </div>

          <div style="padding: 40px 0;">
            <v-divider />
          </div>

          <p class="text-caption text-center text-medium-emphasis">Crafted with care &amp; coffee for Protogen 200s Course</p>

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
