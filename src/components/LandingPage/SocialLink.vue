<script setup lang="ts">
const props = defineProps<{
  href: string;
  icon: string;
  label: string;
}>();
</script>

<template>
  <a class="SocialLink" :class="label" :href="props.href">
    <div class="ImageBg"></div>
    <img :src="props.icon" />
    <div class="label">{{ props.label }}</div>
  </a>
</template>

<style scoped>
.SocialLink {
  display: flex;
  flex-direction: row;
  gap: 16px;
  align-items: center;
}

a {
  text-decoration: none;
  font-size: 16px;
  color: var(--color-text-1);
  position: relative;
  transition: all 0.4s ease;
  z-index: 1;
  padding-right: 16px;
}

a:hover {
  color: #000;
}

a:hover .ImageBg {
  width: 100%;
}

.ImageBg {
  background-color: var(--color-text-1);
  border-radius: 20px;
  height: 40px;
  width: 40px;
  position: absolute;
  top: 50%;
  left: 0;
  transform: translate(0%, -50%);
  transition: all 0.4s ease;
  z-index: -1;
}

img {
  width: 24px;
  height: 24px;
  z-index: 1;
  margin: 8px;
}

.LinkedIn img {
  width: 20px;
  height: 20px;
  margin: 10px;
}

.GitHub img,
.Email img {
  width: 30px;
  height: 30px;
  margin: 5px;
}
</style>
