<script setup lang="ts">
defineProps<{
  label: string
  icon: string
  url?: string
  to?: string
}>()
</script>

<template>
  <v-btn
    v-if="url"
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    :prepend-icon="icon"
    variant="tonal"
    size="large"
    block
    rounded="lg"
    class="text-none"
  >
    {{ label }}
  </v-btn>

  <v-btn
    v-else
    :to="to"
    :prepend-icon="icon"
    variant="tonal"
    size="large"
    block
    rounded="lg"
    class="text-none"
  >
    {{ label }}
  </v-btn>
</template>

<style scoped>
:deep(.v-btn__prepend) {
  margin-inline-end: 12px;
}
</style>
