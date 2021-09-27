<template>
    <h1 class="title">Items {{ test }}</h1>
</template>

<script>
export default {
  name: 'App',
  components: {},
  layout: 'nav',
  data() {
    return { test: 'hola' }
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
