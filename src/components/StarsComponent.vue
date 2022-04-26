<template>
  <div>
    <font-awesome-icon v-for= "item in 5" :key="item" icon="fa-solid fa-star" :class="{yellowStar: item <= stars}"/>

  </div>
</template>

<script>


/* import the fontawesome core */
import { library } from '@fortawesome/fontawesome-svg-core'

/* import specific icons */
import { faStar } from '@fortawesome/free-solid-svg-icons'

/* import font awesome icon component */
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

/* add icons to the library */
library.add(faStar)


export default {
    name: 'StarsComponent',
    components: {
        FontAwesomeIcon,
    },
    props: {
        vote: Number
    },
    computed: {
        stars(){
            const stars = Math.ceil(this.vote/2);
            return stars;
        }
    }
}
</script>

<style scoped>
.yellowStar {
    color: gold;
}
</style>>

