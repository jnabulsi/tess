<template>
  <div class="hamburger-menu">
    <!-- Menu Button -->
    <div class="menu-btn" :class="{ close: isMenuOpen }" @click="toggleMenu">
      <div class="btn-line"></div>
      <div class="btn-line"></div>
      <div class="btn-line"></div>
    </div>

    <!-- Navigation Menu -->
    <nav class="menu" :class="{ show: isMenuOpen }">
      <ul class="menu-nav">
        <li class="nav-item" v-for="(item, index) in menuItems" :key="index">
          <NuxtLink :to="item.route" class="nav-link" @click.native="toggleMenu">
            {{ item.name }}
          </NuxtLink>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "HamburgerMenu",
  data() {
    return {
      isMenuOpen: false,
      menuItems: [
        { name: "About", route: "/about" },
        { name: "Work", route: "/work" },
        { name: "Contact", route: "/contact" },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<style scoped>
.hamburger-menu {
  position: relative;
  z-index: 10;
}

/* Menu Button */
.menu-btn {
  position: fixed;
  z-index: 3;
  top: 20px;
  right: 20px;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 80px;
  height: 80px;
  transition: transform 0.5s ease;
}

.menu-btn .btn-line {
  width: 60px;
  height: 8px;
  margin: 8px 0;
  background-color: white;
  border-radius: 4px;
  transition: transform 0.5s ease, opacity 0.5s ease;
}

/* Close State */
.menu-btn.close {
  transform: rotate(180deg);
}

.menu-btn.close .btn-line:nth-child(1) {
  transform: rotate(45deg) translate(17px, 17px);
  background-color: orange;
}

.menu-btn.close .btn-line:nth-child(2) {
  opacity: 0;
}

.menu-btn.close .btn-line:nth-child(3) {
  transform: rotate(-45deg) translate(17px, -17px);
  background-color: orange;
}

/* Menu */
.menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  justify-content: center;
  align-items: center;
  visibility: hidden;
  opacity: 0;
  transition: opacity 0.5s ease, visibility 0.5s ease;
  transition-delay: 0s;
  z-index: 2;
}

.menu.show {
  visibility: visible;
  opacity: 1;
}

/* Navigation Links */
.menu-nav {
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;
}

.nav-item {
  margin: 80px 0;
}

.nav-link {
  color: white;
  font-size: 4rem;
  text-decoration: none;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: orange;
}
</style>
