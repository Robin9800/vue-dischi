<template>
  <div id="app">
    <Header/>
    <Album/>
  </div>
</template>

<script>
import Header from "/src/components/Header.vue"
import Album  from "/src/components/Album.vue"


export default {
  name: 'App',
  components: {
    Header,
    Album

}
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>