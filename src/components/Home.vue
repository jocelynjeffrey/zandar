<template>
  <div>
    <h1>{{ main }}</h1>
    <img src="../assets/imgs/crystal_ball.png">
    <h2>{{ question }}</h2>
    <transition name="fade">
      <h2 v-if="showFortune">{{ fortune }}</h2>
    </transition>
    <button @click="getFortune">click me</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      main: 'Ask Zandar',
      question: 'What will your fortune reveal?',
      showFortune: false,
    };
  },
  computed: {
    fortune() {
      switch (true) {
        case this.moodVariable <= 15:
          return 'yes!';
        case this.moodVariable <= 30:
          return 'definitely';
        case this.moodVariable <= 45:
          return 'nooooooope.';
        case this.moodVariable <= 60:
          return 'absolutely!';
        case this.moodVariable <= 75:
          return 'your chances look good!';
        case this.moodVariable <= 90:
          return 'I think not.';
        default:
          return 'hmmm...maybe?';
      }
    },
  },
  methods: {
    getFortune() {
      this.showFortune = true;
      this.fortune = 'heyyy';
    },
  },
};
</script>

<style lang="scss" scoped>
  img {
    width: 80%;
    max-width: 500px;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity 1s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>
