
<script setup lang="ts">
defineProps<{
  label: string;
  url: string;
  icon: string;
}>()
</script>

<template>
  <v-btn
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="mb-2 pa-4 text-body-1 font-weight-bold"
    color="#f8bbd0"
    style="background: #f8bbd0; color: #5a2947; border-radius: 5px; box-shadow: 0 2px 8px 0 rgba(0,0,0,0.04);"
    block
  >
    <v-icon :icon="icon" class="mr-2" />
    {{ label }}
  </v-btn>
</template>

<style scoped>
/* No additional styles needed for LinkButton */
</style>