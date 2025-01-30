<template>
  <div>
    <header>
      <Burgermenu />
    </header>
    <main>
      <NuxtPage />
    </main>
  </div>
</template>

<script setup>
import Burgermenu from '~/components/Burgermenu.vue';
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
  /* Background color for the entire app */
}

html {
  scroll-behavior: smooth;
  /* Add smooth scrolling behavior */
}

.title {
  width: 70%;
  /* Ensure the title div fills its container */
}

/* Media query for screens smaller than 768px (typical mobile screens) */
@media only screen and (max-width: 768px) {
  .title {
    width: 90%;
    /* Adjust width for smaller screens */
  }
}

p {
  color: whitesmoke;
  /* Default paragraph color for the app */
  line-height: 2em;
  /* Adjust line height */
}

.front {
  min-height: calc(100vh - 160px);
  /* Adjust min-height for smaller screens */
  background-color: #8DA2D0;
  /* Ensure the front section has the same background */
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* Center vertically */
  align-items: center;
  /* Center horizontally */
}
</style>
