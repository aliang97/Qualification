<script setup lang="ts">
import DataNasa from './DataNasa.vue';
import DataSimonComputing from './DataSimonComputing.vue';
import DataYext from './DataYext.vue';
</script>

<template>
  <div class="WorkHistory background">
    <div class="container">
      <h2>Resume</h2>
      <DataYext />
      <DataSimonComputing />
      <DataNasa />
    </div>
  </div>
</template>

<style scoped>
.WorkHistory {
  --color-bg-1: var(--color-white-1);
  --color-text-1: var(--color-black-1);

  width: 100%;
  min-height: 100vh;
  padding: 72px 0;

  @media (max-width: 769px) {
    padding: 32px 0;
  }
}

.background {
  background-color: var(--color-bg-1);
  color: var(--color-text-1);
}

h2 {
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 16px;
}
</style>
