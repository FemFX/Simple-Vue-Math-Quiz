<template>
  <div id="app">
    <Header :score="score" />
    <Game :num1="num1" :num2="num2" @handleSubmit="handleSubmit" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Game from "./components/Game.vue";

export default {
  name: "app",
  components: {
    Header,
    Game
  },
  data() {
    return {
      score: 0,
      num1: undefined,
      num2: undefined
    };
  },
  created() {
    this.getRandoms();
  },
  methods: {
    handleSubmit(val) {
      if (this.num1 + this.num2 == val) {
        this.score++;
      }
      this.getRandoms();
    },
    getRandoms() {
      this.num1 = Math.floor(Math.random() * 10) + 1;
      this.num2 = Math.floor(Math.random() * 10) + 1;
    }
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background-color: #24272e;
  color: #fff;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
#btn {
  position: absolute;
  top: 50%;
  left: 50%;
  padding: 15px;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
