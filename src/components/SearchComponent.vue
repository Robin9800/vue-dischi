<template>
  <div class="search">
      <select v-model="selectedGenre"
      @change="$emit('searchEmit', selectedGenre)">
            <option value="*">All categories</option>
            <option value="Pop">Pop</option>
            <option value="Rock">Rock</option>
            <option value="Metal">Metal</option>
            <option value="Jazz">Jazz</option>
        </select>
  </div>
</template>

<script>
export default {
    name: 'SearchComponent',
    data(){
        return {
            selectedGenre: '*'
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
    .search select{
        width: 200px;
        align-self: center;
        margin: 6px 0px;
        background-color: hsl(210deg 15% 23%);
        color: white;
    }
    .search button{
        width: 50px;
        align-self: center;
        margin-top: 6px
    }
</style>