
<script setup lang="ts">
import LinkButton from '../components/LinkButton.vue'

const links = [
  { label: 'Portfolio', url: 'https://jessvu-designs.vercel.app/', icon: 'mdi-web' },
  { label: 'LinkedIn', url: 'https://www.linkedin.com/', icon: 'mdi-linkedin' },
  { label: 'Email', url: 'mailto:hello@example.com', icon: 'mdi-email' },
]
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

                <p class="mb-6" style="margin-bottom: 48px;">Builder of things on the web ✨</p>




                <nav aria-label="Profile links" style="display: flex; flex-direction: column; gap: 16px;">
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


