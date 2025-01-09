<script lang="ts" setup>
defineProps({
  reasonOption: {
    type: String,
    required: false,
  },
  statusOption: {
    type: String,
    required: false,
  },
});
</script>

<template>
  <div class="return container">
    <div class="return-header">
      <h1>Возвраты</h1>
    </div>
    <div class="return-create">
      <div class="return-reason">
        <select name="" id="">
          <option>reasonOption</option>
        </select>
      </div>
      <select class="return-status">
        <option>statusOption</option>
      </select>
    </div>
    <div class="return-info"></div>
  </div>
</template>

<style lang="scss" scoped>
.return {
  text-align: center;
}
</style>
