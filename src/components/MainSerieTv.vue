
<script>

export default {
  data() {
    return {
      
      
    }
  },
  components:{
   
    
  },props:{
    serieTvList:{
      type: Object,
      required: true
    }
  }
  
}
</script>

<template>


<article>
    
    <h2>Serie tv</h2>
    
    <div>
      <img :src="'https://image.tmdb.org/t/p/w342/' + serieTvList.backdrop_path" alt="">
    </div>
    <p>{{ serieTvList.original_name }}</p>
    <p>{{ serieTvList.name }}</p>
    <span class="lang-icon" :class="`lang-icon-${serieTvList.original_language}`"></span>
    <p>{{ serieTvList.vote_average }}</p>

</article>


<!-- serieTvList.original_language -->
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