<template>
  <h1>Raffle</h1>
  <div class="p-grid">
    <div class="p-col-8 p-offset-2">
      <TextArea v-model="itemText" rows="20" class="width-100" />
    </div>
  </div>
  <div class="p-grid">
    <div class="p-col-6 p-offset-3">
      <Button label="抽選" class="width-100" @click="raffle" />
    </div>
  </div>

  <h2 class="p-text-center">
    選ばれたのは<br />
    {{ result }}<br />
    でした
  </h2>
</template>

<script>
export default {
  name: 'Raffle',
  data() {
    return {
      itemText: '',
      result: '',
    };
  },
  computed: {
    items() {
      return this.itemText.split('\n');
    },
  },
  methods: {
    raffle() {
      this.result = this.items[Math.floor(Math.random() * this.items.length)];
    },
  },
};
</script>

<style lang="scss">
.width-100 {
  width: 100%;
}
</style>
