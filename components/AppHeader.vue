<template>
  <header class="header">
    <NuxtLink to="/" class="logo">
      <img src="/img/logo.png" alt="Website Logo" class="logo-image" />
    </NuxtLink>

    <BurgerMenu />
  </header>
</template>

<script>
import BurgerMenu from '~/components/BurgerMenu.vue';

export default {
  name: 'Head',
  components: {
    BurgerMenu,
  },
};
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 200px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  text-decoration: none;
}

.logo-image {
  height: 120px;
  width: auto;
  padding: 40px 40px;
}
</style>
