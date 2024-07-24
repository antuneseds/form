<script setup>

import { ref, reactive } from 'vue';
 
const validate = ref(false)

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
  biografia: ''
})

function mostrarResultado() {
  if (
    produto.confirmarsenha != produto.senha ||
    !produto.email.includes('@') ||
    produto.senha == ''
  ) {
    alert('Credenciais inválidas ou campos não prenchidos!')
  } else {
    contador.value++
    console.log('qe')
    if (contador.value < 2) {
      validate.value = true
    } else {
      validate.value = false
      contador.value = 0
    }
  }
}

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
])
</script>

<template>
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
            <option v-for="estado in estados" :key="estado.cod" :value="estado.cod">
              {{estado.nome}}
            </option>
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
          <button class="btn" @click="mostrarResultado()">Mostrar</button>
        </div>
        </div>
      
    </section>
</template>
