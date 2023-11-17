<template>
  <div id="app" class="container mt-4">
    <div class="row">
      <div class="col-md-4 offset-md-4 calculator">
        <header>
          <h1 class="header-text">
            Calculadora
          </h1>
        </header>
        <label for="numero1" class="label">NÚMERO 1:</label>
        <input v-model.number="numero1" type="number" class="input text-black">

        <label for="numero2" class="label">NÚMERO 2:</label>
        <input v-model.number="numero2" type="number" class="input text-black">

        <label for="operacao" class="label">OPERAÇÃO:</label>
        <select v-model="operacao" class="select text-black">
          <option value="+" class="option">+ SOMAR</option>
          <option value="-" class="option">- SUBTRAIR</option>
          <option value="*" class="option">X MULTIPLICAR</option>
          <option value="/" class="option">÷ DIVIDIR</option>
        </select>

        <div class="result">
          <strong>RESULTADO:</strong> {{ calcularResultado }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: '0',
      numero2: '0',
      operacao: '+',
    };
  },
  computed: {
    calcularResultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2;
        case '-':
          return this.numero1 - this.numero2;
        case '*':
          return this.numero1 * this.numero2;
        case '/':
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 15px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #000;
}

header {
  text-align: center;
  margin-bottom: 20px;
}

.header-text {
  color: #fff;
}

.label,
.input,
.select,
.result {
  color: #fff;
}

.text-black {
  color: black;
}

.input,
.select {
  width: 100%;
  padding: 8px;
  margin: 6px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
  background-color: #eceff1;
}

.select {
  appearance: none;
  background-color: orange;
}

.option:checked {
  background-color: grey;
  color: #fff;
}
</style>