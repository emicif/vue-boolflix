<template>
  <div id="app">
   
       <input type=text v-model="query" />
    <button @click="queryApi">Cerca</button>
  </div>
</template>

<script>
//import HeaderComponent from './components/HeaderComponent.vue'
//import MainComponent from './components/MainComponent.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    //HeaderComponent,
    //MainComponent,
  },
  data(){
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '5125681fd07a81d9933e9268c5c370c3',
      query: '',
    }
  },
  methods: {
    queryApi(){
const params = {
      query: this.query,
      api_key: this.apiKey,
      language: 'it-IT'
    }
    axios.get(this.apiUrl + 'tv', {params}).then((response)=>{
      console.log(response);
    }).catch(error=>{
      console.log(error);
    })
    }
   // const query = 'verde';
    
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
