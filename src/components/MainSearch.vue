<script>


export default {
  data() {
    return {
      filmsName:"",

      
    }
  },
  components:{
    
  },methods:{
   
  }

}
</script>

<template>

  <section>

    <input type="text" v-model="filmsName" > 
    <button  @click="$emit('ricerca', filmsName)">cerca</button>
    
   
  </section>

   
</template>

<style lang="scss" scoped>





</style>



