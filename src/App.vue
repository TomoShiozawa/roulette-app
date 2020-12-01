<template>
  <Raffle />
</template>

<script>
import Raffle from './components/Raffle.vue';

export default {
  name: 'App',
  components: {
    Raffle,
  },
};
</script>

<style lang="scss">
body {
  background-color: var(--surface-a);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--text-color);
  margin-top: 60px;
}
</style>
