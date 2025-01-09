<script setup lang="ts">
import { v4 as uuidv4 } from "uuid";

defineProps({
  label: {
    type: String,
    default: "",
    required: true,
  },
  id: {
    type: String,
    default: () => uuidv4(),
  },
  type: {
    type: String,
    default: "text",
    required: false,
  },
});
</script>

<template>
  <div class="input">
    <label v-if="label" :for="id" class="input-label">{{ label }}</label>
    <input :id="id" :type="type" />
  </div>
</template>

<style scoped lang="scss">
@use "@/assets/styles/tovw.scss" as *;
.input {
  display: flex;
  flex-direction: column;
  label {
    margin-bottom: toVw(10px);
  }
  input {
    padding: toVw(10px) toVw(5px);
    border-radius: toVw(7px);
    border: toVw(1px) solid #000000;
    font-size: toVw(15px);
  }
}
</style>
