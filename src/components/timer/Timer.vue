<template>
  <h2>タイマー</h2>
  <div class="p-grid nested-grid">
    <div class="p-col-12">
      {{ formatTime }}
    </div>
    <div class="p-col-12 p-d-flex p-jc-center">
      <div class="p-col-4">
        <label for="hour">時</label>
        <InputText id="hour" v-model="hour" />
      </div>
      <div class="p-col-4">
        <label for="hour">分</label>
        <InputText id="minute" v-model="minute" />
      </div>
      <div class="p-col-4">
        <label for="hour">秒</label>
        <InputText id="second" v-model="second" />
      </div>
    </div>
    <div class="p-col-12 p-d-flex p-jc-center">
      <div class="p-col-4">
        <Button label="START" class="width-100" @click="raffle" />
      </div>
      <div class="p-col-4">
        <Button label="START" class="width-100" @click="raffle" />
      </div>
    </div>
  </div>
</template>

<script>
import { computed, ref } from '@vue/runtime-core';
export default {
  name: 'Timer',
  setup() {
    const hour = ref('00');
    const minute = ref('00');
    const second = ref('00');

    const formatTime = computed(() => {
      return `${hour.value}:${minute.value}:${second.value}`;
    });

    return {
      hour,
      minute,
      second,
      formatTime,
    };
  },
};
</script>

<style></style>
