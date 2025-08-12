<template>
  <BilibiliBannerBaseComponent
    :baseSrc="baseSrc"
    :marginLeft="marginLeft"
    :moveRate="moveRate"
    :imgData="imgData"
  >
  </BilibiliBannerBaseComponent>
</template>
<script setup lang="ts">
import BilibiliBannerBaseComponent from "@/views/home-banner/banner/base/bilibili-banner-base.component.vue";
import type { OriDataType } from "../base/bilibili-banner-base.type";

const baseSrc = "/bilibili/spring-4/";
const marginLeft = -40;
const moveRate = -2;
const imgData: Array<OriDataType> = [
  {
    type: "image",
    file: "2e81e0644044fafd5e72de3e595d7db6f65122ef.png@3840w_360h_1c_90q.webp",
    width: 1920 * 0.9,
    height: 180 * 0.9,
    x: 0,
    newX: 1,
    bench: 1,
  },
];
</script>
