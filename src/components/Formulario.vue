<template>
    <div class="formulario">
      <div class="row mb-4">
        <div class="col-4">
          <input @input="evento => estado.numero1 = evento.target.value" type="number" class="form-control border-2" placeholder="Numero 1">
        </div>
        <div class="col-md-1">
          <select @input="evento => estado.operacao = evento.target.value" class="form-select text-center">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
          </select>
        </div>
        <div class="col-md-4">
          <input @input="evento => estado.numero2 = evento.target.value" type="number" class="form-control" placeholder="Numero 2">
        </div>
      </div>
  
      <div class="row">
        <span class="resultado">Resultado: {{ realizaCalculo() }}</span>
      </div>
    </div>
  </template>
  
  <script setup>
  import { reactive } from 'vue';
  
  const estado = reactive({
    numero1: 0,
    numero2: 0,
    operacao: 'soma',
  })
  
  const realizaCalculo = () => {
    const numero1 = parseFloat(estado.numero1);
    const numero2 = parseFloat(estado.numero2);
    const operacao = estado.operacao;
  
    switch (operacao) {
      case 'soma':
        return numero1 + numero2;
      case 'subtracao':
        return numero1 - numero2;
      case 'multiplicacao':
        return numero1 * numero2;
      case 'divisao':
        return numero1 / numero2;
      default:
        return 0;
    }
  }
  </script>
  
  <style scoped>
    .resultado {
      font-size: 25pt;
      font-weight: 400;
    }
  </style>
  