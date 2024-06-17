<script>
import MainSearch from './MainSearch.vue'
import MainContainerFilms from './MainContainerFilms.vue'
import axios from 'axios'


export default {
  data() {
    return {
      filmsList:[],
      serieTvList:[],
      
    }
  },
  components:{
    MainSearch,
    MainContainerFilms
    
  },methods:{
    getFilm(nome){

      axios.get('https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=' + nome)
      .then( ( response ) => {
          console.log(response.data.results)
          this.filmsList = response.data.results

      })

    },
    getSerieTv(nome){

      axios.get('https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&query=' + nome)
      .then( ( response ) => {
          console.log(response.data.results)
          this.serieTvList = response.data.results

      })

    },
    ricerca(name){

      this.getFilm(name)
      this.getSerieTv(name)

      // console.log(name)
      // getFilm(this.nome)
    }
    
  }
  
}
</script>

<template>

    <MainSearch @ricerca="ricerca" :filmsList="filmsList" :serieTvList="serieTvList"/>

    <MainContainerFilms :filmsList="filmsList" :serieTvList="serieTvList"/>


   
</template>

<style lang="scss" scoped>





</style>