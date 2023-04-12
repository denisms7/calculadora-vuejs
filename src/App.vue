<script setup>
import { reactive } from 'vue';

const estado = reactive({
  num1: parseFloat(0),
  num2: parseFloat(0),
  operador: '+',
  resultado: 0,

});

function calculo() {
    switch (estado.operador) {
      case '+':
        return estado.resultado = parseFloat(estado.num1) + parseFloat(estado.num2);

      case '-':
        return estado.resultado = parseFloat(estado.num1) - parseFloat(estado.num2);

      case '*':
        return estado.resultado = parseFloat(estado.num1) * parseFloat(estado.num2);

      case '/':
        return estado.resultado = parseFloat(estado.num1) / parseFloat(estado.num2);

      default:
        return estado.resultado = 0;
    }
}
</script>


<template>
  <div class="container ">
    <header class="my-5">
      <h1>Calculadora Aritmética</h1>
      <p>
        Projeto utilizando VueJS <br>
        <a href="https://github.com/denisms7/calculadora-vuejs" target="_blank">Repositório GitHub</a>
      </p>
    </header>

    <section>
      <div class="row">

        <div class="col-md-2">
          <label for="num11" class="form-label">Numero 1:</label>
          <input @keyup="evento => { estado.num1 = evento.target.value; calculo(); }" type="text" placeholder="0" class="form-control" id="num11">
        </div>

        <div class="col-md-1">
          <label for="operacao" class="form-label">Operador:</label>
          <select @change="evento => {estado.operador = evento.target.value; calculo()}" class="form-select" id="operacao">
            <option selected value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
        </div>

        <div class="col-md-2">
          <label for="num22" class="form-label">Numero 2:</label>
          <input @keyup="evento => {estado.num2 = evento.target.value; calculo()}" type="text" placeholder="0" class="form-control" id="num22">
        </div>

        <div class="col-md-2">
          <label for="resultado" class="form-label">Resultado</label>
          <div class="form-control" id="resultado">{{ estado.resultado }}</div>
        </div>

      </div>
    </section>

  </div>
</template>


<style scoped>

</style>
