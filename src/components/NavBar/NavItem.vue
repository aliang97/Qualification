<script setup lang="ts">
const props = defineProps<{
  label: string;
  cssSelector: string;
  isActive: boolean;
}>();

const gotoNavItem = () => {
  const sectionElement = document.querySelector(props.cssSelector);
  if (!sectionElement) {
    return;
  }

  const sectionTopCoord = sectionElement.getBoundingClientRect().top + window.scrollY;
  window.scrollTo({ top: sectionTopCoord, behavior: 'smooth' });
};
</script>

<template>
  <div class="NavItem">
    <button class="interactable" @click="gotoNavItem">
      <div class="icon" :class="props.isActive ? 'active' : 'inactive'"></div>
      <div class="label">{{ props.label }}</div>
    </button>
  </div>
</template>

<style scoped>
.NavItem {
  padding: 16px 0;
}

.interactable {
  padding: 16px 20px;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 20px;
  width: 100%;
}

.interactable:hover {
  cursor: pointer;
  background-color: blue;
}

.icon {
  flex-shrink: 0;
  border-radius: 50%;
  height: 24px;
  width: 24px;
  position: relative;
  z-index: 10;
}

.icon.active {
  background-color: var(--color-active);
}

.icon.inactive {
  background-color: var(--color-inactive);
}

.icon::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 16px;
  height: 16px;
  background-color: var(--color-bg-1);
  border-radius: 50%;
}

.label {
  text-wrap: nowrap;
  font-size: 16px;
  font-weight: 600;
  color: var(--color-text-1);
}
</style>
