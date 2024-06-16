
<script>

export default {
  data() {
    return {
      
      
    }
  },
  components:{
   
    
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
  <p>{{ filmsList.original_title }}</p>
  <p>{{ filmsList.title }}</p>
  <p>{{ filmsList.original_language }}</p>
  <p>{{ filmsList.vote_average }}</p>

</article>


   
</template>

<style lang="scss" scoped>

article{
  border:1px solid black;
  margin-bottom: 2rem;
}



</style>