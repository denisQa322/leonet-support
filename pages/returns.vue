<script lang="ts" setup>
import { v4 as uuidv4 } from "uuid";

import Select from "~/components/select.vue";
import Input from "~/components/input.vue";

import AddIcon from "@/assets/icons/add-button.svg";

const inputs = [
  { label: "Референс", id: uuidv4() },
  { label: "Количество", id: uuidv4() },
  { label: "Стоимость", id: uuidv4() },
  { label: "Дата", id: uuidv4(), type: "date" },
];

const returnReason = [
  { label: "", value: "" },
  { label: "Повреждение", value: "Повреждение" },
  { label: "Неверное вложение", value: "Неверное вложение" },
  { label: "Брак", value: "Брак" },
  { label: "Б/У", value: "Б/У" },
  { label: "Некомплект/Недостача", value: "Некомплект/Недостача" },
];

const returnStatus = [
  { label: "", value: "" },
  { label: "Запрос получен", value: "Запрос получен" },
  { label: "Запрос отправлен", value: "Запрос отправлен" },
  { label: "Ответ получен", value: "Ответ получен" },
  { label: "Запрос на возврат", value: "Запрос на возврат" },
  { label: "Возврат получен", value: "Возврат получен" },
];
</script>

<template>
  <div class="return container">
    <div class="return-header">
      <h1>Возвраты</h1>
    </div>
    <div class="return-create">
      <div class="return-create-inputs">
        <Input v-for="input in inputs" :key="input.id" :label="input.label" />
      </div>
      <div class="return-create-selects">
        <Select selectLabel="Причина возврата" :options="returnReason" />
        <Select selectLabel="Статус возврата" :options="returnStatus" />
      </div>
      <button class="return-create-icon"><img :src="AddIcon" alt="" /></button>
    </div>
    <div class="return-info"></div>
  </div>
</template>

<style lang="scss" scoped>
@use "@/assets/styles/tovw.scss" as *;
.return {
  text-align: center;
  &-header {
    margin-bottom: toVw(25px);
  }
  &-create {
    display: flex;
    gap: toVw(60px);
    align-items: center;
    &-inputs {
      display: flex;
      justify-content: space-between;
      gap: toVw(60px);
    }
    &-selects {
      display: flex;
      justify-content: space-between;
      gap: toVw(60px);
    }
    &-icon {
      margin-left: auto;
      background: none;
      border: none;
      cursor: pointer;
      img {
        width: toVw(50px);
      }
    }
  }
}
</style>
