
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
      let voto = parseInt(Math.ceil(this.serieTvList.vote_average /2 ) , 10)
      for(let index=0; index < voto ; index++){

        this.stellePiene.push(index)

      }

      for(let index=voto; index < 5 ; index++){

        this.stelleVuote.push(index)

      }
    }
   
    
  },props:{
    serieTvList:{
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
    
    <h2>Serie tv</h2>
    
    <div>
      <img :src="'https://image.tmdb.org/t/p/w342/' + serieTvList.backdrop_path" alt="">
    </div>
    <p>{{ serieTvList.original_name }}</p>
    <p>{{ serieTvList.name }}</p>
    <span class="lang-icon" :class="`lang-icon-${serieTvList.original_language}`"></span>
    <p>{{ serieTvList.vote_average }}</p>

    <div class="stelle-piene" v-for="(element, index) in stellePiene" :key="index">
    <font-awesome-icon icon="fa-solid fa-star"/>

  </div>
  <div class="stelle-vuote" v-for="(element, index) in stelleVuote" :key="index">
    <font-awesome-icon icon="fa-solid fa-star"/>

  </div>

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

  .stelle-piene{
    color: gold;
  }

  .stelle-vuote{
    color:white;
  }
}




</style>