<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Oi VueJs!')
const mostrarResultado = ref(false)

const produto = reactive({
  nome: '',
  email: '',
  senha: '',
  datadenascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagensdeprogramacao: '',
  biografia:'',
})

</script>

<template>
   <h1>{{ titulo }}</h1>
  <div class="container d-flex flex-row gap-3">
    <div class="formulario">
      <h2>Cadastro do produto</h2>

      <div class="form-group">
        <label for="">Nome:</label>
        <input class="form-control" type="text" v-model="produto.nome" />
      </div>

      <div class="form-group">
        <label for="">Email</label>
        <input class="form-control" type="text" v-model="produto.email" />
      </div>

      <div class="form-group">
        <label for="">senha:</label>
        <input class="form-control" type="password" v-model="produto.senha" />
      </div>

      <div class="form-group">
        <label for="">Data de Nascimento</label>
        <input type="form-control" typeof="number" v-model="produto.datadenascimento" />
      </div>

      <div class="form-group">
        <label for="">Endereço</label>
        <input type="form-control" typeof="text" v-model="produto.endereco" />
      </div>

      <div class="form-group">
        <label for="">Cidade</label>
        <input type="form-control" typeof="text" v-model="produto.cidade" />
      </div>

      <div class="form-group">
        <label for="">Estado</label>
        <select type="form-control" name="estado" id="estado" v-model="produto.estado">
          <option value="ac">Acre</option>
          <option value="al">Alagoas</option>
          <option value="ap">Amapá</option>
          <option value="am">Amazonas</option>
          <option value="ba">Bahia</option>
          <option value="ce">Ceará</option>
          <option value="df">Destrito Federal</option>
          <option value="es">Espírito Santo</option>
          <option value="go">Goiás</option>
          <option value="ma">Maranhão</option>
          <option value="mt">Mato Grosso</option>
          <option value="ms">Mato Grosso do Sul</option>
          <option value="mg">Minas Gerais</option>
          <option value="pa">Pará</option>
          <option value="pb">Paraíba</option>
          <option value="pr">Paraná</option>
          <option value="pe">Pernambuco</option>
          <option value="pi">Piauí</option>
          <option value="rj">Rio de Janeiro</option>
          <option value="rn">Rio Grande do Norte</option>
          <option value="rs">Rio Grande do Sul</option>
          <option value="ro">Rondônia</option>
          <option value="rr">Roraima</option>
          <option value="sc">Santa Catarina</option>
          <option value="sp">São Paulo</option>
          <option value="se">Sergipe</option>
          <option value="to">Tocantins</option>
        </select>
      </div>

      <div class="form-group">
        <label for="">Hobbies</label>
        <input type="form-control" typeof="text" v-model="produto.hobbies" />
      </div>

      <div class="form-group">
        <label for="">Linguagens de Programação</label>
        <input type="form-control" typeof="text" v-model="produto.linguagensdeprogramacao" />
      </div>

      <div class="form-group">
        <label for="">Biografia</label>
        <input type="form-control" typeof="text" v-model="produto.biografia" />
      </div>

      <button
        type="button"
        class="btn btn-primary"
        @click="mostrarResultado = !mostrarResultado"
      >
        Mostrar
      </button>
    </div>
    <div v-if="mostrarResultado" class="resultado">
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
  </div>
  <div class="altera-titulo">
    <label>Informe um novo título </label>
    <input class="form-control" type="text" v-model="titulo" />
  </div>
  
</template>

<style scoped>
.formulario,
.resultado {
  width: 48%;
  border-radius: 20px;
  padding: 20px
}

.formulario {
  background-color: black;
  color: white;
  margin: 3rem 0 0 3rem;
}

.resultado {
  background-color: black;
  color: white;
  margin: 3rem 0 0 3rem;
}

.altera-titulo {
  background-color: black;
  color: white;
  margin: 1rem 2rem;
  border-radius: 20px;
  padding: .75rem;
}


</style>
