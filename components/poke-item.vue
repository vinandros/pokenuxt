/* eslint-disable vue/no-v-html */
<template>
  <div class="container">
    <div :class="pokeType" class="inner-container">
        <img class="poke-image" :src="imgSrc" alt="alt" />
        <p>{{ pokeName }}</p>
    </div>
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
    pokeType: {
      type: String,
      default:'normal'
    }
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
 
  border: 15px solid #DEDEDE;
  background-color: #DEDEDE;
}
.inner-container{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding:10px;
  border-radius: 5px;
}
.bug{
  background-color: #FFBDC8;
}

.normal{
  background-color:#FFFFFF
}

.fighting{
  background-color: #61697D;
}

.flying{
  background-color: #79CAF9;
}

.poison{
  background-color: #B863CB;
}

.ground{
  background-color: #9E623C;
}

.rock{
  background-color: #59585E;
}

.ghost{
  background-color: #B9CAE6;
}

.steel{
  background-color: #9399A5;
}

.fire{
  background-color: #B22E3D;
}

.water{
  background-color: #25A8FE;
}

.grass{
  background-color: #549C4F;
}

.electric{
  background-color: #FDC41B;
}

.psychic{
  background-color: #F163E0;
}

.ice{
  background-color: #BFEEFE;
}

.dragon{
  background-color: #9180EA;
}

.dark{
  background-color: #634C3F;
}

.fairy{
  background-color: #F1AED9;
}

.unknown{
  background-color: #536675;
}

.shadow{
  background-color: #8567E8;
}

.poke-image {
  width: 160px;
  height: 160px;
}
</style>
