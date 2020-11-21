<template>
  <div id="painelForm">
      <div id="formularioAgenda">
          <form>
            <label for="nome">Nome</label>
            <input type="text" name="nome" id="nome">
            <label for="nome">Telefone</label>
            <input type="tel" id="telefone" v-mask="['(##) ####-####', '(##) #####-####']">
            <label for="nome">E-mail</label>
            <input type="email" name="email" id="email">

            <button>Salvar</button>
          </form>
      </div>
  </div>
</template>

<script>
import {mask} from 'vue-the-mask'

export default {
    name: "PainelForm",
    directives: {mask}
}
</script>

<style scoped>
#painelForm {
    width: 40%;
    padding: 10px;
}

#formularioAgenda {
    background-color: white;
    border-radius: 20px;
    padding: 20px;
    font-family: Arial, Helvetica, sans-serif;
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
    font-family: Arial, Helvetica, sans-serif;
    font-weight: bold;
}
</style>