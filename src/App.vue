<template>
  <div id="app"> 
    <NavBar />
    <DataTable />
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import DataTable from './components/DataTable.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    DataTable
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
