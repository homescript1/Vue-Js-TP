<template>
  <div class="container" id="app">
    <div class="row justify-content-center text-center">
      <div class="col-6">
        <img alt="Vue logo" src="./assets/logo.png">
      </div>
    </div>
      <Tp2 msg="Calcul de la Tva"/>
  </div>
</template>

<script>
import Tp2 from './components/Tp2.vue'

export default {
  name: 'app',
  components: {
    Tp2
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
