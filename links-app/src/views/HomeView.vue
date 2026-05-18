
<script setup lang="ts">
import { ref, computed } from 'vue'
import { useTheme } from 'vuetify'

import LinkButton from '../components/LinkButton.vue'


const links = [
  { label: 'Portfolio', url: 'https://jessvu-designs.vercel.app/', icon: 'mdi-web' },
  { label: 'LinkedIn', url: 'https://www.linkedin.com/', icon: 'mdi-linkedin' },
  { label: 'Email', url: 'mailto:hello@example.com', icon: 'mdi-email' },
]

const theme = useTheme()
const isDark = computed(() => theme.global.current.value.dark)
function toggleTheme() {
  theme.global.name.value = isDark.value ? 'light' : 'dark'
}
</script>

<template>
  <v-app>
    <v-main>
      <v-sheet
        class="fill-height d-flex align-center justify-center"
        height="100vh"
        width="100vw"
        :style="{
          background: 'linear-gradient(135deg, #ffd6e0 0%, #ffe5b4 100%)',
        }"
      >
        <v-container class="fill-height" fluid>
          <v-row align="center" justify="center">
            <v-col cols="12" sm="8" md="6" lg="4">
              <v-card
                class="pa-8 text-center"
                elevation="10"
                :style="{
                  background: 'rgba(255,255,255,0.78)',
                  borderRadius: '32px',
                  backdropFilter: 'blur(10px)',
                  WebkitBackdropFilter: 'blur(10px)',
                  boxShadow: '0 6px 24px 0 rgba(0,0,0,0.10)'
                }"
              >
                <v-avatar size="112" class="mx-auto mb-4">
                  <span class="text-h4 font-weight-bold">JV</span>
                </v-avatar>
                <h1 class="text-h5 font-weight-bold mb-1">Jess Vu</h1>
                <p class="mb-4">Builder of things on the web ✨</p>

                <v-btn
                  class="mb-2"
                  :icon="isDark ? 'mdi-weather-sunny' : 'mdi-weather-night'"
                  variant="text"
                  @click="toggleTheme"
                  color="primary"
                  aria-label="Toggle dark/light theme"
                >
                  <v-icon>{{ isDark ? 'mdi-weather-sunny' : 'mdi-weather-night' }}</v-icon>
                  <span class="ms-2">{{ isDark ? 'Light' : 'Dark' }} Mode</span>
                </v-btn>

                <v-divider class="my-4" />

                <nav aria-label="Profile links">
                  <LinkButton
                    v-for="link in links"
                    :key="link.label"
                    :label="link.label"
                    :url="link.url"
                    :icon="link.icon"
                  />
                </nav>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-sheet>
    </v-main>
  </v-app>
</template>


