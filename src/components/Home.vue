<template>
  <div>
    <h1>{{ main }}</h1>
    <img src="../assets/imgs/crystal_ball.png">
    <h2>{{ fortune }}</h2>
    <button>click me</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      main: 'Ask Zandar',
      fortune: 'What will your fortune reveal?',
    };
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 80%;
  max-width: 500px;
}
</style>
