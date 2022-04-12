<template>
  <div class="card">
      <img :src="song.poster" alt="">
      <h2>{{song.title}}</h2>
      <h3>{{song.author}}</h3>
      <h4>{{song.year}}</h4>
      <h5>{{song.genre}}</h5>
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
        background-color: hsl(210deg 21% 23%);
        height: 300px;
        max-width: 160px;
        margin: 10px 20px;
    }
    .card img{
        align-self: center;
        height: 150px;
        width: 150px;
        padding: 12px;
    }
    .card h2{
        font-size: 18px;
        margin-top: 10px;
        margin-bottom: 18px;
        color: white;
    }
    .card h3,h4,h5{
        color: grey;
    }
    .card h5{
        margin-top: 10px;
    }
</style>