<template>
  <div id="app">
   <HeaderComponent />
   <MainComponent :url="apiKey"/>
    
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
//import axios from 'axios'


export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },
 data(){
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '5125681fd07a81d9933e9268c5c370c3',
      
    }
}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
