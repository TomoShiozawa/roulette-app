<template>
  <h1>Raffle</h1>
  <div class="p-grid nested-grid">
    <div class="p-col-6">
      <div class="p-col-12">
        <label for="itemtext">抽選するものを入力(改行区切り)</label>
        <TextArea
          id="itemtext"
          v-model="itemText"
          rows="20"
          class="width-100"
        />
      </div>
      <div class="p-col-12">
        <Button label="抽選" class="width-100" @click="raffle" />
      </div>
    </div>
    <div class="p-col-6">
      <h2 class="p-text-center">
        選ばれたのは<br />
        {{ result }}<br />
        でした
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
      result: '',
    };
  },
  computed: {
    items() {
      return this.itemText.split('\n');
    },
    pieChartData() {
      return {
        labels: this.items,
        datasets: [
          {
            data: this.items.map(() => 1),
            backgroundColor: this.items.map(
              () =>
                '#' +
                `000000${Math.floor(Math.random() * 16777215).toString(
                  16
                )}`.slice(-6)
            ),
          },
        ],
      };
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
