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

const baseSrc = "/bilibili/winter-2/";
const marginLeft = -45;
const moveRate = -2;
const imgData: Array<OriDataType> = [
  {
    type: "image",
    file: "f97330ca7905307f539b2af1f64fa2a2fdb4eaed.webp",
    width: 1920 * 0.9,
    height: 180 * 0.9,
    x: 0,
    newX: 1,
    bench: 1,
  },
];
</script>
