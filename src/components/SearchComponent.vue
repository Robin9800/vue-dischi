<template>
  <div class="search">
      <input type="text" placeholder="Search" 
      v-model="inputText" 
      @keyup.enter="$emit('search', inputText)" />
    </div>
</template>

<script>
export default {
    name: 'SearchComponent'
}
</script>

<style>
    .search{
        display: flex;
        justify-content: center;
        margin-bottom: 30px;
    }
</style>