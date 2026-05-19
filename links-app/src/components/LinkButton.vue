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
                class="pa-8 text-center wavy-card"
                elevation="10"
                :style="{
                  background: 'rgba(255,255,255,0.78)',
                  borderRadius: '32px',
                  backdropFilter: 'blur(10px)',
                  WebkitBackdropFilter: 'blur(10px)',
                  boxShadow: '0 6px 24px 0 rgba(0,0,0,0.10)'
                }"
              >
                <v-avatar size="112" class="mx-auto mb-4 pink-avatar">
                  <img src="/headshot.jpg" alt="Profile headshot" style="width: 100%; height: 100%; object-fit: cover; border-radius: 50%; display: block;" />
                </v-avatar>
                <h1 class="text-h5 font-weight-bold mb-1">Jess Vu</h1>
                <p class="mb-6" style="margin-bottom: 48px;">✨ research-driven designer of digital products ✨</p>
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

<style scoped>
.pink-avatar {
  border: 3px solid #ffb6c1;
  box-sizing: border-box;
  border-radius: 50%;
  display: inline-block;
  padding: 0;
  background: none;
  overflow: hidden;
}
.wavy-card {
  -webkit-mask-image: url('data:image/svg+xml;utf8,<svg width="100%25" height="100%25" viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg"><path d="M0,40 Q50,0 100,40 T200,40 T300,40 T400,40 V360 Q350,400 300,360 T200,360 T100,360 T0,360 Z" fill="white"/></svg>');
  mask-image: url('data:image/svg+xml;utf8,<svg width="100%25" height="100%25" viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg"><path d="M0,40 Q50,0 100,40 T200,40 T300,40 T400,40 V360 Q350,400 300,360 T200,360 T100,360 T0,360 Z" fill="white"/></svg>');
  -webkit-mask-size: 100% 100%;
  mask-size: 100% 100%;
  -webkit-mask-repeat: no-repeat;
  mask-repeat: no-repeat;
  overflow: hidden;
}
</style>