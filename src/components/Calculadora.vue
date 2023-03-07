<script setup>
    const props = defineProps(['primeiroValor', 'segundoValor', 'operador', 'resultado', 'igual'])
</script>

<template>
  <div class="container pt-4 pb-2 bg-dark position-relative rounded-3">
    <div class="row">
      <div class="col-4">
        <input
          @change="props.primeiroValor"
          type="number"
          class="form-control"
          placeholder="Primeiro valor"
        />
      </div>
      <div class="col-4">
        <input
          @keyup="props.segundoValor"
          type="number"
          class="form-control"
          placeholder="Segundo valor"
        />
      </div>
      <div class="col-4 d-flex">
        <select
          @change="props.operador"
          class="form-control"
        >
          <option value="">Operação</option>
          <option @click="igual()" value="soma" class="fs-3">
            (+) <span class="fs-1">soma</span>
          </option>
          <option @click="igual()" value="subtracao" class="fs-3">
            (-) <span class="fs-5">subtração</span>
          </option>
          <option @click="igual()" value="multiplicacao" class="fs-3">
            (x) <span class="fs-5">multiplicação</span>
          </option>
          <option @click="igual()" value="divisao" class="fs-3">
            (/) <span class="fs-5">divisão</span>
          </option>
        </select>
      </div>
      <div></div>
      <p class="text-white text-center pt-3 fs-1 fw-bold">
        {{ props.resultado }}
      </p>
    </div>
  </div>
</template>
