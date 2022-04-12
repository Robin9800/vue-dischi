<template>
  <div class="search">
      <input type="text" placeholder="Search" 
      v-model="inputText" 
      @keyup.enter="performSearch" />
      <button @keyup.enter="performSearch">Cerca</button>
    </div>
</template>

<script>
export default {
    name: 'SearchComponent',
    data(){
        return {
            //Il valore di input text sarà una stringa
            inputText: ''
        }
    },
    methods: {
        //creo la funzione che andrò ad inserire nel keyup.enter
        performSearch(){
            this.$emit('search',this.inputText);
        }
    }
}
</script>

<style>
    .search{
        display: flex;
        margin-bottom: 20px;
        flex-direction: column;
    }
    .search input{
        width: 200px;
        align-self: center;
        margin: 6px 0px;
    }
    .search button{
        width: 50px;
        align-self: center;
    }
</style>