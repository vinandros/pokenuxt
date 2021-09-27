<template>
  <div>
    <Nav></Nav>
    <Nuxt />
  </div>
</template>
<script>
import Nav from '../components/nav.vue'
export default {
  name: 'PageContainer',
  componets: {
    Nav,
  },
}
</script>
