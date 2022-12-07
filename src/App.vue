<template>
  <div id="app">
    <GeekJokes/>
    <NormalJoke/>
    <LoudJoke/>
    <SnakeJoke/>
  </div>
</template>

<script>
import LoudJoke from '@/components/LoudJoke.vue';
import SnakeJoke from '@/components/SnakeJoke.vue';
import NormalJoke from '@/components/NormalJoke.vue';
import GeekJokes from '@/components/GeekJokes.vue';

export default {
  name: 'App',
  components: {
    GeekJokes,
    LoudJoke,
    SnakeJoke,
    NormalJoke,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
