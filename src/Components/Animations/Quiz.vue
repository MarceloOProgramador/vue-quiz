<template>

  <div>

    <h2 v-text="title"></h2>
    
    <transition name="rotation" mode="out-in">

      <component :is="mode" @answerFnc="answerFnc"></component>

    </transition>

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

.rotation-leave-active{
  animation: rotation-out 2.5s;
}
.rotation-enter-active{
  animation: rotation-in 2.5s;
}
@keyframes rotation-out {
  from{
    transform: rotateY(0deg);
  }
  to{
    transform: rotateY(90deg);
  }
}

@keyframes rotation-in{
  from{
    transform: rotateY(90deg);
  }
  to{
    transform: rotateY(0deg);
  }
}

</style>
