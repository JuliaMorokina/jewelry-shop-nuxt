<script setup lang="ts">
const { level, styleLevel = undefined } = defineProps<{
  level: "h1" | "h2" | "h3";
  styleLevel?: "h1" | "h2" | "h3";
}>();
</script>

<template>
  <component :is="level" class="title" :class="`title--${styleLevel || level}`">
    <slot />
  </component>
</template>

<style lang="css" scoped>
.title {
  margin: 0;
  padding: 0;
  color: var(--color-black);
}

.title--h3 {
  font-weight: 500;
  font-size: 33px;
  line-height: 43px;
  text-align: center;
}
</style>
