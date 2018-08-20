<template>
  <div>
    <h2 v-text="title"></h2>
    <question-component></question-component>
  </div>
</template>

<script>
import Question from "./Question"
export default {
  data (){
    return {
      title: "Quiz"
    }
  },
  components: {
    "question-component" : Question
  }
}
</script>
  
<style scoped>

</style>
