<script setup>
import { reactive } from 'vue';

import Header from './components/Header.vue';
import Calculadora from './components/Calculadora.vue';


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
  
  <Header />

  <Calculadora
    :primeiro-valor="evento => estado.primeiroValor = evento.target.value"
    :segundo-valor="evento => estado.segundoValor = evento.target.value"
    :operador="evento => estado.operador = evento.target.value"
    :resultado="estado.resultado"
    :igual="igual()"
    
  />
</template>



<style scoped>


</style>
