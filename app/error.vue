<script setup lang="ts">
import type { NuxtError } from "#app";

const { error } = defineProps<{
  error: NuxtError;
}>();

const message = computed(() => {
  if (error.statusCode === 404) {
    return "Страница не найдена, попробуйте перейти на главную страницу";
  }

  return error.statusMessage;
});

const redirectToHomePage = () => {
  navigateTo("/");
};
</script>

<template>
  <div class="error">
    <UiTitle level="h1" style-level="h3">{{ error.statusCode }} ошибка</UiTitle>
    <p class="error--message">{{ message }}</p>
    <UiButton outlined @click="redirectToHomePage">Главная страница</UiButton>
  </div>
</template>

<style lang="css" scoped>
.error {
  display: grid;
  place-items: center;
  width: 100%;
  height: 100%;
  padding-top: 50%;
  margin: auto;
  transform: translateY(-50%);
}

.error--message {
  max-width: 430px;
  margin: 24px 0 64px;
  padding: 0;
  font-weight: 400;
  font-size: 20px;
  line-height: 26px;
  text-align: center;
  color: var(--color-dark-gray);
}
</style>
