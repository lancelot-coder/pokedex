<template>
  <div class="row">
    <div class="col-md-2">
      <div v-for="pokemon in pokemons">
        <a @click="selectPokemon(pokemon)">{{pokemon.name}}</a>
      </div>
    </div>
    <div>
      <PokeViewer v-bind:selectedPokemon="selectedPokemon"/>
    </div>
  </div>
</template>

<script>
import PokeViewer from "./PokeViewer";

export default {
  name: 'PokeList',
  props: ["pokemons"],
  components: {
    PokeViewer
  },
  data() {
    return {
      selectedPokemon: null
    }
  },
  methods: {
    selectPokemon: function(pokemon) {
      return fetch(pokemon.url).then((res) => res.json()).then((json) => this.selectedPokemon = json);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  a {
    cursor: pointer;
  }
  a:hover {
    color: #5474af !important;
  }
</style>
