
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
    <p>{{ serieTvList.original_name }}</p>
    <p>{{ serieTvList.name }}</p>
    <p>{{ serieTvList.original_language }}</p>
    <p>{{ serieTvList.vote_average }}</p>

</article>


   
</template>

<style lang="scss" scoped>

article{
  border:1px solid black;
  margin-bottom: 2rem;

  h2{
    color: red;
  }
}



</style>