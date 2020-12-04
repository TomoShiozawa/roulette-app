<template>
  <h1>Raffle</h1>
  <div class="p-grid nested-grid">
    <div class="p-col-6">
      <div class="p-col-12">
        <label for="itemtext">抽選するものを入力してください(改行区切り)</label>
        <TextArea
          id="itemtext"
          v-model="itemText"
          rows="20"
          class="width-100"
        />
      </div>
      <div class="p-col-12">
        <span>選ぶ個数</span>
        <InputNumber v-model="num" />
      </div>
      <div class="p-col-12">
        <Button label="抽選" class="width-100" @click="raffle" />
      </div>
    </div>
    <div class="p-col-6">
      <h2 class="p-text-center">選ばれたのは</h2>
      <h2 v-for="(result, index) in results" :key="index" class="p-text-center">
        {{ result }}
      </h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Raffle',
  data() {
    return {
      itemText: '',
      results: [],
      num: 1,
    };
  },
  computed: {
    items() {
      return this.itemText.split('\n');
    },
  },
  methods: {
    raffle() {
      this.results = [];
      const copyItems = JSON.parse(JSON.stringify(this.items));

      for (let i = 0; i < this.num; i++) {
        const randomNum = Math.floor(Math.random() * copyItems.length);
        const result = copyItems[randomNum];
        this.results.push(result);
        copyItems.splice(randomNum, 1);
      }
    },
  },
};
</script>

<style lang="scss">
.width-100 {
  width: 100%;
}
</style>
