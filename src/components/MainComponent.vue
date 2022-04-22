<template>
    <div>
      <FilmList :films="films" />
      <SeriesList :series="series" />
    </div>
</template>


<script>

import FilmList from './FilmList.vue'
import SeriesList from './SerieList.vue'


export default {
  name: 'MainComponent',
  props: {
    films: Array,
    series: Array
 
  },
  components: {
    FilmList,
    SeriesList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
