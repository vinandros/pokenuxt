<template>
  <div>
    <Nav></Nav>
    <div class="container"><slot></slot></div>
  </div>
</template>

<script>
import Nav from './nav'
export default {
  name: 'PageContainer',
  componets: {
    Nav,
  },
}
</script>

<style scoped>
.container {
  width: 60vw;
  height: auto;
  margin: 0 auto;
  max-width: 1200px;
}

@media screen and (max-width: 360px) {
  .container {
    width: 95%;
  }
}
</style>
