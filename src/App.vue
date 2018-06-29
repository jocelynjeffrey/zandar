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

html, body, .viewport {
  width: 100%;
  height: 100%;
  margin: 0;
}

#app {
  display: flex;
  flex-direction: column;
  height: 100%;
  background: no-repeat center url("./assets/imgs/sky.png");
  background-size: cover;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color:rgb(245, 210, 15);
  font-size: 16px;
  text-align: center;
}

h1 {
  margin: 0;
  font-family: 'Berkshire Swash', cursive;
  text-shadow: -1px 0 #AD3237, 0 1px #AD3237, 1px 0 #AD3237, 0 -1px #AD3237;
  font-size: 8rem;
}

h2 {
  font-size: 2rem;
  font-style: italic;
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
