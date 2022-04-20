<template>
  <div>
    <input type=text v-model="query" />
    <button @click="queryApi">Cerca</button>
    <div v-for="item in query" :key="item.id"> 
      <h2>{{item.name}}</h2>
      <p>{{item.original_name}}</p>
      <span>{{item.original_language}}</span>

    </div>
  </div>
  
</template>

<script>

import axios from 'axios';


export default {
  name: 'MainComponent',
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
      this.query = response.data.results
    }).catch(error=>{
      console.log(error);
    })
    }
   // const query = 'verde';
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
