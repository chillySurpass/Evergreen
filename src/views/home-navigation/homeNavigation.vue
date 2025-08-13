<template>
  <div class="navigation">
    <!-- 第一层 -->
    <div class="navigation-item first-layer">
      <div class="sub-item avatar">
        <img class="circle-image" src="/10/10.jpg" alt="头像" />
      </div>
      <div class="sub-item name">长青</div>
      <div class="sub-item title">长青的小站</div>
      <div class="sub-item web">Ever Green.</div>
      <div class="sub-item slogan">深渊在我后背 想晒到太阳只有我的墓碑</div>
    </div>
    <div class="sub-line"></div>
    <!-- 第二层 -->
    <div class="navigation-item second-layer">
      <div
        class="block"
        :class="{ selected: selectedIndex === 0 }"
        @click="handleClick(0)"
      >
        <div class="icon">📦</div>
        <div class="text">归档</div>
        <div class="count">12</div>
      </div>
      <div
        class="block"
        :class="{ selected: selectedIndex === 1 }"
        @click="handleClick(1)"
      >
        <div class="icon">📂</div>
        <div class="text">分类</div>
        <div class="count">8</div>
      </div>
      <div
        class="block"
        :class="{ selected: selectedIndex === 2 }"
        @click="handleClick(2)"
      >
        <div class="icon">🏷️</div>
        <div class="text">标签</div>
        <div class="count">20</div>
      </div>
    </div>
    <div class="sub-line"></div>
    <!-- 第三层 -->
    <div class="navigation-item wide">第三层</div>
    <div class="sub-line"></div>
    <!-- 第四层 -->
    <div class="navigation-item">第四层</div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const selectedIndex = ref<number | null>(null);

const handleClick = (index: number) => {
  selectedIndex.value = index;
};
</script>

<style lang="scss" scoped>
.navigation {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}

.sub-line {
  width: 100%;
  height: 1px;
  margin: 10px 0;
  background: linear-gradient(
    to right,
    rgba(169, 169, 169, 0) 0%,
    rgba(169, 169, 169, 0.8) 50%,
    rgba(169, 169, 169, 0) 100%
  );
}

.navigation-item {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  text-align: center;

  &.wide {
    flex: 2;
  }
}

/* 第一层样式 */
.navigation-item.first-layer {
  flex: 3;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  gap: 6px;
}

.sub-item {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2px;
  text-align: center;

  &.name {
    font-size: 16px;
    color: #6c757d;
    font-weight: 600;
    width: auto;
  }

  &.title {
    font-size: 18px;
    color: #333;
    position: relative;
    display: inline-block;
    margin: 4px auto;
    padding: 0px 32px;
    width: auto;

    &::before,
    &::after {
      content: "";
      position: absolute;
      width: 8px;
      height: 8px;
      border-color: black;
      border-style: solid;
      transform: scale(0);
      transition: transform 0.25s ease;
    }

    &::before {
      top: -2px;
      left: -2px;
      border-width: 2px 0 0 2px;
      transform-origin: top left;
    }

    &::after {
      bottom: -2px;
      right: -2px;
      border-width: 0 2px 2px 0;
      transform-origin: bottom right;
    }

    &:hover::before,
    &:hover::after {
      transform: scale(1);
    }
  }

  &.web {
    font-size: 12px;
    color: #222;
    width: auto;
  }

  &.slogan {
    font-size: 16px;
    color: #000;
    width: auto;
  }

  &.avatar {
    margin-bottom: 12px;
  }
}

.circle-image {
  width: 95px;
  height: 95px;
  border: 3px solid #fff;
  border-radius: 50%;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1), 0 1px 3px rgba(0, 0, 0, 0.08),
    0 0 30px 20px rgba(173, 216, 230, 0.3),
    0 0 30px 20px rgba(221, 160, 221, 0.3);
  transition: all 0.3s ease;

  &:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15),
      0 0 40px 25px rgba(173, 216, 230, 0.3),
      0 0 40px 25px rgba(221, 160, 221, 0.3);
  }
}

/* 第二层样式 */
.second-layer {
  width: 100%;
  display: flex;
  justify-content: space-between;
  gap: 6px; /* 间距减小 */
}

.second-layer .block {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  cursor: pointer;
  padding: 8px;
  border-radius: 8px;
  transition: all 0.2s ease;
  background-color: transparent;
}

.second-layer .block:hover {
  background-color: rgba(0, 0, 0, 0.05);
  transform: translateY(-2px);
}

.second-layer .block.selected {
  background-color: rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}

.second-layer .block:active {
  transform: translateY(0);
}

.second-layer .icon {
  font-size: 24px;
}

.second-layer .text {
  font-size: 14px;
  font-weight: 600;
  color: #333;
}

.second-layer .count {
  font-size: 12px;
  color: #555;
}
</style>
