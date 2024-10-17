<template>
  <div id="app" class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <div class="card bg-dark text-white shadow-sm">
          <div class="card-body">
            <h1 class="text-center mb-4">Calculadora Aritmética</h1>

            <div class="mb-3">
              <input
                v-model.number="numero1"
                type="number"
                class="form-control bg-dark text-white"
                placeholder="Insira o primeiro número"
              />
            </div>

            <div class="mb-3">
              <input
                v-model.number="numero2"
                type="number"
                class="form-control bg-dark text-white"
                placeholder="Insira o segundo número"
              />
            </div>

            <div class="mb-3">
              <select v-model="operacao" class="form-select bg-dark text-white">
                <option value="somar">Somar</option>
                <option value="subtrair">Subtrair</option>
                <option value="multiplicar">Multiplicar</option>
                <option value="dividir">Dividir</option>
              </select>
            </div>

            <p class="text-center fs-4 fw-bold">Resultado: {{ resultado }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'somar',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case 'somar':
          return this.numero1 + this.numero2;
        case 'subtrair':
          return this.numero1 - this.numero2;
        case 'multiplicar':
          return this.numero1 * this.numero2;
        case 'dividir':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro (divisão por zero)';
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
#app {
  margin-top: 50px;
}
.card {
  padding: 20px;
  border-radius: 10px;
}
.form-control, .form-select {
  border: 1px solid #6c757d;
}
</style>


