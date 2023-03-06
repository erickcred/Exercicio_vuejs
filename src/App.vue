<script setup>
import { reactive } from 'vue';


const estado = reactive({
  resultado: 0,
  primeiroValor: 0,
  segundoValor: 0,
  operador: ""
});

const igual = () => {
  switch(estado.operador) {
      case "soma":
        estado.resultado = parseInt(estado.primeiroValor) + parseInt(estado.segundoValor)
        break;
      case "subtracao":
        estado.resultado = parseInt(estado.primeiroValor) - parseInt(estado.segundoValor);
        break;
      case "multiplicacao":
        estado.resultado = parseInt(estado.primeiroValor) * parseInt(estado.segundoValor);
        break;
      case "divisao":
        estado.resultado = parseInt(estado.primeiroValor) / parseInt(estado.segundoValor);
        break;
  
  }
}

</script>



<template>
  
  <header>
    <div class="container mt-5 mb-4">
      <h1 class="text-center">Calculadora</h1>
    </div>
  </header>

  <div class="container pt-4 pb-2 bg-dark position-relative rounded-3">
    <div class="row">
      <div class="col-4">
        <input @keyup="evento => estado.primeiroValor = evento.target.value" type="number" class="form-control" placeholder="Primeiro valor">
      </div>
      <div class="col-4">
        <input @keyup="evento => estado.segundoValor = evento.target.value" type="number" class="form-control" placeholder="Segundo valor">
      </div>
      <div class="col-4 d-flex">
        <select @change="evento => estado.operador = evento.target.value" class="form-control">
          <option value="">Operação</option>
          <option value="soma" class="fs-3">(+) <span class="fs-1">soma</span></option>
          <option value="subtracao" class="fs-3">(-) <span class="fs-5">subtração</span></option>
          <option value="multiplicacao" class="fs-3">(x) <span class="fs-5">multiplicação</span></option>
          <option value="divisao" class="fs-3">(/) <span class="fs-5">divisão</span></option>
        </select>
        <button @click="igual()" class="btn btn-secondary">=</button>
      </div>
      <div>
      </div>
      <p class="text-white text-center pt-3 fs-1 fw-bold">{{ estado.resultado }}</p>
    </div>
  </div>

</template>



<style scoped>


</style>
