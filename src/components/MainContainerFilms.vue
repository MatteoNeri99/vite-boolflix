
<script>
import MainFilm from './MainFilm.vue'



export default {
  data() {
    return {
      
      
    }
  },
  components:{
    MainFilm
    
  },props:{
    filmsList:{
      type: Array,
      required: true
    }
  }
  
}
</script>

<template>


<MainFilm v-for="filmsList in filmsList"  :filmsList="filmsList"/>

  
   
</template>

<style lang="scss" scoped>





</style>