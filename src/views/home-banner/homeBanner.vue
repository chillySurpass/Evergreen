<template>
  <component class="card" :is="bannerComponent" />
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";

const bannerComponents = [
  "bilibili-spring-1-banner",
  "bilibili-spring-2-banner",
  "bilibili-spring-3-banner",
  "bilibili-spring-4-banner",
  "bilibili-spring-5-banner",
  "bilibili-spring-6-banner",
  "bilibili-summer-1-banner",
  "bilibili-summer-2-banner",
  "bilibili-summer-3-banner",
  "bilibili-summer-4-banner",
  "bilibili-summer-5-banner",
  "bilibili-summer-6-banner",
  "bilibili-summer-7-banner",
  "bilibili-autumn-1-banner",
  "bilibili-autumn-2-banner",
  "bilibili-autumn-3-banner",
  "bilibili-autumn-4-banner",
  "bilibili-autumn-5-banner",
  "bilibili-winter-1-banner",
  "bilibili-winter-2-banner",
  "bilibili-winter-3-banner",
  "bilibili-winter-4-banner",
  "bilibili-winter-5-banner",
];

const bannerComponent = ref(null);

onMounted(() => {
  const randomIndex = Math.floor(Math.random() * bannerComponents.length);
  import(`./banner/inst/${bannerComponents[randomIndex]}.component.vue`)
    .then((module) => {
      bannerComponent.value = module.default;
    })
    .catch((err) => {
      console.error("Error loading banner component:", err);
    });
});
</script>
