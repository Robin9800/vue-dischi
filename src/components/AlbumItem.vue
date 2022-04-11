<template>
  <div class="card">
      <img :src="song.image" alt="">
      <h2>{{song.title}}</h2>
      <h3>{{song.author}}</h3>
      <h3>{{song.year}}</h3>
  </div>
</template>

<script>
export default {
    name: 'AlbumItem',
    props: {
        song: Object
    }
}
</script>

<style>
    .card{
        text-align: center;
    }
</style>