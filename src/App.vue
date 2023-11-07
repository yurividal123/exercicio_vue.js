<script setup>
  import { reactive } from 'vue';
  
  const calculo1 = reactive( {
    ValorPrimario: '',
    Valorsecundario: '',
    Operacoes: '',
    ResultadoDaOperacao: '',
  })

  const Calculo = () => {
    if(calculo1.ValorPrimario && calculo1.Valorsecundario){


if ( calculo1.Operacoes === 'somar'){
  calculo1.ResultadoDaOperacao =  Number(calculo1.ValorPrimario) + Number(calculo1.Valorsecundario)
  }

  if ( calculo1.Operacoes === 'subtrair'){
    calculo1.ResultadoDaOperacao =  Number(calculo1.ValorPrimario) - Number(calculo1.Valorsecundario)
  }

  
  if ( calculo1.Operacoes === 'multiplicar'){
    calculo1.ResultadoDaOperacao =  Number(calculo1.ValorPrimario) * Number(calculo1.Valorsecundario)
  }
  

  if ( calculo1.Operacoes === 'dividir'){
    calculo1.ResultadoDaOperacao =  Number(calculo1.ValorPrimario) / Number(calculo1.Valorsecundario)
  }
  console.log(calculo1.Operacoes)
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

  const Operacao = (event) => {
    calculo1.ValorDaOperacao = event.target.value
  }


</script>

<template>
<div class="body">
  <section class="section-principal">
    <h1>Calculadora Aritmética</h1>
    <span>Primeiro Número</span> <br />
    <input @change="Valor1" type="number"> <br />
    <span>Segundo Número</span> <br />
    <input @change="Valor2" type="number"> <br />
    <select @change="Operacao" name="select">
  <option value="soma">Soma</option>
  <option value="subtracao">Subtração</option>
  <option value="divisao">Divisão</option>
  <option value="multiplicacao">Multiplicação</option>
</select>
    <br />
    O resultado é {{ calculo1.ResultadoDaOperacao }}
  </section>
</div>
</template>

<style scoped>
  .body {
    width: 100%;
    height: 100vh;
    text-align: center;
  } 
  .section-principal {

  }
</style>
