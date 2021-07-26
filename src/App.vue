<template>
  <div id="app">
      <Insert />
      <br>
      <Table />
  </div>
</template>

<script>
import Insert from '@/components/Insert.vue'
import Table from '@/components/Table.vue'

export default {
  name: 'App',
  components: { Insert,Table }
}
</script>

<style>
#app {
  background-color: bisque;
  height: 100vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 80px
}
</style>
