<template>
  <div class="painelAgenda">
    <div class="painelContato">
      <BlocoContato
        v-for="contato in todosContatos"
        v-bind:key="contato.id" 
        :contato="contato"
      />
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';
import BlocoContato from './BlocoContato.vue';
export default {
    name: "PainelAgenda",
    components: {
      BlocoContato,
    },
    computed: mapGetters(["todosContatos"]),
};
</script>

<style scoped>
.painelAgenda {
    width: 50%;
    padding: 10px;
}
.painelContato {
    background-color: #d8c5ff;
    border-radius: 20px;
    padding: 20px;
}
</style>