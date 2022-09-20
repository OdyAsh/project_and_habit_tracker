<template>
  <aside :class="`${isExpanded ? 'isExpanded' : ''}`">
    <div class="logo">
      <img
        src="../assets/logo.png"
        alt="Transparent Clear Icon Png - Icon List Style Image Png, Png"
      />
    </div>
    <div class="menu-toggle-wrap">
      <button class="menu-toggle" @click="toggleMenu">
        <span class="material-icons"> keyboard_double_arrow_right </span>
      </button>
    </div>
  </aside>
</template>

<script setup>
import { ref } from "vue";
const isExpanded = ref(false);
const toggleMenu = () => {
  isExpanded.value = !isExpanded.value;
};
</script>

<style lang="scss" scoped>
aside {
  display: flex;
  flex-direction: column;
  width: calc(2rem + 2rem);
  min-height: 100vh;
  overflow: hidden;
  padding: 1rem;
  background-color: var(--dark);
  color: var(--light);
  transition: 0.2s ease-out;

  .logo {
    margin-bottom: 1rem;
    img {
      width: 2rem;
    }
  }

  @media (-webkit-device-pixel-ratio: 1) {
    @media (max-width: 46em) {
      position: fixed;
      z-index: 99;
    }
  }

  &.isExpanded {
    width: var(--sidebar-width);
  }

  @media (-webkit-device-pixel-ratio: 1.25) {
    @media (max-width: 46em) {
      position: fixed;
      z-index: 99;
    }
  }
  @media (max-width: calc(46em / 1.25)) and (-webkit-device-pixel-ratio: 1.25) {
    position: fixed;
    z-index: 99;
  }
}
</style>