<script setup lang="ts">
const props = defineProps<{
  textContent: string;
}>();
</script>

<template>
  <div class="DescriptionText">{{ props.textContent }}</div>
</template>

<style scoped>
div {
  text-align: center;
  font-size: 16px;
  line-height: 1.6;
  max-width: 600px;
}
</style>
