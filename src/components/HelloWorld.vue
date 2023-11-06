<template>
  <div>
    <input v-model="firstNumber" type="text" />
    <select v-model="operator">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model="secondNumber" type="text" />
    <button @click="calculate">Calculate</button>
    <p>Result: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstNumber: "",
      operator: "+",
      secondNumber: "",
      result: 0
    };
  },
  methods: {
    calculate() {
      const num1 = parseFloat(this.firstNumber);
      const num2 = parseFloat(this.secondNumber);

      switch (this.operator) {
        case "+":
          this.result = num1 + num2;
          break;
        case "-":
          this.result = num1 - num2;
          break;
        case "*":
          this.result = num1 * num2;
          break;
        case "/":
          this.result = num1 / num2;
          break;
      }
    }
  }
};
</script>
