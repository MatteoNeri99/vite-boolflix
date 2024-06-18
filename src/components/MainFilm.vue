
<script>

export default {
  data() {
    return {
      
      stellePiene:[],
      stelleVuote:[],
    }
  },
  methods:{

    getStelle(){
      let voto = parseInt(Math.ceil(this.filmsList.vote_average /2 ) , 10)
      for(let index=0; index < voto ; index++){

        this.stellePiene.push(index)

      }

      for(let index=voto; index < 5 ; index++){

        this.stelleVuote.push(index)

      }
    }
   

    
    
   
    
  },props:{
    filmsList:{
      type: Object,
      required: true
    }
  },created(){
    this.getStelle()
  }
  
}
</script>

<template>


<article>

  <template>
  
</template>

  <h2>Film</h2>
  <div>
    <img :src="'https://image.tmdb.org/t/p/w342/' + filmsList.backdrop_path" alt="">
  </div>
  <p>{{ filmsList.original_title }}</p>
  <p>{{ filmsList.title }}</p>
  <span class="lang-icon" :class="`lang-icon-${filmsList.original_language}`"></span>
 
  <div class="stelle-piene" v-for="(element, index) in stellePiene" :key="index">
    <font-awesome-icon icon="fa-solid fa-star"/>

  </div>
  <div class="stelle-vuote" v-for="(element, index) in stelleVuote" :key="index">
    <font-awesome-icon icon="fa-solid fa-star"/>

  </div>
  
   
 
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

  .stelle-piene{
    color: gold;
  }

  .stelle-vuote{
    color:white;
  }

}



</style>