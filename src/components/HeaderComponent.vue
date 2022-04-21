<template>
  <div class="header">
    <h1>Boolflix</h1>
    <div class="searchbar">
      <input type=text placeholder="Ricerca per titolo" v-model="textToSearch" />
      <button @click="search">Cerca</button>

    </div>
    
  
  </div>
  
</template>

<script>



export default {
  name: 'HeaderComponent',
   data(){
    return {
      
      textToSearch: '',
    //  searching: false,

    }
  },
  methods:{
    search(){
      /*
        this.queryApi('tv').then((response)=>{
          this.series = response.data.results;
          console.log('this.series', this.series)
          this.searching = false;
        });
        this.queryApi('movie').then((response)=>{
          this.films = response.data.results;
          console.log('this.films', this.films)
          this.searching = false;
        });
       */
      this.$emit('search', this.textToSearch);
    },
    /*
    queryTvApi(){
     this.queryApi('tv')
    },
    queryMovieApi(){
      this.queryApi('movie')
    },
    queryApi(searchType){
      if (!this.searching && this.query.length>0){
        this.searching = true;
        const params = {
          query: this.query,
          api_key: this.apiKey,
          language: 'it-IT'
        } 
    return axios.get(this.apiUrl + searchType, {params}).catch(error=>{
          console.log(error);
          this.searching = false;
        })
    }
    }
    */
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  background-color: black ;
  height: 50px;
  display: flex;
  justify-content: space-between;
}
h1 {
  color: red;
}

.searchbar {
  line-height: 50px;
  vertical-align: middle;
}


</style>
