<template>
    <div>
            <img v-if="film.poster_path != null" :src='urlImage + film.poster_path'>
            <span v-else></span>
                <h3>{{film.title}}</h3> 
                <h4 v-if="film.title != film.original_title">{{film.original_title}} </h4>
                <span v-else></span>
                <p >{{film.original_language}}</p>
                <!-- <country-flag v-if="sendflag.includes(span2.toLowerCase())" :country='span2' size="small"/>
                    <span v-else>{{ span2 }}</span> -->
                <country-flag :country= 'film.original_language' size='normal'/>
                <StarsComponent :vote="film.vote_average" />
       
    </div> 

    
</template>


<script>

import CountryFlag from 'vue-country-flag'

import StarsComponent from './StarsComponent.vue'


export default {
    name: 'FilmItem',
    props: {
        film: Object, 
    },
    components: {
        CountryFlag,
        StarsComponent
    },
    data() {
        return {
            urlImage: 'https://image.tmdb.org/t/p/w342',
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



</style>>

