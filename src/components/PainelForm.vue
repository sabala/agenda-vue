<template>
  <div class="painelForm">
      <div class="formularioAgenda">
          <form @submit="salvar">
            <label for="nome">Nome</label>
            <input type="text" name="nome" id="nome" v-model="nome" required />

            <label for="telefone">Telefone</label>
            <input type="tel" name="telefone" id="telefone" v-model="telefone" v-mask="['(##) ####-####', '(##) #####-####']" required />

            <label for="email">E-mail</label>
            <input type="email" name="email" id="email" v-model="email" />

            <button>Salvar</button>
          </form>
      </div>
  </div>
</template>

<script>
import {mask} from 'vue-the-mask';
import Contato from '../models/Contatos';
import { mapActions } from 'vuex';

export default {
    name: "PainelForm",
    data: () => {
      return {
        nome: "",
        telefone: "",
        email: ""
      }
    },
    directives: {mask},
    methods: {
        ...mapActions(["salvarContato"]),
        salvar(){
            event.preventDefault();
            const contato = new Contato(this.nome, this.telefone, this.email);
            this.salvarContato(contato);
            this.limparForumulario();
            console.log(this.nome[0]);
        },
        limparForumulario(){
            this.nome = "",
            this.telefone = "",
            this.email = ""
        }
    }
}
</script>

<style scoped>
.painelForm {
    width: 50%;
    padding: 10px;
}

.formularioAgenda {
    background-color: white;
    border-radius: 20px;
    padding: 20px;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-weight: bold;
}
input[type=text], input[type=tel], input[type=email], button{
    display: block;
    margin-bottom: 10px;
}
#nome, #email, #telefone{
    width: 75%;
    height: 20px;
}
button {
    background-color: #8A2BE2;
    border: none;
    outline: none;
    border-radius: 5px;
    padding: 5px 15px;
    color: white;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    font-weight: bold;
}
</style>