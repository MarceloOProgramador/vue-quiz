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
import successComponent from "./Answer/successComponent" 
import errorComponent from "./Answer/errorComponent" 
export default {
  data (){
    return {
      title: "Quiz",
      mode: "question-component",
    }
  },
  components: {
    "question-component" : Question,
    "success-component" : successComponent,
    "error-component" : errorComponent
  },
  methods:{
    answerFnc (mode) {

      if(mode == undefined){
        this.mode = "question-component"
      } else {
        this.mode = mode
      }

    }
  }
}
</script>
  
<style scoped>

</style>
