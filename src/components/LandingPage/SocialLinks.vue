<script setup lang="ts">
import SocialLink from './SocialLink.vue';
defineProps<{
  socialData: {
    href: string;
    icon: string;
    label: string;
  }[];
}>();
</script>

<template>
  <div class="SocialLinks">
    <template v-for="data in socialData" :key="data.label">
      <SocialLink v-bind="data" />
    </template>
  </div>
</template>

<style scoped>
.SocialLinks {
  display: flex;
  flex-direction: row;
  gap: 32px;
  margin: 32px 0;

  @media (max-width: 769px) {
    flex-direction: column;
    gap: 16px;
  }
}
</style>
