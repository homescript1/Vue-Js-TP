<template>
  <div id="app">
     <Kpego msg="" />
     <p>
     <button class="btn btn-primary" @click="satisfied">Satisfait </button>
      <button class="btn btn-primary" @click="not_satisfied">Pas Satisfait </button>
    </p> 
    Votre choix pour satisfait est : {{ satisf }} et pas satisfait est : {{ nosatisf }}
  </div>
</template>


<script>
import Kpego from './components/Kpego.vue'

export default {
  //name => nom de l'application
  name: 'app',
  components: {
    //comme ici ou on affiche le contenu de la balise HelloWorld plus haut.
    Kpego
  },
  data: function() {
    return  {
      satisf: true,
       nosatisf : false
    }
  },methods: {
    satisfied(){
      this.satisf = false;
    },
    not_satisfied(){
      this.nosatisf = true;
    }
  }
}
</script>

<style scoped>
</style>
