<template>
  <h2>進数変換するやつ</h2>
  <div class="p-grid p-nested-grid p-jc-center">
    <div class="p-field p-col-12 p-sm-6">
      <label for="decimalnumber">10進数</label>
      <InputText
        id="decimalnumber"
        v-model="decimalNumber"
        class="input-text"
        @input="changeNumbers(decimalNumber, 10)"
      />
    </div>
    <div class="p-field p-col-12 p-sm-6">
      <label for="binarynumber">2進数</label>
      <InputText
        id="binarynumber"
        v-model="binaryNumber"
        class="input-text"
        @input="changeNumbers(binaryNumber, 2)"
      />
    </div>
    <div class="p-field p-col-12 p-sm-6">
      <label for="octalnumber">8進数</label>
      <InputText
        id="octalnumber"
        v-model="octalNumber"
        class="input-text"
        @input="changeNumbers(octalNumber, 8)"
      />
    </div>
    <div class="p-field p-col-12 p-sm-6">
      <label for="hexadecimalnumber">16進数</label>
      <InputText
        id="hexadecimalnumber"
        v-model="hexadecimalNumber"
        class="input-text"
        @input="changeNumbers(hexadecimalNumber, 16)"
      />
    </div>
    <div class="p-field p-col-12 p-sm-6">
      <Dropdown
        v-model="selectedBase"
        :options="selectBases"
        option-label="name"
        option-value="base"
        @change="changeNumbers(selectedBaseNumber, selectedBase)"
      />
      <InputText
        v-model="selectedBaseNumber"
        class="input-text"
        @input="changeNumbers(selectedBaseNumber, selectedBase)"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'BaseConverter',
  data() {
    return {
      masterNum: 0,
      selectedBase: 10,
      decimalNumber: null,
      binaryNumber: null,
      octalNumber: null,
      hexadecimalNumber: null,
      selectedBaseNumber: null,
      selectBases: [...Array(31).keys()].map((val) => {
        return { name: `${val + 2}進数`, base: val + 2 };
      }),
    };
  },
  methods: {
    changeNumbers(input, base) {
      if (!input) {
        return;
      }
      this.masterNum = parseInt(input, base);

      this.decimalNumber = this.masterNum.toString(10);
      this.binaryNumber = this.masterNum.toString(2);
      this.octalNumber = this.masterNum.toString(8);
      this.hexadecimalNumber = this.masterNum.toString(16);
      this.selectedBaseNumber = this.masterNum.toString(this.selectedBase);
    },
  },
};
</script>

<style lang="scss">
.input-text {
  width: 100%;
}
</style>
