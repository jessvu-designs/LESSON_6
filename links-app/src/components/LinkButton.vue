<template>
  <v-btn
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="mb-2"
    color="#4fd1c5"
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
import { defineProps } from 'vue'

defineProps<{
  label: string
  url: string
  icon?: string
}>()
</script>
