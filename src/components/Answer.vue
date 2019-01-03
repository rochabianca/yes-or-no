<template>
  <div>
    <p>{{ BigDAnswer.answer }}</p>
    <img :src="BigDAnswer.image" alt="why">
  </div>
</template>

<script>
export default {
  name: "Answer",
  props: {
    BigDAnswer: Object
  }
};
</script>

<style>
</style>
