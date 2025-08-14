<template>
  <div class="article-timeline">
    <!-- 顶部总览 -->
    <div class="timeline-summary">
      <div class="summary-row">
        <span class="summary-icon">📦</span>
        <span class="summary-title">归档</span>
      </div>
      <div class="summary-count">共计 {{ totalArticles }} 篇文章</div>
    </div>

    <el-timeline>
      <!-- 年份分组 -->
      <template v-for="(yearArticles, year) in groupedArticles" :key="year">
        <!-- 年份节点 -->
        <el-timeline-item
          :timestamp="year"
          placement="top"
          type="primary"
          hollow
        >
          <div class="year-label">
            <span>{{ year }}</span>
            <div class="year-bar"></div>
          </div>
        </el-timeline-item>

        <!-- 年份下文章 -->
        <el-timeline-item
          v-for="(article, index) in yearArticles"
          :key="`${year}-${index}`"
          :timestamp="formatDate(article.date)"
          placement="top"
        >
          <el-card
            shadow="hover"
            class="article-card"
            @click="onClick(article)"
          >
            <h3 class="title">{{ article.title }}</h3>
            <p class="summary">{{ article.summary }}</p>
          </el-card>
        </el-timeline-item>
      </template>
    </el-timeline>
  </div>
</template>

<script setup lang="ts">
import { computed, defineProps, defineEmits } from "vue";

interface Article {
  title: string;
  summary: string;
  date: string; // YYYY-MM-DD
}

const props = defineProps<{
  articles: Article[];
}>();

const emit = defineEmits<{
  (e: "select", article: Article): void;
}>();

const onClick = (article: Article) => {
  emit("select", article);
};

const formatDate = (dateStr: string) => {
  const [, month, day] = dateStr.split("-");
  return `${month}-${day}`;
};

// 按年份分组，倒序
const groupedArticles = computed(() => {
  const groups: Record<string, Article[]> = {};
  props.articles.forEach((article) => {
    const year = article.date.split("-")[0];
    if (!groups[year]) groups[year] = [];
    groups[year].push(article);
  });

  return Object.fromEntries(
    Object.entries(groups).sort(([a], [b]) => Number(b) - Number(a))
  );
});

// 总文章数
const totalArticles = computed(() => props.articles.length);
</script>

<style lang="scss" scoped>
.article-timeline {
  padding: 20px;
  background-color: #f9fcff;
  overflow-y: auto;

  /* 顶部总览 */
  .timeline-summary {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 40px;
    gap: 4px;

    .summary-row {
      display: flex;
      align-items: center;
      gap: 8px;

      .summary-icon {
        font-size: 18px;
      }

      .summary-title {
        font-size: 22px;
        font-weight: bold;
        color: #1a4f7a;
      }
    }

    .summary-count {
      font-size: 18px;
      color: #4a90e2;
    }
  }

  /* 年份节点 */
  .year-label {
    display: flex;
    align-items: center;
    gap: 12px;

    span {
      font-size: 20px;
      font-weight: bold;
      color: #1a4f7a;
      background: #e6f2ff;
      padding: 4px 12px;
      border-radius: 14px;
      border: 1px solid #a6c8e0;
    }

    .year-bar {
      flex: 1;
      height: 4px;
      border-radius: 2px;
      background: linear-gradient(to right, #a6c8e0, #e6f2ff);
    }
  }

  /* 文章卡片 */
  .article-card {
    cursor: pointer;
    transition: all 0.3s ease;
    border-radius: 8px;
    border: 1px solid #d6e9f8;
    background: #ffffff;

    &:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 12px rgba(64, 158, 255, 0.15);
      border-color: #a6c8e0;
    }

    &:active {
      transform: translateY(0);
      box-shadow: 0 2px 4px rgba(64, 158, 255, 0.1);
    }

    .title {
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 6px;
      color: #1a4f7a;
    }

    .summary {
      font-size: 14px;
      color: #4a90e2;
    }
  }

  :deep(.el-timeline-item__node--primary) {
    border-color: #409eff;
    background-color: #409eff;
  }
}
</style>
