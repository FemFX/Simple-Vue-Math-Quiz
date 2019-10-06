<template>
  <div class>
    <div class="center">
      <span class="num1">{{ num1 }}</span> +
      <span class="num2">{{ num2 }}</span> =
      <input type="number" class="result" v-model="val" />
    </div>
    <button class="btn btn-primary next" @click="handleSubmit(val)">Next</button>
  </div>
</template>
<script>
export default {
  name: "Game",
  props: ["num1", "num2"],
  data() {
    return {
      val: ""
    };
  },
  methods: {
    handleSubmit(val) {
      this.$emit("handleSubmit", val);
      this.val = ""
    }
  }
};
</script>
<style scoped>
* {
  color: #fff;
}
input {
  color: #000;
}
.center {
  position: absolute;
  top: 50%;
  left: 50%;
  padding: 15px;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  font-size: 24px;
  margin-left: 5px;
}
input {
  width: 50px;
}
.next {
  position: absolute;
  bottom: 15px;
  right: 15px;
}
</style>