<template>
  <p>Reaction Time {{ reactionTime }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["reactionTime"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.reactionTime < 300) {
      this.rank = "Ninja Fingers";
    } else if (this.reactionTime < 500) {
      this.rank = "Rapid Fingers";
    } else {
      this.rank = "Snail Pace...";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>