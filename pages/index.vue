<template>
  <div>
    <ul class="ul-poke-list">
      <li
        v-for="pokemon in pokemons"
        :key="pokemon.id"
        class="li-poke-item"
      >
        <PokeItem :img-src="pokemon.image" :poke-type="pokemon.type" :poke-name="pokemon.name" />
      </li>
    </ul>
  </div>
</template>

<script>
import PokeItem from '../components/poke-item'
export default {
  name: 'App',
  components: {
    PokeItem,
  },
  layout: 'nav',
  async asyncData({ params, $http }) {
    const response = await $http.$get(
      `${process.env.apiURL}/pokemon`
    )
    const pokemonsIDs = response.results

    const pokemons = await Promise.all(
      pokemonsIDs.map(async (pokemonId) => {
        let pokeData = {}
        pokeData = await $http.$get(pokemonId.url)

        pokeData.image = pokeData.sprites.other.dream_world.front_default
        pokeData.type = pokeData.types[0].type.name;
        console.log(pokeData)
        return pokeData
      })
    )
    return { pokemons }
  },
  head: {
    title: 'Pokenuxt | Home',
    meta: [
      {
        hid: 'main page',
        name: 'main page',
        content: 'pokemons catalog main page'
      }
    ],
  },
}
</script>

<style>
.ul-poke-list {
  list-style-type: none;
  display: flex;
  justify-content: center;
  align-items: space-between;
  flex-wrap: wrap;
}

.li-poke-item {
  margin: 10px 10px;
  border: 1px solid black;
  border-radius: 5px;
}
</style>
