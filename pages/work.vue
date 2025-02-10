<template>
  <div class="work-page">
    <WorkPane imageSrc="/img/work1.png" text="VFX & VIDEO EDITING" />
    <WorkPane imageSrc="/img/work2.png" text="3D DESIGN & GAME DESIGN" />
    <WorkPane imageSrc="/img/work3.png" text="PHOTOGRAPHY" />
  </div>
</template>

<script setup>
import WorkPane from '~/components/WorkPane.vue';
</script>

<style scoped>
.work-page {
  display: flex;
  flex-direction: column;
  height: 100vh;
  margin: 0;
}
</style>

