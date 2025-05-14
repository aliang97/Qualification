<script setup lang="ts">
import BrandList from './BrandList.vue';
import MainContent from './MainContent.vue';
</script>

<template>
  <div class="AboutMe background">
    <div class="container">
      <h2>Professional Experience</h2>
      <MainContent />
    </div>
    <BrandList />
  </div>
</template>

<style scoped>
.AboutMe {
  --color-bg-1: var(--color-blue-1);
  --color-text-1: var(--color-white-1);

  width: 100%;
  padding: 72px 0;
  color: var(--color-text-1);

  @media (max-width: 769px) {
    padding: 32px 0;
  }
}

.background {
  background-color: var(--color-bg-1);
}

h2 {
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 32px;
}
</style>
