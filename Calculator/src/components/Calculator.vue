<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="input-group">
      <input v-model.number="number1" type="number" placeholder="Insira o primeiro número" />
      <select v-model="operation">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input v-model.number="number2" type="number" placeholder="Insira o segundo número" />
    </div>
    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
    };
  },
  computed: {
    result() {
      let result = 0;
      switch (this.operation) {
        case '+':
          result = this.number1 + this.number2;
          break;
        case '-':
          result = this.number1 - this.number2;
          break;
        case '*':
          result = this.number1 * this.number2;
          break;
        case '/':
          result = this.number1 / this.number2;
          break;
      }
      return result;
    },
  },
};
</script>

<style scoped>
.calculator {
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  text-align: center;
}

.input-group {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.input-group input,
.input-group select {
  width: 30%;
  padding: 10px;
  margin: 5px;
}

.result {
  font-size: 1.5em;
  font-weight: bold;
}
</style>

