<template>
  <div>
    <h2>{{ask}}</h2>
    <form @submit.prevent="checkResult">
      <input type="text" name="answer" id="answer" placeholder="Resultado" v-model="reply"/>
      <button>Responder</button>
    </form>
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
      reply : ""
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

      if (this.reply == this.result) {

        alert("Acertou!!");

        this.generateQuestion();

        this.reply = "";

      } else {

        alert("Errou!");

      }
    }
  }
}
</script>

<style>

</style>
