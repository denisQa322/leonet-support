<script lang="ts" setup></script>

<template>
  <div class="header container">
    <div class="header-img">
      <NuxtLink to="/">
        <img src="../assets/images/support-main-icon.png" alt="" />
      </NuxtLink>
    </div>
    <nav class="header-navigation">
      <NuxtLink to="/returns" class="link">Возвраты</NuxtLink>
      /
      <NuxtLink to="/rejects" class="link">Отказы</NuxtLink>
    </nav>
  </div>
</template>

<style lang="scss" scoped>
@use "@/assets/styles/tovw.scss" as *;
.header {
  text-align: center;
  color: #0067a4;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: toVw(20px);
  &-img {
    cursor: pointer;
    img {
      height: toVw(50px);
      width: toVw(50px);
    }
  }

  &-navigation {
    display: flex;
    gap: toVw(5px);
    font-size: toVw(25px);
    .link {
      cursor: pointer;
      text-decoration: none;
    }
  }
}
</style>
