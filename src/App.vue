<script setup>
import { RouterLink, RouterView } from 'vue-router'
import SocialsVue from '../../2024/src/components/socials-vue.vue';
import jumpLink from '../../2024/src/components/jump-link.vue';

</script>

<template>
  <header>
    <div class="wrapper">
      <div class="wrapper-inner">
        <img alt="Vue logo" class="logo" src="@/assets/matt-logo-personal-alpha.webp" width="367" height="138" />
        <p>Full-stack developer with JavaScript/Vue and PHP. I freelance for companies who want to make the world a better place.</p>
        <nav>
          <jump-link link="projects" text="Projects" />
          <jump-link link="about" text="About" />
          <jump-link link="contact" text="Contact" />
        </nav>
      </div>

      <SocialsVue />
    </div>
  </header>
  <main>
    <RouterView></RouterView>
    
  </main>
</template>
