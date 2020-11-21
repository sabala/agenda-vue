<template>
  <div>
    <Header />

    <div id="container">
      <PainelForm />
      <PainelContatos />
    </div>
  </div>
</template>

<script>
import PainelContatos from './components/PainelContatos.vue'
import PainelForm from './components/PainelForm.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: { Header, PainelForm, PainelContatos },
}
</script>

<style>
body {
  margin: 0;
  background-color: #dddddd;
}
#container {
  display: flex;
  padding: 20px;
}
</style>