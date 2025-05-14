<script setup lang="ts">
import { ref } from 'vue';
defineProps<{
  imageSrc: string;
  label: string;
}>();
const isFlipped = ref(false);

const mouseEnter = () => {
  isFlipped.value = true;
};
const mouseLeave = () => {
  setTimeout(() => {
    isFlipped.value = false;
  }, 500);
};
</script>

<template>
  <div class="HexagonScene">
    <div
      class="HexagonCard"
      :class="isFlipped ? 'is-flipped' : ''"
      v-on:mouseenter="mouseEnter"
      v-on:mouseleave="mouseLeave"
    >
      <div class="HexagonFront">
        <div class="Hexagon">
          <img class="hexagonImage" :class="label" :src="imageSrc" alt="" />
        </div>
      </div>
      <div class="HexagonBack">
        <div class="Hexagon">
          <img class="hexagonImage" :class="label" :src="imageSrc" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.HexagonScene {
  perspective: 600px;
}

.HexagonCard {
  position: relative;
  transition: transform 1s;
  transform-style: preserve-3d;
}

.HexagonCard.is-flipped {
  transform: rotateY(180deg);
}

.HexagonFront,
.HexagonBack {
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  height: 100%;
  width: 100%;
  backface-visibility: hidden;
}

.HexagonBack {
  transform: rotateY(180deg);
}

.Hexagon {
  height: 100px; /* adjust to control the size  */
  aspect-ratio: 1 / cos(30deg);
  clip-path: polygon(50% -50%, 100% 50%, 50% 150%, 0 50%);
  display: flex;
  align-items: center;
  justify-content: center;
}

.HexagonFront .Hexagon {
  background: var(--color-white-1);
}

.HexagonBack .Hexagon {
  background: var(--color-blue-2);
}

img {
  width: 60px;
  height: 60px;
}
</style>
