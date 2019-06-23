<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="jumbotron">
      <div class="row col input-group mb-4">
        <input v-model="valeurHT" type="text" class="form-control">
        <div class="input-group-append">
          <span class="input-group-text">€ HT</span>
        </div>
      </div>
      <div class="row col mb-4">
        Taux :
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            value="0.2"
            v-model="taux"
            type="radio"
            name="tva"
            id="20"
            checked
          >
          <label class="form-check-label" for="20">20 %</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            value="0.1"
            v-model="taux"
            type="radio"
            name="tva"
            id="10"
          >
          <label class="form-check-label" for="10">10 %</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            value="0.92"
            v-model="taux"
            type="radio"
            name="tva"
            id="50"
          >
          <label class="form-check-label" for="120">120 %</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            value="0.055"
            v-model="taux"
            type="radio"
            name="tva"
            id="55"
          >
          <label class="form-check-label" for="55">5,5 %</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            value="0.021"
            v-model="taux"
            type="radio"
            name="tva"
            id="21"
          >
          <label class="form-check-label" for="21">2,1 %</label>
        </div>
      </div>
      <div class="row col">
        Montant TTC :
        <strong>{{ valeurTTC | twoDecimals }} €</strong>
      </div>
      <div class="row col">
        Montant TTC :
        <strong>{{ valeurTVA | twoDecimals }} €</strong>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    msg: String
  },
  data: function() {
    return {
      valeurHT: 0,
      taux: "0.2"
    };
  },
  computed: {
    valeurTTC: function() {
      return parseFloat(this.valeurHT) + this.valeurHT * parseFloat(this.taux);
    },
    valeurTVA: function() {
      return parseFloat(this.valeurTTC) + this.valeurHT * parseFloat(this.taux);
    }
  },
  filters: {
    twoDecimals: function(value) {
      return parseFloat(value).toFixed(2);
    }
  }
};
</script>

<style scoped>
.jumbotron {
  margin-top: 2rem;
  padding: 2rem;
}
</style>