<template>
  <div>
    <Header />
    <div id="container">
      <PainelForm />
      <PainelAgenda />
    </div>
  </div>
</template>

<script>
import PainelForm from './components/PainelForm.vue'
import PainelAgenda from './components/PainelAgenda.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: { Header, PainelForm, PainelAgenda },
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