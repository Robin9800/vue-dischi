<template>
  <div class="container">
      <div class="cards">
          <AlbumItem 
          v-for="item in songs" 
          :key="item.id"
          :song="item"/>
      </div>
  </div>
</template>

<script>
import axios from 'axios';
import AlbumItem from '@/components/AlbumItem'
export default {
    name: "AlbumList",
    data(){
        return {
            songs: []
        }
    },
    props: {
        url: String
    },
    components: {
        AlbumItem
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
        }
    }

}
</script>

<style>
body{
    background-color: hsl(209deg 33% 17%);
}
.container{
    padding: 40px 200px;
}
.cards{
    height: 92vh;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
}
</style>