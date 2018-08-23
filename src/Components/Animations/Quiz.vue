<template>
  <div>
    <h2 v-text="title"></h2>
    <component 
      :is="mode"
      @answerFnc="answerFnc">
    </component>
  </div>
</template>

<script>
import Question from "./Question"
export default {
  data (){
    return {
      title: "Quiz",
      mode: "question-component",
    }
  },
  components: {
    "question-component" : Question
  },
  methods:{
    answerFnc () {
      alert("I'M HERE!");
    }
  }
}
</script>
  
<style scoped>

</style>
