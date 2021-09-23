<template>
  <PageContainer>
    <h1 class="title">Games {{ test }}</h1>
  </PageContainer>
</template>

<script>
import PageContainer from '../components/page-container'
export default {
  name: 'App',
  components: {
    PageContainer,
  },
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
