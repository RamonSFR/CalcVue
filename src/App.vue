<script setup>
import Cabecalho from './components/Cabecalho.vue';
import { reactive } from 'vue';

const estado = reactive({
  numero1: '',
  numero2: '',
  operacao: 'soma',
})


</script>

<template>
  <div class="container p-5">
    <Cabecalho/>
    <div class="formulario">
      <div class="row mb-4">
        <div class="col-4">
          <input type="number" class="form-control border-2" placeholder="Numero 1">
        </div>
        <div class="col-md-1">
          <select class="form-select text-center">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
          </select>
        </div>
        <div class="col-md-4">
          <input type="number" class="form-control" placeholder="Numero 2">
        </div>
      </div>

      <div class="row">
        <span class="resultado">Resultado: 45</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .resultado {
    font-size: 25pt;
    font-weight: 400;
  }
</style>
