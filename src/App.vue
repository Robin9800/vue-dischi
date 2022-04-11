<template>
  <div id="app">
    <Header/>
    <AlbumList :url="apiUrl"/>
  </div>
</template>

<script>
import Header from "/src/components/Header.vue"
import AlbumList from "/src/components/AlbumList.vue"


export default {
  name: 'App',
  components: {
    Header,
    AlbumList
  },
  data(){
    return {
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
    }
  }
}
</script>

<style>

</style>