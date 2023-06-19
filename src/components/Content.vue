<script setup>
    const props = defineProps(['selecionaOperacao', 'primeiroNumero', 'segundoNumero', 'editaPrimeiroNumero', 'editaSegundoNumero', 'editaSelect'])
</script>

<template>
    <div>
        <span>{{ props.primeiroNumero }}</span>
        <input @change="props.editaPrimeiroNumero" type="number"
            placeholder="Digite o primeiro valor">
    </div>
    <div class="operacao">
        <select @change="props.editaSelect">
            <option value="select">Selecione uma operação</option>
            <option value="soma">+</option>
            <option value="sub">-</option>
            <option value="div">÷</option>
            <option value="mult">x</option>
        </select>
    </div>
    <div>
        <span>{{ props.segundoNumero }}</span>
        <input @change="props.editaSegundoNumero" type="number"
            placeholder="Digite o segundo valor">
    </div>
    <div>
        <span>
            Resultado: {{ props.selecionaOperacao }}
        </span>
    </div>
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