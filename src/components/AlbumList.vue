<template>
  <div class="container">
      <SearchComponent @searchEmit="filterGenre"/>
      <div class="cards">
          <AlbumItem 
          v-for="item in filteredSongs" 
          :key="item.id"
          :song="item"/>
      </div>
  </div>
</template>

<script>
import axios from 'axios';
import AlbumItem from '@/components/AlbumItem';
import SearchComponent from '@/components/SearchComponent';

export default {
    name: "AlbumList",
    data(){
        return {
            songs: [],
            genreSelected: "*"
        }
    },
    props: {
        url: String
    },
   computed: {
       filteredSongs(){
            const filter = this.genreSelected;
            if(filter==="*"){
                return this.songs
            }else{
                const filtered = this.songs.filter(function(song){
                    return song.genre === filter
                })
                return filtered
            } 
       }
   },
    components: {
        AlbumItem,
        SearchComponent
    },
    //Chiamo il metodo che mi fa caricare i dati
    mounted(){
        this.loadData();
    },
    methods:{
        loadData(){
            axios.get(this.url).then(
                (result)=>{
                    //Se la riposta è positiva restituisci l'array
                    if(result.status===200){
                        this.songs = result.data.response;
                        console.log(this.songs);
                    }
                }
            )
        },
        filterGenre(selectedGenre){
           this.genreSelected = selectedGenre;
        }
    }

}
</script>

<style>
body{
    background-color: hsl(209deg 33% 17%);
}
.container{
    padding: 20px 200px;
}
.cards{
    height: 92vh;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
}
</style>