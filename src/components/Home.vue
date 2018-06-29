<template>
  <div class="wrapper">
    <h1>{{ main }}</h1>
    <div class="crystal-ball">
      <img src="../assets/imgs/crystal_ball.png">
      <transition name="fade">
        <h2 class="fortune-text" v-if="showFortune">{{ fortune }}</h2>
      </transition>
      <button v-if="!showFortune" @click="getFortune">click me</button>
    </div>
    <h2>{{ question }}</h2>
  </div>
</template>

<script>
import axios from 'axios'; // eslint-disable-line
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
        case this.fortuneVariable <= 15:
          return 'yes!';
        case this.fortuneVariable <= 30:
          return 'definitely';
        case this.fortuneVariable <= 45:
          return 'nooooooope.';
        case this.fortuneVariable <= 60:
          return 'absolutely!';
        case this.fortuneVariable <= 75:
          return 'looks good!';
        case this.fortuneVariable <= 90:
          return 'I think not.';
        default:
          return 'hmmm...maybe?';
      }
    },
  },
  methods: {
    getFortune() {
      // axios.get('http://localhost:3000/api/v1/temperature')
      //   .then(() => {
      //     this.setFortune();
      //     this.reset();
      //   })
      //   .catch(error => console.log('error from server', error)); // eslint-disable-line
      this.setFortune();
    },
    setFortune() {
      this.fortuneVariable = (Math.random() * 100).toFixed(2) - 0;
      console.log(this.fortuneVariable); // eslint-disable-line
      this.showFortune = true;
      this.reset(); // remove when api is called
    },
    reset() {
      setTimeout(
        function() { // eslint-disable-line
          this.showFortune = false;
          console.log('fortune is:', this.fortune); // eslint-disable-line
        }.bind(this),
        1400,
      );
    },
  },
};
</script>

<style lang="scss" scoped>
  .wrapper {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 2rem;
  }

  img {
    width: 80%;
    max-width: 500px;
    height: 100%;
  }

  .crystal-ball {
    display: flex;
    flex-direction: column;
    align-items: center;

    button {
      position: absolute;
      top: 50%;
    }

    .fortune-text {
      position: absolute;
      color: #FC0F71;
      text-shadow: -1px 0 #B00049, 0 1px #B00049, 1px 0 #B00049, 0 -1px #B00049;
      top: 45%;
      font-size: 6rem;
      margin: 0;
    }
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>
