<template>
  <div>
    <h2>FILMS</h2>
    <div class="container">
         
        <div class="card" v-for="film in films" :key= film.id>
           <img :src='urlImage + film.poster_path'>
            <h3>{{film.title}}</h3> 
            <h4>{{film.original_title}} </h4>
            <p class="p">{{film.original_language}}</p>
            <!-- <country-flag v-if="sendflag.includes(span2.toLowerCase())" :country='span2' size="small"/>
                <span v-else>{{ span2 }}</span> -->
                 <country-flag :country= 'film.original_language' size='normal'/>
            <span>{{film.voto_average}}</span>
        </div>
    </div>
</div>
</template>

<script>

import CountryFlag from 'vue-country-flag'

export default {
    name: 'FilmList',
    props: {
        films: Array
    },
    components: {
        CountryFlag
    },
    data() {
        return {
            urlImage: 'https://image.tmdb.org/t/p/w342'
        }
    }
}
</script>

<style lang="scss" scoped>

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

</style>
