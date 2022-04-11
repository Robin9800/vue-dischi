<template>
  <header class="flex j-start">
      <img class="a-center" src="img/logo-small.svg" alt="dc-logo">
  </header>
</template>

<script>
export default {
    name: "headerComponent"
}
</script>

<style>
/*UTILITIES*/
    .flex{
        display: flex;
    }
    .j-center{
        justify-content: center;
    }
    .j-start{
        justify-content: start;
    }
    .a-center{
        align-self: center;
    }
    header{
        background-color: hsl(210deg 21% 23%);
        height: 8vh;
    }
    header img{
        height: 36px;
        margin-left: 20px;
    }
</style>