<script lang="ts" setup>
import { v4 as uuidv4 } from "uuid";

defineProps({
  selectLabel: {
    type: String,
    required: true,
  },
  options: {
    type: Array as () => { label: string; value: string }[],
    required: true,
  },
});

const id = uuidv4();
</script>

<template>
  <div class="select">
    <label for="id">{{ selectLabel }}</label>
    <select :id="id">
      <option
        v-for="option in options"
        :key="option.value"
        :value="option.value"
      >
        {{ option.label }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
@use "@/assets/styles/tovw.scss" as *;
.select {
  display: flex;
  flex-direction: column;
  label {
    margin-bottom: toVw(10px);
  }
  select {
    cursor: pointer;
    border-radius: toVw(7px);
    padding: toVw(10px) toVw(5px);
    border: toVw(1px) solid #000000;
    font-size: toVw(15px);
  }
}
</style>
