<template>
    <div id="container">
        <p> {{ msg }}</p>
        <p> Bienvenue sur mon premier TP avec Vue.js</p>
       
    </div>
</template>

<script>
export default {
  name: 'Kpego',
  props: {
    msg: String
  }
}
</script>
