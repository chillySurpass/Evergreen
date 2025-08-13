<template>
  <div class="home">
    <el-row class="full-height" gutter="0">
      <!-- 左侧导航 -->
      <el-col :span="5" class="left">
        <homeNavigation />
      </el-col>

      <!-- 右侧内容 -->
      <el-col :span="19" class="right">
        <div class="right-top">
          <homeBanner />
        </div>
        <div class="right-bottom">
          <!-- 未来可放文章列表/内容 -->
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script setup lang="ts">
import homeBanner from "@/views/home-banner/homeBanner.vue";
import homeNavigation from "@/views/home-navigation/homeNavigation.vue"; // 修正拼写
</script>

<style lang="scss" scoped>
/* 高度变量，方便统一调整 */
:root {
  --top-height: 150px;
}

.home {
  height: 100vh;
  width: 100%;
  overflow: hidden;
}

.full-height {
  height: 100%;
}

.left {
  height: 100%;
  background-color: #f6f7f8;
}

.right {
  height: 100%;
  display: flex;
  flex-direction: column;
}

.right-top {
  height: var(--top-height);
  max-height: var(--top-height);
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 16px;
  box-sizing: border-box;
}

.right-bottom {
  flex: 1; /* 自动填满剩余空间 */
  background-color: burlywood;
  overflow-y: auto;
}
</style>
