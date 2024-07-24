<script setup>
import Resultados from './components/Resultados.vue';
import Formulario from './components/Formulario.vue';

</script>

<template>
   <header>
    <h1 class="titulo">{{ titulo }}</h1>
  </header>

  <main>
    <Formulario />
    <Resultados />

  </main>
  </template>
      

<style scoped>
main {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.formulario,
.resultado {
  border-radius: 20px;
  padding: 20px;
  font-family: 'Times New Roman', Times, serif;
}

.formulario {
  background-color: black;
  color: white;
  font-family: 'Times New Roman', Times, serif;
  width: 30%;
  height: 90%;
}

.formulario h2 {
  text-align: center;
}

.resultado {
  background-color: black;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  max-width: 40%;
  max-height: 90%;
  width: 100%;
  height: 100%;
  overflow-y: auto;
  word-break: break-all;
  gap: 5px;
}

.resultado p {
  padding: 1px;
}

.resultado h2 {
  text-align: center;
}

.altera-titulo {
  background-color: black;
  color: white;
  margin: 3rem 3rem;
  border-radius: 20px;
  padding: 0.75rem;
  font-family: 'Times New Roman', Times, serif;
  display: flex;
  width: 20%;
  height: 10%;
  flex-direction: column;
}

.principal {
  display: flex;
  flex-wrap: wrap;
  height: 70vh;
  align-items: center;
  justify-content: center;
  width: 100%;
  gap: 20px;
}

.form-group label {
  font-size: 25px;
}

.form-group {
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-top: 5px;
}
.titulo {
  text-align: center;
}

.caixa-btn {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.btn {
  border-radius: 20px;
  padding: 10px 20px;
  border: none;
}
</style>
