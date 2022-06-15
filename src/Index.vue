<template>
  <div id="app">
    <excel-to-json></excel-to-json>
  </div>
</template>

<script>
import ExcelToJson from './components/ExcelToJson.vue'
export default {
  name: 'App',
  components: {
    ExcelToJson
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
  margin-top: 60px;
}
</style>
