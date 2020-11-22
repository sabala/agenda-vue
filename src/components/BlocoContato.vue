<template>
  <div class="blocoContatos">
        <span class="inicial"> {{contato.nome[0]}} </span>
        <div class="descricaoContato">
            <span class="nome"> {{contato.nome}} </span>
            <span> {{contato.telefone}} </span>
            <span> {{contato.email}} </span>
        </div>
         <div class="botao">
            <button @click="excluirContato(contato.id)" class="botaoRemover">
                <img src="../img/lixeira.png" alt="Remover Contato">
            </button>
        </div>
       
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
    name: "BlocoContato",
    props: {
      contato: Object,
    },
    methods: mapActions(["excluirContato"])
}
</script>

<style scoped>
.blocoContatos {
    display: flex;
    background-color: white;
    border-radius: 10px;
    margin-bottom: 10px;
    padding: 5px;
}
.descricaoContato {
    width: 100%;
    float: right;
    text-align: right;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}
.descricaoContato span {
    display: block;
    font-size: 100%;
}
.inicial{
    width: 60px;
    height: 50px;
    line-height: 50px;
    background-color: #8A2BE2;
    font-size: 35px;
    color: white;
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
    border-radius: 100%;
    text-align: center;
    margin: 2px;

}
.nome {
    font-weight: bolder;
    font-size: 150% !important;
}
.botao {
    margin-top: 9%;
}
.botaoRemover {
    outline: none;
    border: none;
    background-color: white;
}
.botaoRemover img {
    width: 15px;
}
.botaoRemover img:active {
    filter: invert(50%);
}
.botaoRemover:hover {
    cursor: pointer;
}
</style>