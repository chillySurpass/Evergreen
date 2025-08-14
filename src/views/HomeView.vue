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
          <homeFile :articles="articles" @select="openArticle" />
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script setup lang="ts">
import homeBanner from "@/views/home-banner/homeBanner.vue";
import homeNavigation from "@/views/home-navigation/homeNavigation.vue";
import homeFile from "@/views/home-file/homeFile.vue";

interface Article {
  title: string;
  summary: string;
  date: string;
}

const articles: Article[] = [
  {
    title: "Vue3 新特性解析",
    summary: "探索 Vue3 的 Composition API、Teleport、Suspense 等特性。",
    date: "2025-08-10",
  },
  {
    title: "JavaScript 性能优化技巧",
    summary: "如何在项目中优化性能，减少页面卡顿。",
    date: "2025-08-08",
  },
  {
    title: "前端组件化最佳实践",
    summary: "通过合理的组件拆分与封装，提高开发效率与可维护性。",
    date: "2025-08-05",
  },
  {
    title: "2024 年前端趋势",
    summary: "AI 辅助编程、WebAssembly、无服务器架构等趋势解析。",
    date: "2024-12-30",
  },
];

const openArticle = (article: Article) => {
  console.log("点击了文章:", article);
};
</script>

<style lang="scss" scoped>
:root {
  --top-height: 150px;
}

.home {
  height: 100vh;
  width: 100%;
  overflow: hidden;

  .full-height {
    display: flex;
    height: 100vh;
  }

  .left {
    height: 100%;
    background-color: #f6f7f8;
    overflow-y: auto;
    overflow-x: hidden;
  }

  .right {
    flex: 1;
    height: 100%;
    overflow-y: auto;
    overflow-x: hidden;
  }

  .right-top {
    height: var(--top-height);
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 16px;
    box-sizing: border-box;
  }

  .right-bottom {
    box-sizing: border-box;
  }
}
</style>
