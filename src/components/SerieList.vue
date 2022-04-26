<template>
  <div>
    <h2>SERIE TV</h2>
    <div class="container">
         
        <div class="card" v-for="serie in series" :key= serie.id>
           <img v-if="serie.poster_path != null" :src='urlImage + serie.poster_path'>
           <span v-else>Le serie</span>
            <h3>{{serie.name}}</h3> 
            <h4 v-if="serie.name != serie.original_name">{{serie.original_name}} </h4>
            <span v-else>TITOLO UGUALE</span>
             <p >{{serie.original_language}}</p>
            <!-- <country-flag v-if="sendflag.includes(span2.toLowerCase())" :country='span2' size="small"/>
                <span v-else>{{ span2 }}</span> -->
            <country-flag :country= 'serie.original_language' size='normal'/>
            <!-- <font-awesome-icon v-for= "n in getYellowStar(serie.vote_average)" :key="n" icon="fa-solid fa-star" class="yellow"/> -->

            <p>{{serie.vote_average}}</p>
        </div>
    </div>
</div>
</template>

<script>

import CountryFlag from 'vue-country-flag'


    // /* import the fontawesome core */
    // import { library } from '@fortawesome/fontawesome-svg-core'

    // /* import specific icons */
    // import { faStar } from '@fortawesome/free-solid-svg-icons'

    // /* import font awesome icon component */
    // import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

    // /* add icons to the library */
    // library.add(faStar)


export default {
    name: 'SerieList',
    props: {
        series: Array
    },
    components: {
        CountryFlag,
       // FontAwesomeIcon
    },
    data() {
        return {
            urlImage: 'https://image.tmdb.org/t/p/w342'
        }
    },
    /*
    methods: {
       getYellowStar(voto){
          const votoDiviso = voto / 2; //arrotondare per eccesso
          console.log('votoDiviso', votoDiviso)
          return votoDiviso;
          //console.log('getYellowStar', (voto).toFixed())
        }
    },
    */
    
}
</script>





<style lang="scss" scoped>

h2 {
    text-align: center;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
}

.card {
    width: 20%;
    
    border: 1px solid grey;
    text-align: center;
    padding: 10px;
}

img {
    width: 100%;
}

.yellow {
    color: yellow;
}
.white {
    color: white;
    border: 1px solid black;
}
/*
<div class="flex-wrap">
                <h4>Lingua originale: </h4>
                <country-flag v-if="sendflag.includes(span2.toLowerCase())" :country='span2' size="small"/>
                <span v-else>{{ span2 }}</span>
            </div>
*/

</style>
