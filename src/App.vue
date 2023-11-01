<script setup>
import { reactive } from 'vue';

const estado = reactive({
  operacao: '',
  numero1: null,
  numero2: null,
})

const calcularResultado = () => {
  const { operacao, numero1, numero2} = estado;
  
  switch (operacao) {
    case 'subtracao':
      return numero1 - numero2;
    case 'multiplicacao':
      return numero1 * numero2;
    case 'divisao':
      return numero1 / numero2;
    default:
      return numero1 + numero2;
    }
}

const atualizarOperacao = (e) => {
  estado.operacao = e.target.value;
}

const atualizarNumero1 = (e) => {
  estado.numero1 = parseFloat(e.target.value);
}

const atualizarNumero2 = (e) => {
  estado.numero2 = parseFloat(e.target.value);
}

</script>

<template>
  <div class="container">
    <h1>Calculadora Aritmética</h1>
    <div class="calc">
      <input @keyup="atualizarNumero1" type="number" placeholder="Digite o primeiro numero">
      <input @keyup="atualizarNumero2" type="number" placeholder="Digite o segundo numero">
      <select @change="atualizarOperacao">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">x</option>
        <option value="divisao">/</option>
      </select>
      <span>
        {{ calcularResultado() }}
      </span>
    </div>
  </div>
</template>

<style scoped>
  .calc, h1 {
    text-align: center;
  }

  input, select {
    padding: 6px;
    font-size: 20px;
  }

  span {
    margin-left: 12px;
    font-size: 20px;
  }
</style>

