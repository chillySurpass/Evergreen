<template>
  <div class="common-layout">
    <el-container>
      <el-aside width="200px">Aside</el-aside>
      <el-header>
        <div class="container">
          <div class="card">
            <BilibiliAutumn1BannerComponent></BilibiliAutumn1BannerComponent>
          </div>
        </div>
      </el-header>
      <el-main>Main</el-main>
      <el-footer>Footer</el-footer>
    </el-container>
  </div>
</template>

<script setup lang="ts">
import BilibiliAutumn1BannerComponent from "@/views/banner/inst/bilibili-autumn-1-banner.component.vue";
</script>

<style lang="scss">
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;

  > .card {
    width: 800px;
    border-radius: 8px;
    box-shadow: 4px 4px 4px 4px rgba(0, 0, 0, 0.25);
    overflow: hidden;
  }
}
</style>
