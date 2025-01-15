<script lang="ts" setup>
import { ref } from "vue";

import { v4 as uuidv4 } from "uuid";

import AddIcon from "@/assets/icons/add-button.svg";

const reference = ref(0);
const quantity = ref(0);
const price = ref(0);
const date = ref("");

const returnReason = ref("");
const returnStatus = ref("Запрос получен");
const sellerName = ref("");
</script>

<template>
  <div class="return container">
    <div class="return-header">
      <h1>Возвраты</h1>
    </div>
    <div class="return-create">
      <div class="return-create-inputs">
        <div class="reference-input">
          <label for="reference">Референс</label>
          <input id="reference" v-model="reference" />
        </div>
        <div class="quantity-input">
          <label for="quantity">Количество</label>
          <input id="quantity" v-model="quantity" />
        </div>
        <div class="price-input">
          <label for="price">Стоимость</label>
          <input id="price" v-model="price" />
        </div>
        <div class="date-input">
          <label for="date">Дата</label>
          <input id="date" v-model="date" type="date" />
        </div>
      </div>
      <div class="return-create-selects">
        <div class="return-reason">
          <label>Причина возврата</label>
          <select v-model="returnReason">
            <option disabled value="">Выбери причину возврата</option>
            <option>Повреждение</option>
            <option>Неверное вложение</option>
            <option>Брак</option>
            <option>Б/У</option>
            <option>Некомплект/Недостача</option>
          </select>
        </div>
        <div class="seller-name">
          <label>Поставщик</label>
          <select v-model="sellerName">
            <option disabled value="">Выбери поставщика</option>
            <option>ЮГ</option>
            <option>EMEX</option>
            <option>РК</option>
            <option>АП</option>
          </select>
        </div>
      </div>
      <button class="return-create-icon"><img :src="AddIcon" alt="" /></button>
    </div>
    <div class="return-info">
      <div class="return-reference">
        <label>Референс</label>
        <p>{{ reference }}</p>
      </div>
      <div class="return-reference">
        <label>Количество</label>
        <p>{{ quantity }}</p>
      </div>
      <div class="return-reference">
        <label>Стоимость</label>
        <p>{{ price }}</p>
      </div>
      <div class="return-reference">
        <label>Дата</label>
        <p>{{ date }}</p>
      </div>
      <div class="return-reason">
        <label>Причина возврата</label>
        <p>{{ returnReason }}</p>
      </div>
      <div class="return-status">
        <label>Статус возврата</label>
        <p>{{ returnStatus }}</p>
        <select v-model="returnStatus">
          <option disabled value="">Выбери статус</option>
          <option>Запрос отправлен</option>
          <option>Ответ получен</option>
          <option>Запрос на возврат</option>
          <option>Возврат получен</option>
        </select>
      </div>
      <div class="return-seller">
        <label>Поставщик</label>
        <p>{{ sellerName }}</p>
      </div>
    </div>
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
    gap: toVw(40px);
    align-items: center;
    border-bottom: toVw(1px) solid #0067a4;
    padding-bottom: toVw(25px);
    &-inputs {
      display: flex;
      justify-content: space-between;
      gap: toVw(40px);
    }
    &-selects {
      display: flex;
      justify-content: space-between;
      gap: toVw(40px);
      .return-reason {
        display: flex;
        flex-direction: column;
      }
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
  &-info {
    padding-top: toVw(25px);
    display: flex;
    justify-content: space-between;
  }
}
</style>
