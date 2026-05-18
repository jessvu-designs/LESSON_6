<template>
  <v-btn
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="mb-2 pink-btn"
    color="#ffe5ec"
    variant="elevated"
    block
    size="large"
    v-bind="$attrs"
  >
    <v-icon start v-if="icon">{{ icon }}</v-icon>
    {{ label }}
  </v-btn>
</template>

<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon?: string
}>()
</script>

<style scoped>
  .mb-2 {
    opacity: 0.88;
    transition: opacity 0.2s;
  }
  .mb-2:hover {
    opacity: 1;
  }
  .pink-btn {
    background-color: #ffe5ec !important;
    border: 2px solid #ff9a8b !important;
    color: #6d214f !important;
    box-shadow: 0 4px 16px 0 rgba(248,187,208,0.10);
  }
</style>