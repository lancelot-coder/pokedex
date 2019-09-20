<template>
  <div>
    <div v-show="selectedPokemon">
        <img v-bind:src="selectedPokemon.sprites.front_default">
        <h2>{{pokemonName}}</h2>
        <h3>abilities</h3>
        <ul>
            <li v-for="ability in selectedPokemon.abilities">{{ability.ability.name}}</li>
        </ul>
    </div>
  </div>
</template>

<script>
import _ from 'lodash'

export default {
  name: 'PokeViewer',
  props: ["selectedPokemon"],
  computed: {
      pokemonName: function() {
          return _.capitalize(this.selectedPokemon.name)
      }
  }
}
</script>
<style scoped>

</style>