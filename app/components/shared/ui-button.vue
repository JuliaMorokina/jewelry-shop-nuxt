<script setup lang="ts">
const { outlined = false } = defineProps<{
  outlined?: boolean;
}>();
</script>

<template>
  <button class="button" :class="{ 'button-outlined': outlined }">
    <slot />
  </button>
</template>

<style lang="css" scoped>
.button {
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 156px;
  max-height: 53px;
  padding: 16px;

  font-size: 16px;
  font-weight: 700;
  border: 1px solid var(--color-black);
  background-color: var(--color-black);
  color: var(--color-white);
  border-radius: 4px;
  cursor: pointer;
  transition: 0.3s;
}

.button:hover,
.button-outlined {
  background-color: transparent;
  color: var(--color-black);
}

.button-outlined:hover {
  background-color: var(--color-black);
  color: var(--color-white);
}
</style>
