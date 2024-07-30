<template>
  <div class="container mt-5">
    <div class="form-group">
      <label for="number1">Número 1</label>
      <input type="number" v-model.number="number1" class="form-control" id="number1" />
    </div>
    <div class="form-group">
      <label for="number2">Número 2</label>
      <input type="number" v-model.number="number2" class="form-control" id="number2" />
    </div>
    <div class="form-group">
      <label for="operation">Operação</label>
      <select v-model="operation" class="form-control" id="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
    </div>
    <h3 class="mt-3">Resultado: {{ result }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add'
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number1 / this.number2;
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 400px;
}
</style>
