<template>
  <div class="container">
    <div class="card" v-if="randomBanner === 'spring1'">
      <BilibiliSpring1BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'spring2'">
      <BilibiliSpring2BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'spring3'">
      <BilibiliSpring3BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'spring4'">
      <BilibiliSpring4BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'spring5'">
      <BilibiliSpring5BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'spring6'">
      <BilibiliSpring6BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer1'">
      <BilibiliSummer1BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer2'">
      <BilibiliSummer2BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer3'">
      <BilibiliSummer3BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer4'">
      <BilibiliSummer4BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer5'">
      <BilibiliSummer5BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer6'">
      <BilibiliSummer6BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'summer7'">
      <BilibiliSummer7BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'autumn1'">
      <BilibiliAutumn1BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'autumn2'">
      <BilibiliAutumn2BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'autumn3'">
      <BilibiliAutumn3BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'autumn4'">
      <BilibiliAutumn4BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'autumn5'">
      <BilibiliAutumn5BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'winter1'">
      <BilibiliWinter1BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'winter2'">
      <BilibiliWinter2BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'winter3'">
      <BilibiliWinter3BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'winter4'">
      <BilibiliWinter4BannerComponent />
    </div>
    <div class="card" v-if="randomBanner === 'winter5'">
      <BilibiliWinter5BannerComponent />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import BilibiliSpring1BannerComponent from "@/views/banner/inst/bilibili-spring-1-banner.component.vue";
import BilibiliSpring2BannerComponent from "@/views/banner/inst/bilibili-spring-2-banner.component.vue";
import BilibiliSpring3BannerComponent from "@/views/banner/inst/bilibili-spring-3-banner.component.vue";
import BilibiliSpring4BannerComponent from "@/views/banner/inst/bilibili-spring-4-banner.component.vue";
import BilibiliSpring5BannerComponent from "@/views/banner/inst/bilibili-spring-5-banner.component.vue";
import BilibiliSpring6BannerComponent from "@/views/banner/inst/bilibili-spring-6-banner.component.vue";
import BilibiliSummer1BannerComponent from "@/views/banner/inst/bilibili-summer-1-banner.component.vue";
import BilibiliSummer2BannerComponent from "@/views/banner/inst/bilibili-summer-2-banner.component.vue";
import BilibiliSummer3BannerComponent from "@/views/banner/inst/bilibili-summer-3-banner.component.vue";
import BilibiliSummer4BannerComponent from "@/views/banner/inst/bilibili-summer-4-banner.component.vue";
import BilibiliSummer5BannerComponent from "@/views/banner/inst/bilibili-summer-5-banner.component.vue";
import BilibiliSummer6BannerComponent from "@/views/banner/inst/bilibili-summer-6-banner.component.vue";
import BilibiliSummer7BannerComponent from "@/views/banner/inst/bilibili-summer-7-banner.component.vue";
import BilibiliAutumn1BannerComponent from "@/views/banner/inst/bilibili-autumn-1-banner.component.vue";
import BilibiliAutumn2BannerComponent from "@/views/banner/inst/bilibili-autumn-2-banner.component.vue";
import BilibiliAutumn3BannerComponent from "@/views/banner/inst/bilibili-autumn-3-banner.component.vue";
import BilibiliAutumn4BannerComponent from "@/views/banner/inst/bilibili-autumn-4-banner.component.vue";
import BilibiliAutumn5BannerComponent from "@/views/banner/inst/bilibili-autumn-5-banner.component.vue";
import BilibiliWinter1BannerComponent from "@/views/banner/inst/bilibili-winter-1-banner.component.vue";
import BilibiliWinter2BannerComponent from "@/views/banner/inst/bilibili-winter-2-banner.component.vue";
import BilibiliWinter3BannerComponent from "@/views/banner/inst/bilibili-winter-3-banner.component.vue";
import BilibiliWinter4BannerComponent from "@/views/banner/inst/bilibili-winter-4-banner.component.vue";
import BilibiliWinter5BannerComponent from "@/views/banner/inst/bilibili-winter-5-banner.component.vue";

const banners = [
  "spring1",
  "spring2",
  "spring3",
  "spring4",
  "spring5",
  "spring6",
  "summer1",
  "summer2",
  "summer3",
  "summer4",
  "summer5",
  "summer6",
  "summer7",
  "autumn1",
  "autumn2",
  "autumn3",
  "autumn4",
  "autumn5",
  "winter1",
  "winter2",
  "winter3",
  "winter4",
  "winter5",
];

const randomBanner = ref("");

onMounted(() => {
  const randomIndex = Math.floor(Math.random() * banners.length);
  randomBanner.value = banners[randomIndex];
});
</script>
<style lang="scss">
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;

  > .card {
    width: 100%;
    border-radius: 0px;
    box-shadow: 4px 4px 4px 4px rgba(0, 0, 0, 0.25);
    overflow: hidden;
  }
}
</style>
