<template>
  <div>
    <h1>Quien es este Pokemon?</h1>
    <PokemonPicture :pokemonId="100" :showPokemon="true"/>
    <PokemonOptions />
  </div>
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions.vue'
import PokemonPicture from '@/components/PokemonPicture.vue'

import getPokemonOptions from '@/helpers/getPokemonOptions'

console.log(getPokemonOptions)

export default {
  components: { PokemonOptions, PokemonPicture }
}
</script>
