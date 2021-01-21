<template>
  <div id="app">
    <Inventory />
  </div>
</template>

<script>
import Inventory from './views/Inventory';


export default {
  components: {
    Inventory
  },
  name: 'App',
}
</script>

<style>
#app {
  width: 600px;
  color: #2c3e50;
  margin: 60px auto;
}
</style>
