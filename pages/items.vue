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
}
</script>

<style>
.title {
  color: blue;
}
</style>
