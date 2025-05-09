<script setup lang="ts">
const props = defineProps<{
  photo: string;
  heading: string;
}>();
</script>

<template>
  <div class="MainHeading">
    <div class="photo">
      <img :src="props.photo" alt="Alex Liang's Photo" />
    </div>
    <h1>{{ props.heading }}</h1>
  </div>
</template>

<style scoped>
.MainHeading {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
}

.photo {
  height: 300px;
  width: 300px;
  border-radius: 50%;
  overflow: hidden;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top center;
}

h1 {
  font-size: 60px;
  font-weight: 600;
}
</style>
