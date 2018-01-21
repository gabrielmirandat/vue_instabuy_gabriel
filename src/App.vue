<template>
  <div id="app">
    <v-app>
      <toolbar/>
      <v-container fluid>
        <lista-produtos/>
      </v-container>
    </v-app>
  </div>
</template>

<script>
import ListaProdutos from './components/ListaProdutos'
import Toolbar from './components/objects/Toolbar'

export default {
  name: 'App',
  components: {
    Toolbar,
    ListaProdutos
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
