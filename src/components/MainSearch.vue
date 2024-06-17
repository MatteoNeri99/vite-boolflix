<script>


export default {
  data() {
    return {
      searchName:"",

      
    }
  },
  components:{
    
  },methods:{
   
  }

}
</script>

<template>

  <section>

    <input type="text" v-model="searchName" > 
    <button  @click="$emit('ricerca', searchName)">cerca</button>
    
   
  </section>

   
</template>

<style lang="scss" scoped>





</style>



