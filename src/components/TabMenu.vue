<template>
  <TabView>
    <TabPanel header="抽選">
      <Raffle />
    </TabPanel>
  </TabView>
</template>

<script>
import Raffle from './raffle/Raffle.vue';

export default {
  name: 'App',
  components: {
    Raffle,
  },
};
</script>

<style lang="scss"></style>
