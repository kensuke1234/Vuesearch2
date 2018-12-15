<template>
  <div id="app">
    <Search></Search>
  </div> 
</template> 

<script>
import Search from './components/Search'

export default {
  name: 'app',
  components: {
    Search
  }
}


</script>

<style>
#app {
  font-family: 'メイリオ','Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: blue;
  font-size: 20px;
  margin-top: 200px;
}
</style>
