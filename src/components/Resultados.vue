<script setup>
  defineProps(['produto', 'formulario'])
</script>

<template>
  <div v-if="formulario" class="resultado">
    <h2>Dados do produto</h2>
    <p>Nome: {{ produto.nome }}</p>
    <p>Email: {{ produto.email }}</p>
    <p>Senha: {{ produto.senha }}</p>
    <p>Data de Nascimento: {{ produto.datadenascimento }}</p>
    <p>Endereço: {{ produto.endereco }}</p>
    <p>Cidade: {{ produto.cidade }}</p>
    <p>Estado: {{ produto.estado }}</p>
    <p>Hobbies: {{ produto.hobbies }}</p>
    <p>Linguagens de Programação: {{ produto.linguagensdeprogramacao }}</p>
    <p>Biografia: {{ produto.biografia }}</p>
  </div>

  <div class="altera-titulo">
    <label>Informe um novo título </label>
    <input class="form-control" type="text" v-model="titulo" />
  </div>
</template>
<style scoped>

</style>
