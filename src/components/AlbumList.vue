<template>
  <div class="container">
      <div v-if="songs.lenght > 0">
          <AlbumItem :song="songs"/>
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
                (response)=>{
                    //Se la riposta è positiva
                    if(response.status===200){
                        this.songs = response.data;
                        console.log(this.songs);
                    }
                }
            )
        }
    }

}
</script>

<style>
    main{
        height: 92vh;
        background-color: hsl(209deg 33% 17%);
    }
</style>