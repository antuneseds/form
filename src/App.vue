<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Formulário!')
const contador = ref(0)
const produto = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmarsenha: '',
  datadenascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagensdeprogramacao: '',
  biografia:'',
})
const validate = ref(false)

const estados = ref([
  { cod: 'AC', nome: 'Acre' },
  { cod: 'AL', nome: 'Alagoas' },
  { cod: 'AP', nome: 'Amapá' },
  { cod: 'AM', nome: 'Amazonas' },
  { cod: 'BA', nome: 'Bahia' },
  { cod: 'CE', nome: 'Ceará' },
  { cod: 'DF', nome: 'Distrito Federal' },
  { cod: 'ES', nome: 'Espírito Santo' },
  { cod: 'GO', nome: 'Goiás' },
  { cod: 'MA', nome: 'Maranhão' },
  { cod: 'MT', nome: 'Mato Grosso' },
  { cod: 'MS', nome: 'Mato Grosso do Sul' },
  { cod: 'MG', nome: 'Minas Gerais' },
  { cod: 'PA', nome: 'Pará' },
  { cod: 'PB', nome: 'Paraíba' },
  { cod: 'PR', nome: 'Paraná' },
  { cod: 'PE', nome: 'Pernambuco' },
  { cod: 'PI', nome: 'Piauí' },
  { cod: 'RJ', nome: 'Rio de Janeiro' },
  { cod: 'RN', nome: 'Rio Grande do Norte' },
  { cod: 'RS', nome: 'Rio Grande do Sul' },
  { cod: 'RO', nome: 'Rondônia' },
  { cod: 'RR', nome: 'Roraima' },
  { cod: 'SC', nome: 'Santa Catarina' },
  { cod: 'SP', nome: 'São Paulo' },
  { cod: 'SE', nome: 'Sergipe' },
  { cod: 'TO', nome: 'Tocantins' }
]);


function mostrarResultado() {
  if (produto.confirmarsenha != produto.senha || !produto.email.includes("@") || produto.senha == '') {
    alert("Credenciais inválidas ou campos não prenchidos!")
  } else {
   contador.value++
    console.log("qe")
    if (contador.value < 2) {
      validate.value = true
    } else {
      validate.value = false
      contador.value = 0
    }
  }
}
</script>

<template>
  <header>
    <h1 class="titulo">{{ titulo }}</h1>
  </header>

  <main>

  <section class="container d-flex flex-row gap-3 principal">
    <div class="formulario">

      <h2>Cadastro do produto</h2>

      
      <div class="form-group">
        <label for="">Nome: </label>
        <input class="form-control" v-model="produto.nome" />
      </div>

      <div class="form-group">
        <label for="">Email: </label>
        <input class="form-control" v-model="produto.email" />
      </div>

      <div class="form-group">
        <label for="">Senha: </label>
        <input class="form-control" type="password" v-model="produto.senha" />
      </div>

      <div class="form-group">
        <label for="">Confirmar senha: </label>
        <input class="form-control" type="password" v-model="produto.confirmarsenha" />
      </div>

      <div class="form-group">
        <label for="">Data de Nascimento: </label>
        <input type="date" v-model="produto.datadenascimento" />
      </div>

      <div class="form-group">
        <label for="">Endereço: </label>
        <input type="form-control" v-model="produto.endereco" />
      </div>

      <div class="form-group">
        <label for="">Cidade: </label>
        <input type="form-control" v-model="produto.cidade" />
      </div>

      <div class="form-group">
        <label for="">Estado: </label>
        <select name="estado" id="estado" v-model="produto.estado">
          <option v-for="estado in estados" :key="estado.cod" :value="estado.cod"> {{estado.nome}} </option>
        </select>
      </div>

      <div class="form-group">
        <label for="">Hobbies: </label>
        <input type="form-control" typeof="text" v-model="produto.hobbies" />
      </div>

      <div class="form-group">
        <label for="">Linguagens de Programação: </label>
        <input type="form-control" typeof="text" v-model="produto.linguagensdeprogramacao" />
      </div>

      <div class="form-group">
        <label for="">Biografia: </label>
        <input type="form-control" typeof="text" v-model="produto.biografia" />
      </div>

      <div class="caixa-btn">
      <button
        class="btn"
        @click="mostrarResultado()"
      >
        Mostrar
      </button>
      </div>

    </div>

    <div v-if="validate == true" class="resultado">
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
  </section>
  <div class="altera-titulo">
    <label>Informe um novo título </label>
    <input class="form-control" type="text" v-model="titulo" />
  </div>
</main>
</template>

<style scoped>

main {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center
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
  padding: .75rem;
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