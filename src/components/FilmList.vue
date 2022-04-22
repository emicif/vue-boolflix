<template>
  <div>
    <h2>FILM</h2>
     
    <div class="container">
        <FilmItem />
       
    </div>

   
</div>
</template>

<script>

import FilmItem from '@/components/FilmItem.vue'

export default {
    name: 'FilmList',
    components: {
        FilmItem
    },
    data() {
        return {
            urlImage: 'https://image.tmdb.org/t/p/w342',
        }
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



</style>
