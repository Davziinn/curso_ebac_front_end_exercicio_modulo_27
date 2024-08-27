<template>
  <div id="app">
    <div class="calculator">
      <input v-model.number="num1" type="number" placeholder="Digite o primeiro número">
      <input v-model.number="num2" type="number" placeholder="Digite o segundo número">
      <select v-model="operation">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
    </div>
    <div class="result">
      <p>
        Resultado: {{ result }}
      </p>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: '+'
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case '+':
          return this.num1 + this.num2;
        case '-':
          return this.num1 - this.num2;
        case '*':
          return this.num1 * this.num2;
        case '/':
          return this.num2 !== 0 ? this.num1 / this.num2 : 'Divisão por zero';
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}
input, select {
  margin: 10px;
  padding: 10px;
  font-size: 16px;
}
.result {
  margin-top: 20px;
  font-size: 18px;
  font-weight: bold;
}
</style>
