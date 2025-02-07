<template>
  <div>
    <AppHeader />
    <main class="main-content">
      <NuxtPage />
    </main>
    <AppFooter />
  </div>
</template>

<script setup>
import AppHeader from '~/components/AppHeader.vue';
import AppFooter from '~/components/AppFooter.vue';
</script>

<style>
html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
  font-family: "HelveticaNeue-Light", "Helvetica Neue Light", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
  font-weight: 300;
  background-color: #8DA2D0;
}

.main-content {
  padding-top: 160px;
}

html {
  scroll-behavior: smooth;
}

/* Media query for screens smaller than 768px (typical mobile screens) */
@media only screen and (max-width: 768px) {
  .title {
    width: 90%;
  }
}

p {
  color: whitesmoke;
  line-height: 2em;
}
</style>
