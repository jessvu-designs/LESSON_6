
<script setup lang="ts">
const props = defineProps<{
  label: string;
  url: string;
  icon: string;
  iconOnly?: boolean;
}>()
</script>

<template>
  <v-btn
    v-if="url"
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    :class="iconOnly ? 'icon-btn' : 'mb-2 pa-4 text-body-1 font-weight-bold'"
    :color="iconOnly ? undefined : '#f8bbd0'"
    :style="iconOnly ? '' : 'background: #f8bbd0; color: #5a2947; border-radius: 999px; box-shadow: 0 2px 8px 0 rgba(0,0,0,0.04); min-height: 48px;'"
    :icon="props.iconOnly"
    :block="!iconOnly"
  >
    <v-icon :icon="icon" :class="iconOnly ? '' : 'mr-2'" style="font-size: 32px;" />
    <template v-if="!iconOnly">
      {{ label }}
    </template>
  </v-btn>
  <v-btn
    v-else
    :class="iconOnly ? 'icon-btn' : 'mb-2 pa-4 text-body-1 font-weight-bold'"
    :color="iconOnly ? undefined : '#f8bbd0'"
    :style="iconOnly ? '' : 'background: #f8bbd0; color: #5a2947; border-radius: 999px; box-shadow: 0 2px 8px 0 rgba(0,0,0,0.04); min-height: 48px;'"
    :icon="props.iconOnly"
    :block="!iconOnly"
  >
    <v-icon :icon="icon" :class="iconOnly ? '' : 'mr-2'" style="font-size: 32px;" />
    <template v-if="!iconOnly">
      {{ label }}
    </template>
  </v-btn>
</template>

<style scoped>
.icon-btn {
  background: none !important;
  color: #5a2947 !important;
  box-shadow: none !important;
  min-width: 0;
  padding: 8px;
  border-radius: 50%;
}
</style>