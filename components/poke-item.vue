/* eslint-disable vue/no-v-html */
<template>
  <div class="container">
    <img class="poke-image" :src="imgSrc" alt="alt" />
    <p>{{ pokeName }}</p>
  </div>
</template>

<script>
export default {
  name: 'PokeItem',
  props: {
    imgSrc: {
      type: String,
      default: 'https://via.placeholder.com/150',
    },
    pokeName: {
      type: String,
      default: 'Pikachu',
    },
  },
}
</script>

<style scoped>
.container {
  width: 100%;
  height: auto;
  font-family: var(--font-family);
  font-size: 1.5rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.poke-image {
  width: 150px;
  height: 150px;
}
</style>
