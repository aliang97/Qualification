<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  pageScrollPercent: number;
}>();
const pageScrollPercentString = computed(() => `${props.pageScrollPercent}%`);
</script>

<template>
  <div class="NavProgress">
    <div class="progress"></div>
  </div>
</template>

<style scoped>
.NavProgress {
  position: absolute;
  height: calc(var(--size-navItem-Y) * var(--amount-navItems));
  width: 4px;
  top: 32px;
  left: 32px;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 9;
}

.progress {
  margin: calc(var(--size-navItem-Y) / 4) 0;
  border-radius: 2px;
  width: 4px;
  background: linear-gradient(
    to bottom,
    var(--color-active) v-bind(pageScrollPercentString),
    var(--color-inactive) v-bind(pageScrollPercentString)
  );
  flex-grow: 1;
}
</style>
