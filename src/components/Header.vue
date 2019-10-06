<template>
  <div>
    <div class="score">Score : {{score}}</div>
    <h1 class="text-center">MATH QUIZ</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: ["score"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  color: #fff;
  margin: 0;
  padding: 0;
}
.score {
  position: absolute;
  top: 5px;
  padding: 10px;
}
</style>
