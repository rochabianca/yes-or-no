<template>
  <div>
    <h2>Throw here you doubts and we will answer. YES or NO.</h2>
    <form>
      <label for="question">Question</label>
      <input name="question" type="text" placeholder="Do you liked this app?">
      <input type="submit" value="Send your doubt" v-on:click="makeQuestion">
      <button v-on:click="clearForm">Clear</button>
    </form>
    <Answer v-if="answerFromBigD && answerFromBigD.answer" :BigDAnswer="answerFromBigD"/>
  </div>
</template>

<script>
import axios from "axios";
import Answer from "./Answer";

export default {
  name: "Question",
  components: {
    Answer
  },
  data: function() {
    return {
      answerFromBigD: null
    };
  },
  methods: {
    makeQuestion: function(e) {
      e.preventDefault();
      axios.get("https://yesno.wtf/api").then(response => {
        this.answerFromBigD = response.data;
      });
    },
    clearForm: function() {
      this.answerFromBigD = null;
    }
  }
};
</script>

<style>
</style>
