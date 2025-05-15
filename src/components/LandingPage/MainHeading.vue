<script setup lang="ts">
import PinSVG from '@/assets/LandingPage/locationPin.svg';
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
    <a class="location" href="https://maps.app.goo.gl/ikN2VCr4Md7ALRkc7">
      <img :src="PinSVG" alt="location" />
      Arlington, Virginia, USA
    </a>
  </div>
</template>

<style scoped>
.MainHeading {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.photo {
  height: 300px;
  width: 300px;
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 16px;

  @media (max-width: 769px) {
    height: 200px;
    width: 200px;
  }
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top center;
}

h1 {
  text-align: center;
  font-size: 60px;
  font-weight: 600;

  @media (max-width: 769px) {
    font-size: 42px;
  }
}

.location {
  margin-top: 8px;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 8px;
  color: var(--color-text-1);
  text-decoration: none;
}

.location img {
  width: 16px;
  height: 16px;
}
</style>
