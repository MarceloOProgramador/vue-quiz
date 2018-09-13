<template>

  <div class="alert alert-danger">

    <h1>Errado!</h1>
    
    <button @click="next" class="btn btn-primary"> Proxima </button>

  </div>

</template>

<script>
export default {

  methods : {

    next () {

      this.$emit("answerFnc")
      
    }

  }
  
}
</script>

<style scoped>

</style>
