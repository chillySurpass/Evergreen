<template>
  <div class="home">
    <el-row :span="24">
      <el-col :span="5">
        <div class="left"></div>
      </el-col>
      <el-col :span="19" class="right">
        <div class="right-top"><homeBanner></homeBanner></div>
        <div class="right-bottom"></div>
      </el-col>
    </el-row>
  </div>
</template>

<script setup lang="ts">
import homeBanner from "@/views/home-banner/homeBanner.vue";
</script>

<style lang="scss">
.home {
  height: 100%;
  width: 100%;
}
.left {
  height: 100%;
  background-color: aqua;
}
.right {
  height: 100%;
}
.right-top {
  height: 150px;
  max-height: 150px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;

  > .card {
    width: 100%;
    overflow: hidden;
  }
}
.right-bottom {
  height: calc(100vh - 150px);
  background-color: burlywood;
}
</style>
