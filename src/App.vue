<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from './components/Home';

export default {
  name: 'App',
  components: {
    Home,
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Berkshire+Swash');
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 16px;
  background: no-repeat center url("./assets/imgs/sky.png");
  background-size: cover;
  padding: 40px;
  color:rgb(245, 210, 15);
}

h1 {
  margin: 0;
  padding: 1rem 0 2.5rem;
  font-family: 'Berkshire Swash', cursive;
  text-shadow: -1px 0 #AD3237, 0 1px #AD3237, 1px 0 #AD3237, 0 -1px #AD3237;
  font-size: 8rem;
}

h2 {
  font-size: 2.5rem;
}

button {
  background: navy;
  border: none;
  font-size: 1rem;
  min-width: 8rem;
  padding: 1rem;
  color: yellow;

  &:hover {
    background: #103f6b;
  }
}

</style>
