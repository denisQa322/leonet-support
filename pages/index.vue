<script lang="ts" setup></script>

<template>
  <div class="main container">
    <div class="main-info">
      <h1 class="main-info-header">
        Добро пожаловать в
        <span class="main-info-header-span"
          >систему управления заказами(СУЗ)</span
        >
      </h1>
      <p class="main-info-text">
        Данная система предназначена для учета по
        <NuxtLink to="/returns" class="link">возвратам</NuxtLink>
        и
        <NuxtLink to="/rejects" class="link">отменам</NuxtLink>
        заказов
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "@/assets/styles/tovw.scss" as *;

.main {
  text-align: center;
  padding-top: toVw(100px);
  &-info {
    &-header {
      font-size: toVw(50px);
      padding-bottom: toVw(150px);
      display: flex;
      flex-direction: column;
      font-weight: 400;
      &-span {
        font-weight: 800;
      }
    }
    &-text {
      font-size: toVw(30px);
      .link {
        text-decoration: underline;
        cursor: pointer;
      }
    }
  }
}
</style>
