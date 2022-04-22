<template>
  <div>
    <h2>FILM</h2>
     <font-awesome-icon icon="fa solid fa-star" class="yellow" />
      <font-awesome-icon icon="fa solid fa-star" class="white" />
    <div class="container">
        
        <div class="card" v-for="film in films" :key= film.id>
           <img v-if="film.poster_path != null" :src='urlImage + film.poster_path'>
           <span v-else>NETFLIX</span>
            <h3>{{film.title}}</h3> 
            <h4 v-if="film.title != film.original_title">{{film.original_title}} </h4>
            <span v-else>TITOLO UGUALE</span>
            <p >{{film.original_language}}</p>
            <!-- <country-flag v-if="sendflag.includes(span2.toLowerCase())" :country='span2' size="small"/>
                <span v-else>{{ span2 }}</span> -->
            <country-flag :country= 'film.original_language' size='normal'/>
            <p><font-awesome-icon v-for= "(star, index) in getYellowStar(film.vote_average)" :key="index" icon="fa-solid fa-star" class="yellow"/>
           <!-- <font-awesome-icon v-for= "(star, index) in getWhiteStar(film.vote_average)" :key="index" icon="fa-solid fa-star" class="white"/></p> -->
 
            <p >{{film.vote_average}}</p>
        </div>   
    </div>

   
</div>
</template>

<script>

import CountryFlag from 'vue-country-flag'
/* import the fontawesome core */
import { library } from '@fortawesome/fontawesome-svg-core'

/* import specific icons */
import { faStar } from '@fortawesome/free-solid-svg-icons'

/* import font awesome icon component */
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

/* add icons to the library */
library.add(faStar)

export default {
    name: 'FilmList',
    props: {
        films: Array,
    },
    components: {
        CountryFlag,
        FontAwesomeIcon
  
    },
    data() {
        return {
            urlImage: 'https://image.tmdb.org/t/p/w342',
        }
    },
    methods: {
        getYellowStar(voto){
            if (voto > 5){
            
            console.log('getYellowStar', (voto).toFixed())
            } else {
                 console.log('getWhiteStar', (voto).toFixed())
            }
            
        },
        
    }
   
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
/*
<div class="flex-wrap">
                <h4>Lingua originale: </h4>
                <country-flag v-if="sendflag.includes(span2.toLowerCase())" :country='span2' size="small"/>
                <span v-else>{{ span2 }}</span>
            </div>
*/

.yellow {
    color: yellow;
}
.white {
    color: white;
    border: 1px solid black;
}

</style>
