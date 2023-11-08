<script setup>
import { reactive } from 'vue';

const calculo1 = reactive({
  ValorPrimario: '',
  Valorsecundario: '',
  operacoes: '',
  resultadoDaOperacao: 0,
})

const Calculo = () => {
  if (calculo1.ValorPrimario && calculo1.Valorsecundario) {

    if (calculo1.operacoes === 'soma') {
      calculo1.resultadoDaOperacao = Number(calculo1.ValorPrimario) + Number(calculo1.Valorsecundario)
      console.log(`calculo1`)
    }

    if (calculo1.operacoes === 'subtracao') {
      calculo1.resultadoDaOperacao = Number(calculo1.ValorPrimario) - Number(calculo1.Valorsecundario)
    }


    if (calculo1.operacoes === 'multiplicacao') {
      calculo1.resultadoDaOperacao = Number(calculo1.ValorPrimario) * Number(calculo1.Valorsecundario)
    }


    if (calculo1.operacoes === 'divisao') {
      calculo1.resultadoDaOperacao = Number(calculo1.ValorPrimario) / Number(calculo1.Valorsecundario)
    }
    return calculo1.resultadoDaOperacao
  }
}

const Valor1 = (event) => {
  calculo1.ValorPrimario = event.target.value
  Calculo()
}

const Valor2 = (event) => {
  calculo1.Valorsecundario = event.target.value
  Calculo()
}

const operacao = (event) => {
  calculo1.operacoes = event.target.value
  Calculo()
}
console.log(calculo1)


</script>

<template>
  <section class="section-principal">
    <div class="body">
      <h1>Calculadora Aritmética</h1>
      <span class="spann">Primeiro Número</span> <br />
      <input @change="Valor1" type="number"> <br /> <br>
      <span class="spann">Segundo Número</span> <br />
      <input @change="Valor2" type="number"> <br />
      <div class="select">
        <select @change="operacao" name="select">
        <option disabled selected value="">Selecione uma operação</option>
        <option value="soma">Soma</option>
        <option value="subtracao">Subtração</option>
        <option value="divisao">Divisão</option>
        <option value="multiplicacao">Multiplicação</option>
      </select>
      </div>
      <br />
      <div class="resultado">
        O resultado é {{ Calculo() }}
      </div>
    </div>
  </section>
</template>

<style scoped>

* {
  box-sizing: border-box;
}
.section-principal {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: black;
}

.body {
  padding: 40px;
  border: solid 3px black;
  align-items: center;
  text-align: center;
  background-color: rgb(224, 190, 190);
}

.style {
  padding: 10px;
}

input {
  padding: 5px;
  text-align: center;
}

.spann {
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 600;
}

.select {
  margin-top: 5px;
}

.select option {
  text-align: center;
}

.resultado {
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 900;
}

</style>
