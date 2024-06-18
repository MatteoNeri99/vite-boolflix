
<script>

export default {
  data() {
    return {
      stellePiene:[],
      stelleVuote:[],
      imgUrl:"",
      
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
    },getImg(){

        if(this.serieTvList.backdrop_path != null){
          this.imgUrl='https://image.tmdb.org/t/p/w342/' + this.serieTvList.backdrop_path
        }else if(this.serieTvList.poster_path != null){
          this.imgUrl='https://image.tmdb.org/t/p/w342/' + this.serieTvList.poster_path

        }else{
          this.imgUrl=""
        }

      }
   
    
  },props:{
    serieTvList:{
      type: Object,
      required: true
    }
  },created(){
    this.getStelle()
    this.getImg()
  }
  
}
</script>

<template>


<article>
    
    
    
    <div class="img">

      <img :src="imgUrl" alt="">

    </div>

    <div class="info">

    
      <p>{{ serieTvList.original_name }}</p>
      <p>{{ serieTvList.name }}</p>
      <span class="lang-icon" :class="`lang-icon-${serieTvList.original_language}`"></span>
    

      <div>
        <font-awesome-icon icon="fa-solid fa-star" class="stelle-piene" v-for="(element, index) in stellePiene" :key="index"/>

        <font-awesome-icon icon="fa-solid fa-star" class="stelle-vuote" v-for="(element, index) in stelleVuote" :key="index"/>

      </div>

    </div>

</article>


</template>

<style lang="scss" scoped>
@use "../style/partials/Flag" as *;

article{
  border:1px solid black;
  margin-bottom: 2rem;
  width: calc((1000px / 5)  - 1rem);
  height: 200px;

  img{
      width: 100%;
      height: 100%;
      object-fit: cover;

    }  

  .img{
    display: inline-block;
  }

  .info{
    display:none;
  }

  .img:hover {
    display: none;
  }

  .img:hover .info{
    display: inline-block;
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