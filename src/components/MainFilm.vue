
<script>

export default {
  data() {
    return {
      
      flag:"",
    }
  },
  methods:{
    getFlag(lingua){

      axios.get('https://flagcdn.com/16x12/'+ lingua.png)
      .then( ( response ) => {
        console.log(response)
        this.flag=response

      })

    },flagFilm(){
      this.getFlag(filmsList.original_language )
    }
    
   
    
  },props:{
    filmsList:{
      type: Object,
      required: true
    }
  }
  
}
</script>

<template>


<article>

  <h2>Film</h2>
  <div>
    <img :src="'https://image.tmdb.org/t/p/w342/' + filmsList.backdrop_path" alt="">
  </div>
  <p>{{ filmsList.original_title }}</p>
  <p>{{ filmsList.title }}</p>
  <span class="lang-icon" :class="`lang-icon-${filmsList.original_language}`"></span>
  <p>{{ filmsList.vote_average }}</p>

</article>


   
</template>

<style lang="scss" scoped>
@use "../style/partials/Flag" as *;

article{
  border:1px solid black;
  margin-bottom: 2rem;

  h2{
    color: red;
  }

  .lang-icon {
    background-image: url(../../node_modules/@textabledev/langs-flags-list/lang-flags.png);
  }

}



</style>