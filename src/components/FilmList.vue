<template>
  <div>
    <h2>FILM</h2>
        <div class="container">
             <div class="card" v-for="film in films" :key="film.id">
                <FilmItem :film="film"/>
            </div> 
        </div>
    </div>
</template>

<script>

import FilmItem from './FilmItem.vue'

export default {
    name: 'FilmList',
     props: {
        films: Array,
    },
    components: {
        FilmItem
    },
    
    

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



</style>
