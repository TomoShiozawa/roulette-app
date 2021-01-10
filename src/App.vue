<template>
  <h1>ちょっとした時に便利なツール</h1>
  <TabMenu />
</template>

<script>
import TabMenu from './components/TabMenu.vue';

export default {
  name: 'App',
  components: {
    TabMenu,
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
  margin-left: auto;
  margin-right: auto;
  max-width: 1080px;
}
</style>
