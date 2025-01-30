<template>
  <div class="home-image-container">
    <img src="/img/homeimg.png" alt="Home Image" class="home-image" />
  </div>
</template>

<script>
export default {
  name: 'HomeImage',
};
</script>

<style scoped>
.home-image-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.home-image {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}
</style>
