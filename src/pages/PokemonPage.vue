<template>
  <div>
    <h1>Quien es este Pokemon?</h1>
    <PokemonPicture />
    <PokemonOptions />
  </div>
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions.vue'
import PokemonPicture from '@/components/PokemonPicture.vue'

export default {
  components: { PokemonOptions, PokemonPicture }
}
</script>
