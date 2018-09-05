<template>
  <div>
    <h1>Errado!</h1>
    <button @click="next"> Proxima </button>
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
