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
    <div class="navigation-item">第二层</div>
    <div class="sub-line"></div>
    <!-- 第三层 -->
    <div class="navigation-item wide">第三层</div>
    <div class="sub-line"></div>
    <!-- 第四层 -->
    <div class="navigation-item">第四层</div>
  </div>
</template>

<script setup lang="ts"></script>

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
  gap: 6px; /* 每个 sub-item 之间的间距 */
}

.sub-item {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2px;
  text-align: center;

  &.name {
    font-size: 16px;
    color: gray;
    width: auto;
  }

  &.title {
    font-size: 18px;
    color: #333;
    position: relative;
    display: inline-block; /* 只包裹文字 */
    margin: 4px auto;
    padding: 0px 32px; /* 增加内边距，文字与边框距离更大 */
    width: auto; /* 取消继承的100%宽度 */

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

    /* 左上折角，往外偏移 */
    &::before {
      top: -2px;
      left: -2px;
      border-width: 2px 0 0 2px;
      transform-origin: top left;
    }

    /* 右下折角，往外偏移 */
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
    color: #000;
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
</style>
