<template>
    <h1>asjdasdgasdg</h1>

    <input type="text" v-model="value1" placeholder="Valor 1">
    <input type="text" v-model="value2" placeholder="Valor 2">

    <button v-on:click="displayResult('+')" type="button"> + </button>
    <button v-on:click="displayResult('-')" type="button"> - </button>
    <button v-on:click="displayResult('*')" type="button"> * </button>
    <button v-on:click="displayResult('/')" type="button"> / </button>
</template>

<script>
    export default {
        name: 'CCalculadora',
        data: () => ({
            value1: '',
            value2: ''
        }),
        methods: {
            displayResult(operacao) {
                if(operacao == '/' && (this.value1 == 0 && this.value2 == 0)) {
                    alert('Essa operação não é permitida :)');
                    this.value1 = '';
                    this.value2 = '';
                    return;
                }

                let resultado = eval(`${this.value1} ${operacao} ${this.value2}`);
                alert(`${this.value1} ${operacao} ${this.value2} = ${resultado}`);
            }
        }
    }
</script>

<style scoped>
    h1 {
        color: red;
    }
</style>