<template>
    <div>
        <font-awesome-icon icon="fa solid fa-star" class="yellow" />
        <font-awesome-icon icon="fa solid fa-star" class="white" />

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
             
           
                <font-awesome-icon v-for= "n in getYellowStar(film.vote_average)" :key="n" icon="fa-solid fa-star" class="yellow"/>
          
                
                <!-- <p><font-awesome-icon v-for= "star in getYellowStar(film.vote_average)" :key="star" icon="fa-solid fa-star" class="yellow"/> -->
            <!-- <span><font-awesome-icon v-for= "(star, index) in getWhiteStar(film.vote_average)" :key="index" icon="fa-solid fa-star" class="white"/></span> -->

                <!-- <p><font-awesome-icon v-for= "n in 5" :key="n" icon="fa-solid fa-star" class="yellow"/></p> -->
           
              <!--  <p>{{film.vote_average}}</p> -->
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
    name: 'FilmItem',
     props: {
        films: Array,
    },
    components: {
        CountryFlag,
        FontAwesomeIcon
    },
    /*
    data() {
        return {
            votoDiviso: 4,
        }
    },
    */
     methods: {
       getYellowStar(voto){
          const votoDiviso = voto / 2; //arrotondare per eccesso
          console.log('votoDiviso', votoDiviso)
          return votoDiviso;
          //console.log('getYellowStar', (voto).toFixed())
        }
    },
    
}
</script>


<style scoped>
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
</style>>

