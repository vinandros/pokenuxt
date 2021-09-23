<template>
  <div class="nav">
    <div class="logo">
      <h1 class="title">Pokenuxt</h1>
    </div>
    <div class="pages">
      <ul class="ul-links-container">
        <li class="ul-link">Games</li>
        <li class="ul-link">Items</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.nav {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 50px;
}

.logo {
  height: auto;
  width: auto;
}

.title {
  font-size: 3.5rem;
  color: var(--yellow);
  font-family: var(--font-family);
  text-shadow: -3px 0 var(--blue), 0 3px var(--blue), 3px 0 var(--blue),
    0 -3px var(--blue);
  margin: 0;
}

.pages {
}

.ul-links-container {
  list-style-type: none;
  display: flex;
}

.ul-link {
  padding: 5px 10px;
  margin: 0 10px;
  font-family: var(--font-family);
  font-size: 1.5rem;
  cursor: pointer;
}
</style>
