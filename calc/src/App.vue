<template>
  <div id = "app">
    <tlist/>

  </div>

</template>

<script>
import tlist from "./components/tlist";

export default {
  name: 'Todo',
  components: {tlist}
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
