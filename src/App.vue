<template>
  <div id="app">
    <h2>Clientes</h2>
    <ListUser/>
    <h2>Supermercados</h2>
    <ListSupermarket/>
    <h2>Formulário Cliente</h2>
    <FormUser/>
    
  </div>
</template>

<script>
import ListUser from './components/ListUser.vue';
import ListSupermarket from './components/ListSupermarket.vue';
import FormUser from './components/FormUser.vue';

export default {
  name: 'app',
  components: {
    ListUser,
    ListSupermarket,
    FormUser
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
