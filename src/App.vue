<script setup>
  import { reactive } from 'vue';
  
  const calculo1 = reactive( {
    ValorPrimario: '',
    Valorsecundario: '',
    operacoes: '',
    resultadoDaOperacao: 0,
  })
  
  const Calculo = () => { 
    if(calculo1.ValorPrimario && calculo1.Valorsecundario){
      
if ( calculo1.operacoes === 'soma'){
  calculo1.resultadoDaOperacao =  Number(calculo1.ValorPrimario) + Number(calculo1.Valorsecundario)
  console.log(`calculo1`)
  }

  if ( calculo1.operacoes === 'subtracao'){
    calculo1.resultadoDaOperacao =  Number(calculo1.ValorPrimario) - Number(calculo1.Valorsecundario)
  }

  
  if ( calculo1.operacoes === 'multiplicacao'){
    calculo1.resultadoDaOperacao =  Number(calculo1.ValorPrimario) * Number(calculo1.Valorsecundario)
  }
  

  if ( calculo1.operacoes === 'divisao'){
    calculo1.resultadoDaOperacao =  Number(calculo1.ValorPrimario) / Number(calculo1.Valorsecundario)
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
<div class="body">
  <section class="section-principal">
    <h1>Calculadora Aritmética</h1>
    <span>Primeiro Número</span> <br />
    <input @change="Valor1" type="number"> <br />
    <span>Segundo Número</span> <br />
    <input @change="Valor2" type="number"> <br />
    <select @change="operacao" name="select">
  <option disabled selected value="">Selecione uma operação</option>
  <option value="soma">Soma</option>
  <option value="subtracao">Subtração</option>
  <option value="divisao">Divisão</option>
  <option value="multiplicacao">Multiplicação</option>
</select>
    <br />
    O resultado é {{ Calculo() }}
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
