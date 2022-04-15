<template>
  <div>
    <h1 v-if="!pokemon">Espere por favor....</h1>
    <div v-else>
      <h1>Quien es este Pokemon?</h1>
      <PokemonPicture :pokemonId="pokemon.id" :showPokemon="showPokemon"/>
      <PokemonOptions
        :pokemons="pokemonArr"
        @selection="checkAnswer"
      />

    </div>

  </div>
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions.vue'
import PokemonPicture from '@/components/PokemonPicture.vue'

import getPokemonOptions from '@/helpers/getPokemonOptions'

export default {
  components: { PokemonOptions, PokemonPicture },
  data () {
    return {
      pokemonArr: [],
      pokemon: null,
      showPokemon: false
    }
  },
  methods: {
    async mixPokemonArray () {
      this.pokemonArr = await getPokemonOptions()

      const randomInt = Math.floor(Math.random() * 4)
      this.pokemon = this.pokemonArr[randomInt]
    },
    checkAnswer (pokemonId) {
      this.showPokemon = !!pokemonId
    }
  },
  mounted () {
    this.mixPokemonArray()
  }
}
</script>
