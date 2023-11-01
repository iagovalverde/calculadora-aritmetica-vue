<script setup>
import { reactive } from 'vue';
import Calculadora from './components/Calculadora.vue';

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
  <Calculadora 
  :atualiza-numero1="atualizarNumero1" 
  :atualiza-numero2="atualizarNumero2" 
  :atualiza-operacao="atualizarOperacao"
  :calcula-resultado="calcularResultado()"
  />
</template>



