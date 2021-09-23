<template>
  <div>
    <PageContainer>
      <div>
        <ul class="ul-poke-list">
          <li
            v-for="pokemon in pokemons"
            :key="pokemon.id"
            class="li-poke-item"
          >
            <PokeItem :img-src="pokemon.image" :poke-name="pokemon.name" />
          </li>
        </ul>
      </div>
    </PageContainer>
  </div>
</template>

<script>
import PageContainer from '../components/page-container'
import PokeItem from '../components/poke-item'
export default {
  name: 'App',
  components: {
    PageContainer,
    PokeItem,
  },
  async asyncData({ params, $http }) {
    const response = await $http.$get(
      `${process.env.apiURL}/pokemon?offset=10&limit=10`
    )
    const pokemonsIDs = response.results

    const pokemons = await Promise.all(
      pokemonsIDs.map(async (pokemonId) => {
        let pokeData = {}
        pokeData = await $http.$get(pokemonId.url)

        pokeData.image = pokeData.sprites.other.dream_world.front_default
        console.log(pokeData)
        return pokeData
      })
    )
    return { pokemons }
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
  width: 200px;
  height: 200px;
}
</style>
