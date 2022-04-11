<template>
  <div class="card">
      <img :src="song.poster" alt="">
      <h2>{{song.title}}</h2>
      <h3>{{song.author}}</h3>
      <h4>{{song.year}}</h4>
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
        height: 280px;
        max-width: 150px;
        margin: 20px 20px;
    }
    .card img{
        align-self: center;
        height: 150px;
        width: 150px;
        padding: 12px;
    }
    .card h2{
        font-size: 17px;
        margin-top: 10px;
        margin-bottom: 20px;
        color: white;
    }
    .card h3,h4{
        color: grey;
    }
</style>