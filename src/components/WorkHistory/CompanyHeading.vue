<script setup lang="ts">
import OpenLinkSVG from '@/assets/WorkHistory/NewTab.svg';

const props = defineProps<{
  logoSrc?: string;
  name: string;
  website?: string;
  tenure?: string;
  title?: string;
}>();
</script>

<template>
  <div class="CompanyHeading">
    <div class="left">
      <div v-if="props.logoSrc" class="logo">
        <img :src="props.logoSrc" alt="company logo" />
      </div>
      <h3>{{ props.name }}</h3>
      <div v-if="props.title" class="title">{{ props.title }}</div>
      <a v-if="props.website" :href="props.website" target="_blank">
        {{ props.website }}
        <img :src="OpenLinkSVG" alt="Open Link in New Tab" />
      </a>
    </div>
    <div class="tenure" v-if="props.tenure">{{ props.tenure }}</div>
  </div>
</template>

<style scoped>
.CompanyHeading {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 8px 16px;
  background-color: #ddd;
  min-height: 48px;

  @media (max-width: 769px) {
    flex-direction: column;
  }
}

.left {
  display: flex;
  flex-direction: row;
  align-items: baseline;
  flex-grow: 1;
  gap: 8px;
  position: relative;
  padding-left: 56px;

  @media (max-width: 769px) {
    flex-direction: column;
    gap: 2px;
  }
}

.logo {
  border-radius: 50%;
  height: 40px;
  width: 40px;
  position: absolute;
  left: 0;
  top: 50%;
  transform: translate(0%, -50%);
}

img {
  width: 100%;
  height: 100%;
}

h3 {
  font-size: 20px;
  font-weight: 500;
}

.title {
  font-weight: 500;
  font-size: 16px;
}

.title::before {
  content: '-';
  margin-right: 8px;
}

a {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 999px;
  padding: 8px 16px;
  color: var(--color-text-1);
}

a:hover {
  background-color: #ccc;
}

a > img {
  width: 12px;
  height: 12px;
  margin-left: 4px;
}

.tenure {
  font-size: 16px;

  @media (max-width: 769px) {
    margin-top: 8px;
  }
}
</style>
