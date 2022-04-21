<template>
    <div>
      <FilmList :films="films" />
    </div>
</template>


<script>

import FilmList from './FilmList.vue'


export default {
  name: 'Main-component',
  props: {
    films: Array
  },
  components: {
    FilmList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
