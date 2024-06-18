
<script>
import MainFilm from './MainFilm.vue'
import MainSerieTv from './MainSerieTv.vue'



export default {
  data() {
    return {
      
      
    }
  },
  components:{
    MainFilm,
    MainSerieTv
    
  },props:{
    filmsList:{
      type: Array,
      required: true
    },
    serieTvList:{
      type: Array,
      required: true
    }
  },methods:{
   
    
  }
  
}
</script>

<template>


<MainFilm v-for="(filmsList,index) in filmsList" :key="index"  :filmsList="filmsList"/>
<MainSerieTv v-for="(serieTvList,index) in serieTvList" :key="index"  :serieTvList="serieTvList"/>

  
   
</template>

<style lang="scss" scoped>





</style>