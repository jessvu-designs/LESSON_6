<script setup lang="ts">
import LinkButton from '../components/LinkButton.vue'

const links = [
  { label: 'See My Work', url: 'https://jessvu-designs.vercel.app/', icon: 'mdi-palette' },
  { label: "What I'm Reading", icon: 'mdi-book-open-variant' },
  { label: "What I'm Listening To", icon: 'mdi-music' },
  { label: 'Instagram', url: 'https://www.instagram.com/', icon: 'mdi-instagram', iconOnly: true },
  { label: 'Connect with me on LinkedIn', url: 'https://www.linkedin.com/', icon: 'mdi-linkedin', iconOnly: true },
  { label: 'Contact Me', url: 'mailto:hello@example.com', icon: 'mdi-email', iconOnly: true },
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
          <v-card
            class="pa-8 text-center wavy-card"
            elevation="10"
            :style="{
              background: 'rgba(255,255,255,0.78)',
              borderRadius: '32px',
              backdropFilter: 'blur(10px)',
              WebkitBackdropFilter: 'blur(10px)',
              boxShadow: '0 1px 6px 0 rgba(0,0,0,0.015)',
              margin: '0 auto'
            }"
          >
            <!-- wavy-card style moved to <style> block below -->
            <v-avatar size="112" class="mx-auto mb-4 pink-avatar">
              <img src="/headshot.jpg" alt="Profile headshot" style="width: 100%; height: 100%; object-fit: cover; border-radius: 50%; display: block;" />
            </v-avatar>
            <h1 class="text-h5 font-weight-bold mb-1">Jess Vu</h1>
            <p class="mb-6" style="margin-bottom: 48px;">research-driven designer of ✨digital products✨</p>
                <div style="display: flex; flex-direction: column; align-items: center; gap: 12px;">
              <template v-for="link in links" :key="link.label">
                <LinkButton
                  v-if="!link.iconOnly"
                  :label="link.label"
                  :url="link.url"
                  :icon="link.icon"
                  :iconOnly="link.iconOnly"
                />
              </template>
                  <div style="font-weight: 600; font-size: 1.1rem; margin-bottom: 0px; color: #5a2947; margin-top: 20px;">Let's Connect</div>
              <div class="icon-row">
                <template v-for="link in links" :key="link.label">
                  <LinkButton
                    v-if="link.iconOnly"
                    :label="link.label"
                    :url="link.url"
                    :icon="link.icon"
                    :iconOnly="link.iconOnly"
                  />
                </template>
              </div>
            </div>
          </v-card>
        </v-container>
      </v-sheet>
    </v-main>
  </v-app>
</template>

<style scoped>
  .icon-row {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 16px;
    margin-bottom: 0;
    margin-top: 0;
  }
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
    border-radius: 32px;
    overflow: hidden;
  }
  @media (min-width: 900px) {
    .wavy-card {
      max-width: 720px !important;
    }
  }
</style>