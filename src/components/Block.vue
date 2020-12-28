<template>
  <div class="card" v-if="showBlock" @click="stopTimer">Click Me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      setTimer: null,
      reactionTime: 0,
    };
  },
  methods: {
    startTimer() {
      this.setTimer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.setTimer);
      this.$emit("endGame", this.reactionTime);
    },
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  updated() {},
  unmounted() {},
};
</script>

<style>
.card {
  width: 400px;
  border-radius: 25px;
  padding: 100px 0;
  margin: 25px auto;
  background: #0faf87;
  color: wheat;
}
</style>