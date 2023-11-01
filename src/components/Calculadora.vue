<script setup>
const props = defineProps(['atualizaNumero1', 'atualizaNumero2', 'atualizaOperacao', 'calculaResultado'])
</script>
<template>
    <h1>Calculadora Aritmética</h1>
    <div class="calc">
        <input @keyup="props.atualizaNumero1" type="number" placeholder="Digite o primeiro numero">
        <input @keyup="props.atualizaNumero2" type="number" placeholder="Digite o segundo numero">
        <select @change="props.atualizaOperacao">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
        </select>
        <span>
            {{ props.calculaResultado }}
        </span>
    </div>
</template>
<style scoped>
    .calc,
    h1 {
        text-align: center;
    }

    input,
    select {
        padding: 6px;
        font-size: 20px;
    }

    span {
        margin-left: 12px;
        font-size: 20px;
    }
</style>