<script setup>
import { reactive } from 'vue';
import Content from './components/Content.vue'

const estado = reactive({
  operacao: 'select',
  primeiroNumero: 0,
  segundoNumero: 0,
  resultado: 0,
})

function subtraiInputs() {
  const {primeiroNumero, segundoNumero} = estado;
  return (primeiroNumero - segundoNumero);
}

function somaInputs() {
  const {primeiroNumero, segundoNumero} = estado;
  return parseInt(primeiroNumero) + parseInt(segundoNumero);
}

function multiplicaInputs() {
  const {primeiroNumero, segundoNumero} = estado;
  return (primeiroNumero * segundoNumero);
}

function divideInputs() {
  const {primeiroNumero, segundoNumero} = estado;
  return (primeiroNumero / segundoNumero);
}

function selecionaOperacao() {
  const { operacao } = estado;

  switch (operacao) {
    case 'soma':
      return somaInputs();
    case 'sub':
      return subtraiInputs();
    case 'div':
      return divideInputs();
    case 'mult':
      return multiplicaInputs();
    default:
      return 'Selecione uma operação'
  }
}

</script>

<template>
  <div class="container ">
    <Content :seleciona-operacao="selecionaOperacao()" :primeiro-numero="estado.primeiroNumero" :edita-primeiro-numero="event => estado.primeiroNumero = event.target.value" :segundo-numero="estado.segundoNumero" :edita-segundo-numero="event => estado.segundoNumero = event.target.value" :edita-select="event => estado.operacao = event.target.value" />
  </div>
</template>

<style scoped>

</style>
