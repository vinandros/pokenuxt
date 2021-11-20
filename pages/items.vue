<template>
    <h1 class="title">{{items}} </h1>
</template>

<script>
export default {
  name: 'App',
  components: {},
  layout: 'nav',
  async asyncData({ params, $http }) {
    const response = await $http.$get(
      `${process.env.apiURL}/item`
    )
    const itemsIDs = response.results

    const items = await Promise.all(
      itemsIDs.map(async (item) => {
        let itemData = {}
        itemData = await $http.$get(item.url)

        itemData.image = itemData.sprites.default
        itemData.name = itemData.names.filter((lang) => lang.language.name === 'en')[0];
        console.log(itemData)
        return itemData
      })
    )
    return { items }
  },
  head: {
    title: 'Pokenuxt | Items',
    meta: [
      {
        hid: 'items page',
        name: 'items page',
        content: 'pokemons items catalog'
      }
    ],
  },
}
</script>

<style>
.title {
  color: blue;
}
</style>

