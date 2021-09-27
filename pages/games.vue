<template>
    <h1 class="title">Games {{ test }}</h1>
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
    title: 'Pokenuxt | Games',
    meta: [
      {
        hid: 'games page',
        name: 'games page',
        content: 'pokemons games catalog'
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
