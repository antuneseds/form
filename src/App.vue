<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Formulário!')
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
  <div>
    <h1 class="titulo">{{ titulo }}</h1>
  </div>
  <div class="container d-flex flex-row gap-3 principal">
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
          <option value="AC">Acre</option>
          <option value="AL">Alagoas</option>
          <option value="AP">Amapá</option>
          <option value="AM">Amazonas</option>
          <option value="BA">Bahia</option>
          <option value="CE">Ceará</option>
          <option value="DF">Destrito Federal</option>
          <option value="ES">Espírito Santo</option>
          <option value="GO">Goiás</option>
          <option value="MA">Maranhão</option>
          <option value="MT">Mato Grosso</option>
          <option value="MS">Mato Grosso do Sul</option>
          <option value="MG">Minas Gerais</option>
          <option value="PA">Pará</option>
          <option value="PB">Paraíba</option>
          <option value="PR">Paraná</option>
          <option value="PE">Pernambuco</option>
          <option value="PI">Piauí</option>
          <option value="RJ">Rio de Janeiro</option>
          <option value="RN">Rio Grande do Norte</option>
          <option value="RS">Rio Grande do Sul</option>
          <option value="RO">Rondônia</option>
          <option value="RR">Roraima</option>
          <option value="SC">Santa Catarina</option>
          <option value="SP">São Paulo</option>
          <option value="SE">Sergipe</option>
          <option value="TO">Tocantins</option>
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
    <div class="altera-titulo">
      <label>Informe um novo título </label>
      <input class="form-control" type="text" v-model="titulo" />
    </div>
  </div>
  
  
</template>

<style scoped>
.formulario,
.resultado {
  width: 65%;
  border-radius: 20px;
  padding: 20px;
  font-family: 'Times New Roman', Times, serif;
  margin-top: 10%;
}

.formulario {
  background-color: black;
  color: white;
  font-family: 'Times New Roman', Times, serif;
}

.resultado {
  background-color: black;
  color: white;
 
}

.altera-titulo {
  background-color: black;
  color: white;
  margin: 3rem 3rem;
  border-radius: 20px;
  padding: .75rem;
  font-family: 'Times New Roman', Times, serif;
  display: grid;
  grid-column: 1 / 3;
}

.principal {
  display:grid;
  grid-template-columns: 1fr 1fr;
  justify-items: center;
}

.titulo {
  text-align: center;
}

</style>
