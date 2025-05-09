<script setup lang="ts">
import { ref } from 'vue';
import NavItem from './NavItem.vue';
import NavProgress from './NavProgress.vue';

const isHovered = ref(false);
const mouseIn = () => {
  isHovered.value = true;
};
const mouseOut = () => {
  isHovered.value = false;
};

const pageScrollPercent = ref(5);
window.addEventListener('scroll', () => {
  const pageHeight = document.body.scrollHeight - window.innerHeight;
  const scrollY = window.scrollY;
  pageScrollPercent.value = Math.max(Math.round((scrollY * 100) / pageHeight), 5);
});

const itemIsActive = (amountItems: number, index: number, pageScrollPercent: number) => {
  const threshold = Math.round((100 / (amountItems - 1)) * index);
  return pageScrollPercent >= threshold;
};

const navItems = [
  {
    label: 'Home',
    cssSelector: '.LandingPage',
  },
  {
    label: 'Work History',
    cssSelector: '.WorkHistory',
  },
  {
    label: 'About Me',
    cssSelector: '.AboutMe',
  },
  {
    label: 'Contact Me',
    cssSelector: '.ContactMe',
  },
];
</script>

<template>
  <div class="sticky">
    <nav
      class="NavBar"
      :class="isHovered ? 'expanded' : 'collapsed'"
      @mouseover="mouseIn"
      @mouseout="mouseOut"
    >
      <template v-for="(item, idx) in navItems" :key="item">
        <NavItem v-bind="item" :isActive="itemIsActive(navItems.length, idx, pageScrollPercent)" />
      </template>
      <NavProgress :pageScrollPercent="pageScrollPercent" />
    </nav>
  </div>
</template>

<style scoped>
.sticky {
  position: sticky;
  top: 0;
  left: 0;
  z-index: 10;
}

.NavBar {
  --color-inactive: #777;
  --color-active: var(--color-text-1);
  --size-navItem-Y: 88px;
  --amount-navItems: 4;

  position: absolute;
  height: 100vh;
  background-color: var(--color-bg-2);
  transition: width 0.2s ease;
  padding: 32px 0;
  overflow: hidden;
}

.NavBar.collapsed {
  width: 64px;
}

.NavBar.expanded {
  width: 200px;
}
</style>
