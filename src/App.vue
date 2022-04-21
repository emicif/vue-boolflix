<template>
  <div id="app">
   <HeaderComponent @search= "searching" />
   <MainComponent :films="films" />
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },
  methods: {
      searching(textToSearch){
        console.log(textToSearch);
        const params = {
            query: textToSearch,
            api_key: this.apiKey,
            language: 'it-IT'
          } 
        axios.get(this.apiUrl + 'movie', {params} ).then((response)=>{
          console.log(response);
          if (response.status === 200){
            this.films = response.data.results
          }

        }).catch(errore => console.log(errore))
      }
  },
  data(){
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '5125681fd07a81d9933e9268c5c370c3',
      films: [],
      //series: []
    }
}

}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

}
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
</style>
