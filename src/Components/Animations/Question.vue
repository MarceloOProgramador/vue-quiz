<template>

  <div>

    <div class="card-header">

      <h2>{{ask}}</h2>

    </div>
    
    <div class="card-body center">

      <form @submit.prevent="checkResult" class="form-inline">

        <input type="text" name="answer" id="answer" placeholder="Resultado" v-model="reply"/>

        <button>Responder</button>

      </form>

    </div>

  </div>
</template>

<script>

export default {
  created(){
    this.generateQuestion();
  },

  data ()  {
    return {
      ask : "Gerando pergunta...",
      result : 0,
      reply : "",
    }
  },

  methods : {

    generateQuestion() {

      let numberOne = this.generateRandomNumber(1, 100);

      let numberTwo = this.generateRandomNumber(1, 100);

      this.result = numberOne + numberTwo;

      this.ask = numberOne + ' + ' + numberTwo + ' = ' + '?';
    },
    generateRandomNumber (min, max){

      return Math.round(Math.random() * (max - min) + min);

    },
    checkResult () {

      let mode = "error-component"

      if (this.reply == this.result) {

        mode = "success-component";

      } 

      this.$emit("answerFnc", mode)
    }
  }
}
</script>

<style>

</style>
