<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'App'
  }
</script>

<style>
  body, #app{
    height: 100%;
  }
  #app{
    background-color: #e5e5e5;
  }
</style>
