<template>
  <div class="flashing-text-container">
    <p class="flashing-text">Scroll to see showreel</p>
  </div>
</template>

<script>
export default {
  name: 'FlashingText',
};
</script>

<style scoped>
.flashing-text-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
  background-color: transparent;
}

.flashing-text {
  font-size: 1.5rem;
  color: white;
  animation: blink 2.5s infinite;
}

.flashing-text:hover {
  animation: none;
  opacity: 1;
}

@keyframes blink {

  0%,
  50%,
  100% {
    opacity: 1;
    /* Fully visible */
  }

  25%,
  75% {
    opacity: 0;
    /* Fully hidden */
  }
}
</style>
