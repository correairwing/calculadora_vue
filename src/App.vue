<script setup>
import { reactive } from 'vue';

const estado = reactive({
  operacao: 'select',
  primeiroNumero: 0,
  segundoNumero: 0,
  resultado: 0,
})

function subtraiInputs() {
  const {primeiroNumero, segundoNumero} = estado;
  return (primeiroNumero + segundoNumero);
}


</script>

<template>
  <main class="container ">
      <div>
        <span>{{ estado.primeiroNumero }}</span>
        <input @change="evento => estado.primeiroNumero = evento.target.value" type="number" placeholder="Digite o primeiro valor">
      </div>
      <div class="operacao">
        <select>
          <option value="select">Selecione uma operação</option>
          <option value="soma">+</option>
          <option value="sub">-</option>
          <option value="div">÷</option>
          <option value="mult">x</option>
        </select>
      </div>
      <div>
        <span>{{ estado.segundoNumero }}</span>
        <input @change="evento => estado.segundoNumero = evento.target.value" type="number" placeholder="Digite o segundo valor">
      </div>
      <div>
        <span>
          Resultado: {{ subtraiInputs() }}
        </span>
      </div>
  </main>
</template>

<style scoped>
  div {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    background-color: #a3a3a3;
    height: 30vh
  }

  input {
    width: 100%;
  }

  span {
    font-size: 80px;
  }

  .operacao {
    height: auto;
  }

  select {
    width: 100%;
  }
</style>
