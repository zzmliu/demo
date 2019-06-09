<template>
  <div id="app">
    <router-view/>
    <tabBar></tabBar>
  </div>
</template>

<script>
  import tabBar from './components/tabBar'
export default {
  name: 'App',
  components:{
    tabBar
  }
}
</script>

<style>
  body,html{
    height: 100%;
  }
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}
</style>
